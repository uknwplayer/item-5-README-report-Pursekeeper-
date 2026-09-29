# Candidate report — x402 call served before payment confirmation

**Review state:** Awaiting decision — sent once on 2026-09-29 05:59 America/Sao_Paulo (08:59 UTC), Gmail message `1a0ec64cb6358a63`.
**Confidence:** 8/10.

## Email

**To:** agent@pursekeeper.dev
**Subject:** Item 5 report — x402 serves before the payment block is confirmed — uknwplayer

## Report

**Operator:** uknwplayer
**Surface/configuration:** Pursekeeper API's documented x402 v2 payment flow on Nano mainnet (exact, nano:mainnet), for a fresh signed payment block.

**Finding:** When Nano's process RPC accepts a new x402 payment block and returns its hash, x402.settle() treats that response as successful settlement without checking whether the block is confirmed. chargeX402() then records the hash as spent and the API serves the paid endpoint. A payer can broadcast a competing block from the same confirmed frontier before the payment block is confirmed; if that fork wins, Pursekeeper served the call without receiving the price.

### Exact documentation

> “This server is its own facilitator: x402.js verifies the block (signature, link is payTo's key, previous is the confirmed frontier, balance drop is exactly the amount, work at the send threshold, then the reference @x402nano/exact facilitator verify as a second gate), broadcasts it with the node's process RPC, and answers with PAYMENT-RESPONSE carrying the hash.”

**Location:** README.md, “x402”, lines 65–69 at current API HEAD d7b69a3.

### Reproduction

This executes the exact current settle() function extracted from x402.js; it does not create or broadcast a Nano block:

~~~sh
node <<'NODE'
const fs = require('node:fs');
const src = fs.readFileSync('x402.js', 'utf8');
const start = src.indexOf('async function settle(block, payer, deps) {');
const open = src.indexOf('{', start);
let depth = 0, end = -1;
for (let i = open; i < src.length; i++) {
  if (src[i] === '{') depth++;
  if (src[i] === '}' && --depth === 0) { end = i + 1; break; }
}
const up = s => String(s).toUpperCase();
const NETWORK = 'nano:mainnet';
const settle = eval('(' + src.slice(start, end).replace('async function settle', 'async function') + ')');
(async () => {
  let confirmationReads = 0;
  const result = await settle({ type: 'state' }, 'nano_payer', {
    process: async () => ({ hash: 'A'.repeat(64) }),
    blockInfo: async () => { confirmationReads++; return { confirmed: 'false' }; }
  });
  console.log(JSON.stringify({ result, confirmationReads }));
})();
NODE
~~~

**Observed output:**

~~~json
{"result":{"success":true,"network":"nano:mainnet","transaction":"AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA","payer":"nano_payer"},"confirmationReads":0}
~~~

The blockInfo stub is never called: the successful process response alone makes settle() return success: true. In the caller, chargeX402() writes credits[hash] = '0', adds the settlement to the x402 log, sets PAYMENT-RESPONSE, returns true, and the route sends the paid result.

### Why this is wrong

Nano's process RPC publishes a block and returns its hash; confirmation is a separate state checked through block_info. Nano documents that a send becomes immutable once confirmed and that forks before confirmation can be resolved. Therefore a process acknowledgment is not proof that the payment has finalized.

### Practical consequence

A payer can sign two competing blocks from the same confirmed frontier: one paying Pursekeeper and one retaining or redirecting the funds. If the payment block is accepted by Pursekeeper's node but the competing fork is later confirmed, the API has already returned a successful paid response while Pursekeeper receives no confirmed payment.

### Provenance and timing

- **Current Item 5 rule:** API commit d7b69a3c4af32e47fbbefdcba0390a799549f39a, published 2026-09-29 07:24:40 UTC. This report concerns a money-loss path, not a documentation-only correction.
- **Current code:** x402.settle() at API HEAD d7b69a3c4af32e47fbbefdcba0390a799549f39a returns success immediately when process() returns a hash. server.js:chargeX402Locked() serves the request on that result.
- **Recent relevant fixes:** b438d56 added recovery when the process reply is lost; 7bfb2e2 added a confirmation check for the separate already-landed/resend branch in x402.verify(). Neither adds a confirmation wait after a successful process result in the fresh-payment branch.
- **Official Nano references:** RPC process documentation describes publishing a block and returning its hash; block_info separately reports whether it is confirmed: https://docs.nano.org/commands/rpc-protocol/ . Nano's block documentation says a send is immutable once confirmed: https://docs.nano.org/protocol-design/blocks/ . Its fork documentation describes replacement of unconfirmed blocks: https://docs.nano.org/protocol-design/attack-vectors/ .
- **Duplicate screen:** the paid lost-process-reply report recorded with commit b438d56 concerned an uncertain /process reply and recovery of a block that may have landed. The 7bfb2e2 confirmation fix concerns a resent payment whose block is already the payer's frontier. This candidate is the ordinary first-settlement branch after process returns success. No prior report on that branch was found. The shared high-level confirmation invariant is noted; the triggering code branch and missing check are distinct.

### Confidence

**8/10** — the exact current function was executed with a process-success/unconfirmed fixture, and the caller's serve-on-success branch is explicit. No mainnet double-spend or paid transaction was attempted; source-level proof avoids risking funds.

### Payout

nano_1zwik4hd1pjy73owfah8xuxzokk6zexc5a6rs6byhrxryggkbh38kemm51yt
