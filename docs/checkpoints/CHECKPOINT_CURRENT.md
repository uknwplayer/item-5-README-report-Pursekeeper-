# Current Checkpoint — Pursekeeper Item 5 Reports

**Date:** 2026-09-29 07:24 UTC baseline; candidate researched 08:05 UTC
**Block:** 034 — financial-loss path found
**State:** AWAITING PURSEKEEPER DECISION — SENT ONCE

## Current Item 5 rule

Pursekeeper's current rule is in API commit [`d7b69a3`](https://github.com/Pursekeeper/api/commit/d7b69a3c4af32e47fbbefdcba0390a799549f39a). Documentation-only errors are fixed/credited unpaid. Paid findings must prove a concrete path on a documented configuration causing an unauthorized transfer, duplicate settlement, accepting less than the price, or credit/refund that never returns. Source trace is sufficient; do not spend Nano to prove a candidate. Temporary unavailability is excluded. The previous paid-review cutoff rule is no longer an eligibility gate. Items already in Pursekeeper's inbox at the policy change stay under the previous rule.

## Candidate: direct API payment rejected by checkout-wallet heuristic

**Subject:** `Item 5 report — valid API payment rejected by checkout heuristic — uknwplayer`
**Confidence:** 8/10
**Status:** Sent once at 2026-09-29 05:11 America/Sao_Paulo (08:11 UTC); Gmail message `1a0ec37b5628f92a`. Awaiting Pursekeeper decision.

The API README tells callers to send `price_raw` “from any wallet” and retry with `X-Nano-Payment`. Current `server.js` treats a wallet as a Subnano checkout when its recent account history contains any send to Pursekeeper's API address and any send to the Subnano fee collector, without verifying that the two sends belong to the same checkout. For an otherwise eligible, unlisted, not-yet-classified payer with five history entries containing one exact direct API payment and one separate fee transfer, the exact helper returns `true`. Then `creditForUnlocked()` marks the payment `NO_CREDIT_REASON` and exits before API credit or refund. The payment remains with Pursekeeper and the caller receives an error/402.

A local fixture extracted from the exact current helper returned `current: true`; the parent of `b438d56` returned `false`. Commit `b438d56` (2026-09-28 22:25:05 UTC) removed the previous `history.length > 4` bypass, introducing this five-entry false-positive case. This is a source-level reproduction; no real payment was made. Current upstream baseline was revalidated at `d7b69a3c4af32e47fbbefdcba0390a799549f39a` (2026-09-29 07:24:40 UTC). Pursekeeper's latest relevant email at check was 07:10:42 UTC, accepting the earlier DNS report for 2 XNO and confirming its fix at `887bb6c`.

### Duplicate screen

Issue #74 concerned the inverse false negative: non-API purpose sends could be accepted as API credit. Other prior checkout reports concerned RPC failure or missed checkout transfers, not a direct API payer falsely classified from an unrelated fee send. No matching report/issue was found in the checked registers. Candidate confidence: 8/10; live paid transaction not tested.

### Report draft

See [`docs/candidates/ITEM5-2026-09-29-checkout-wallet-false-positive.md`](../candidates/ITEM5-2026-09-29-checkout-wallet-false-positive.md). Do not send unless the operator explicitly says **“Enviar”**. Payout address: `nano_1zwik4hd1pjy73owfah8xuxzokk6zexc5a6rs6byhrxryggkbh38kemm51yt`.


## Block 035 — next financial-loss hunt in progress (2026-09-29 05:13 BRT)

- Revalidated API `main` at `d7b69a3c4af32e47fbbefdcba0390a799549f39a` (07:24:40 UTC), project `main` at `b243dbefd590ab444929e720be5a982f66f4965b`, current rule in `examples/research/README.md`, recent commits, issues, coverage map and Gmail.
- Current scope: four specified money outcomes only. The checkout-wallet false positive was sent once (Gmail `1a0ec37b5628f92a`, 05:11 BRT) and is excluded as a duplicate. Latest inbound Pursekeeper mail remains 07:10:42 UTC; no decision on that new report yet.
- Initial leads for this block: inspect current settlement/charge/refund source and the recent post-fix money-path commits for a distinct exploitable financial outcome. No live payment, Nano transfer, or report send during analysis.


## Block 035 — financial candidate ready (2026-09-29 05:18 BRT)

- Current API HEAD revalidated at d7b69a3c4af32e47fbbefdcba0390a799549f39a (07:24:40 UTC); wanted-list rule unchanged. Project branch was 4a07ade at block start. Gmail's latest relevant inbound reply remains 07:10:42 UTC; no answer has arrived to the checkout-wallet report sent 08:11 UTC.
- Screened current server.js credit and charge paths, x402 verification/settlement, facilitator /settle, /v1/work error hand-back, /v1/fetch hand-back, /v1/hash pre-charge validation, and examples/no-node.js send/receive retries. The five-entry checkout-wallet false positive remains a separate report awaiting decision and was excluded from this hunt.
- Candidate ready: a fresh x402 payment is treated as settled after the Nano node's process RPC returns a hash. The exact current x402.settle() function was extracted and executed locally with process -> {hash} and an unconfirmed blockInfo stub; result was success:true, and confirmation reads were zero. Caller code marks the block spent and returns the paid response. No real transfer or fork was made.
- Distinguish from prior reports: #322/lost-process-reply handling addressed an uncertain process response; 7bfb2e2 added confirmation checking only for a resend whose block is already the payer's frontier. The newly documented candidate is the ordinary first-settlement path when process returns success. Duplicate risk from the shared high-level confirmation invariant is stated in the draft.
- Public /v1/stats read timed out from this environment; no live paid test attempted. Official Nano RPC docs separate process publication/hash return from block_info.confirmed; Nano docs say a send is immutable after confirmation and forks can replace unconfirmed blocks.
- Candidate report: [ITEM5-2026-09-29-x402-unconfirmed-process-ack.md](../candidates/ITEM5-2026-09-29-x402-unconfirmed-process-ack.md). Confidence 8/10; not sent. Payout address unchanged.
