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
