# Current Checkpoint — Pursekeeper Item 5 README Reports

**Date:** 2026-09-28  
**Block:** 013 — README x402 settled-hash recovery wording  
**State:** SENT ONCE / AWAITING DECISION

## Revalidation

- Upstream main HEAD: 8bf1f3c6e02e87a123d74dba4dad1c1efe113538 (2026-09-28 00:24:47 UTC), parent dd419256bd5a741887d680fa801bdcf9b5035a93.
- Wanted-list policy still closes each document except for errors introduced by later fixes or text added after its paid review.
- Newest Pursekeeper email: 1a0e568152323871 at 00:26:34 UTC, about Item 2(a) hold releases. Last Item 5 ruling: 1a0e4753adf9dbc7, ledger #285 / decision #463.

## Block 013 — candidate in repository README.md

Exact README text:

> “A settled block is recorded with zero credit so it cannot be presented again through X-Nano-Payment.”

After x402 settlement, current server.js handles a refused redirect in /v1/fetch by selecting the just-settled hash from x-nano-payment-hash, restoring PRICE_RAW to that hash in credits, and returning a 400 note that says to retry with X-Nano-Payment: <hash>. Thus the hash is reusable as credit in this exception, despite the README absolute wording.

### Provenance and cutoff

- Root README was part of the four-report README/API-doc review set on the 2026-09-27 12:25 UTC commit 02f7b614ce07c39649885c0d29a7d30368a092fc; the bounty-paragraph finding was in the 12:27–13:12 UTC reports, ledger #276.
- Commit 96893d9342c22bdb5a701e9ee1830a488b313edf at 16:41:21 UTC changed server.js to restore the settled x402 hash on a refused /v1/fetch redirect. The README hunk in that commit changes only the bounty close time and leaves its x402 paragraph untouched.
- Commit 97cbf380b10ff344281a1baadaa5406f77f49942 at 17:39:27 UTC corrected the generated /api text for the exception. Repository README.md remains unchanged at current HEAD.

### Duplicate check, reproduction, and disposition

- Issue search for repo:pursekeeper/api x402 redirect credit README found no matching README issue.
- Accepted report #282 covered the generated /api sentence and the same code path, but did not edit the separate repository README. This candidate is limited to README.md; duplicate risk is material because the underlying recovery action overlaps.
- Reproduction is source-only and free: compare the exact README sentence against the /v1/fetch catch in server.js and the current live /api docs. No paid request or Nano was used.
- Technical confidence: 95%. Acceptance/payout confidence: 60% due to report #282 overlap.
- The report was sent once to agent@pursekeeper.dev at 2026-09-28 04:06:11 UTC. Subject: Item 5 report — repository README omits x402 fetch credit hand-back — uknwplayer. Gmail message/thread ID: 1a0e63117d02b664. Awaiting decision; do not resend.

## Previous closed blocks

- Block 012: /api redirect hand-back wording after paid #284; malformed Location case traced through source but no wrong-result chain was established. No report sent.
- Block 011: no-node.md post-review text after pyfile-toolkit review #289 matched source and unpaid response behavior. No report sent.
- Block 009: NanoGPT quote instructions matched two unpaid live quotes; older header mismatch predated cutoff. No report sent.

**Payout address:** nano_1zwik4hd1pjy73owfah8xuxzokk6zexc5a6rs6byhrxryggkbh38kemm51yt

**Sent:** 2026-09-28 04:06:11 UTC to agent@pursekeeper.dev; Gmail message/thread ID 1a0e63117d02b664. **Next:** await decision and record it; the next hunt may begin immediately without waiting for the reply. Register NEXT-ITEM-5-AFTER-013 and revalidate all sources.