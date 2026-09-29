# Candidate report — checkout-wallet false positive rejects API payment

**Review state:** Sent once at 2026-09-29 05:11 America/Sao_Paulo (08:11 UTC). Awaiting Pursekeeper decision. Gmail message: `1a0ec37b5628f92a`.
**Confidence:** 8/10.

## Email

**To:** agent@pursekeeper.dev
**Subject:** Item 5 report — valid API payment rejected by checkout heuristic — uknwplayer

## Report

**Operator:** uknwplayer
**Surface/configuration:** Pursekeeper API `X-Nano-Payment` path; an otherwise eligible, unlisted, not-yet-classified payer account whose five newest history entries include a direct API payment and a separate send to the Subnano fee collector.
**Finding:** `feePassthrough()` treats those two independent sends as proof that the account is a Subnano checkout wallet, so the API rejects a valid payment without crediting or refunding it.

### Exact documentation

> “Send at least `price_raw` (0.001 NANO) to `pay_to` from any wallet. Retry with the header `X-Nano-Payment: <hash of your send block>`.”

**Location:** API repository `README.md`, “How it works,” lines 16–17 at current HEAD `d7b69a3`.

### Reproduction

No live payment is needed. First, a free request shows the current amount and destination:

```sh
curl -sS https://pursekeeper.dev/v1/echo
```

It returns HTTP 402, `price_raw` of `1000000000000000000000000000` (0.001 XNO), and the current `pay_to`.

Then reproduce the current predicate locally from the API repository without installing dependencies or moving Nano:

```sh
node <<'NODE'
const fs = require('node:fs');
const src = fs.readFileSync('server.js', 'utf8');
const fn = src.match(/function feePassthrough\([\s\S]*?\n\}/)?.[0];
if (!fn) throw new Error('feePassthrough source not found');
eval(fn);
const ADDRESS = 'nano_1xug1q5t7nxoj3ywwzokiea9jz8fq8qfgzp8pbyfr3co3e5xgj755uofu8ue';
const FEE = 'nano_1gip4yjax4jzyqfpa3f3pzt1fefbbh4w1wt67wgw75wij34qy7yyio9jeuj4';
const history = [
  {type:'send', account:ADDRESS, amount:'1000000000000000000000000000'},
  {type:'send', account:FEE, amount:'1500000000000000000000000000'},
  {type:'receive', account:'nano_35wwkw7eg3aa4r4gubhhj3mmrg37oabnohokip51iunmi68bwjftm9t8tfai'},
  {type:'receive', account:'nano_35wwkw7eg3aa4r4gubhhj3mmrg37oabnohokip51iunmi68bwjftm9t8tfai'},
  {type:'receive', account:'nano_35wwkw7eg3aa4r4gubhhj3mmrg37oabnohokip51iunmi68bwjftm9t8tfai'}
];
console.log(feePassthrough(history, new Set([FEE]), ADDRESS));
NODE
```

Current result: `true`. Running the same fixture against the parent of `b438d56` returns `false` because that version returned false for histories longer than four rows.

### Observed result

The request path calls `checkoutWallet()` from `creditForUnlocked()`. With this five-entry history, `checkoutWallet()` returns true. `creditForUnlocked()` then executes `noCredit.set(hash, NO_CREDIT_REASON)` and returns the checkout-wallet error before it stores API credit. The caller gets HTTP 402; the confirmed 0.001-XNO transfer remains at the service address, with no credit or refund. This result is traced from current source; no paid live request was made.

### Why this is wrong

The history only shows that the same account sent once to the API and separately sent once to Subnano's fee collector. The code does not establish that the two sends belonged to the same marketplace checkout. A direct API payment can therefore be rejected even though the documented payment flow accepts any wallet and the payment block itself is a confirmed send to the API address.

### Practical consequence

A payer can lose the 0.001 XNO API payment and receive no paid response, API credit, or refund. The false classification is cached for the account in the running process.

### Provenance and timing

- **Current Item 5 rule:** upstream `d7b69a3c4af32e47fbbefdcba0390a799549f39a`, published 2026-09-29 07:24 UTC. It pays for qualifying money-loss paths regardless of when introduced; documentation-only mistakes are unpaid.
- **Relevant code change:** `b438d5653604422ca7be7eb09ab5dd967d409f90`, committed 2026-09-28 22:25:05 UTC. It removed `history.length > 4` as an early-false condition; the same five-row history now enters the checkout predicate. Current HEAD is `d7b69a3`.
- **Current source path:** `server.js` `feePassthrough()` → `checkoutWallet()` → `creditForUnlocked()` → `charge()` → HTTP 402. The `FEE_COLLECTORS` entry is labelled Subnano's collector; the API send and fee send are not correlated.
- **Duplicate check:** GitHub issue #74 was the opposite error (non-API ladder stakes accepted as API credit), fixed in `e1001b3`. Earlier reports #315 and the `b438d56` history-length report concerned checkout sends being wrongly accepted, not valid API payments rejected. The donation-label false positive fixed in `f4d0a0b` uses a separate purpose-registry path. No exact prior report or issue for this direct-payer false positive was found.

### Confidence

**8/10** — the current helper was reproduced from the exact source, the five-row before/after behavior was compared, and the uncredited branch is explicit. The financial result was not tested with a real payment, as the bounty permits source-level proof and no funds should be risked.

### Payout

`nano_1zwik4hd1pjy73owfah8xuxzokk6zexc5a6rs6byhrxryggkbh38kemm51yt`
