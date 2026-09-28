# Current Checkpoint — Pursekeeper Item 5 README Reports

**Date:** 2026-09-28  
**Block:** 011 — Post-review no-node.md audit  
**State:** CLOSED / NO QUALIFYING FINDING / NO REPORT PENDING

## Revalidation

- Upstream `pursekeeper/api` main HEAD remains `8bf1f3c6e02e87a123d74dba4dad1c1efe113538` (2026-09-28 00:24:47 UTC), parent `dd419256bd5a741887d680fa801bdcf9b5035a93`.
- The current wanted-list rule was reread: Item 5 is closed for a document except errors introduced by a later fix or text added after that document's paid review.
- The newest Pursekeeper email was read in full: `1a0e568152323871` at 00:26:34 UTC concerns three released Item 2(a) holds, says no report/fee is owed, and says nothing else is outstanding. The last Item 5 ruling remains email `1a0e4753adf9dbc7`, ledger #285 / decision #463.
- Targeted GitHub issue search found only old issue #2, a separate paid-review enquiry about distinguishing payment flows.

## Block 011 — eligible document, source, and reproduction

The eligible diff was `examples/no-node.md`. Its newly recorded paid review ended at 00:17 UTC; commit `8bf1f3c` added text seven minutes later. The additions distinguish seller-owned `extra` metadata, characterize `maxTimeoutSeconds), and tell buyers where to read a refusal reason. The same commit's no-node.js change is code, while the remaining new files are Item 2(a) research; they add no separate Item 5 documentation lead.

Source comparison supports the updated guidance: `x402.js` marks this API's `work` optional and includes a supplied `error` in the x402 PaymentRequired object; `server.js` supplies the rejection reason when rebuilding that response; `facilitator.js` separately advertises `work: required` and `workThreshold`. The official x402 v2 specification describes `maxTimeoutSeconds` as the maximum time allowed for payment completion. I could not establish a buyer action from the new timeout wording that would produce a wrong result.

A current unpaid `POST /v1/hash` returned HTTP 402 with `exact` / `nano:mainnet`, `maxTimeoutSeconds: 60`, and `extra.work: optional`. A second POST carrying only a malformed v2 envelope (base64 `PAYMENT-SIGNATURE: eyJ4NDAyVmVyc2lvbiI6Mn0=`, decoded `{"x402Version":2}`) returned HTTP 402. The fresh `PAYMENT-REQUIRED.error` decoded to `x402: payload does not match x402 v2 PaymentPayload schema`, exactly matching the JSON `error`. No valid payment block was supplied; no Nano was spent.

## Outcome and next

No document → current behavior → reproducible wrong-result chain was established for the eligible post-review diff. No report candidate was prepared or sent. Confidence in the no-finding result for this diff: high. Closed `NEXT-ITEM-5-AFTER-010`; `NEXT-ITEM-5-AFTER-011` is planned. Revalidate all state at the next hunt.

**Payout address:** `nano_1zwik4hd1pjy73owfah8xuxzokk6zexc5a6rs6byhrxryggkbh38kemm51yt`

## Previous block 010

The same 2026-09-28 no-node.md edit was examined after the paid 00:17 review. Its refusal-error instruction matched a prior unpaid live probe; timeout phrasing had no actionable wrong-result chain. No candidate was drafted or sent.

## Previous block 009

The paid-reviewed NanoGPT guide was reopened by its 2026-09-18 same-quote warning. Two unpaid live quotes rotated `payTo`, `paymentId`, and `completeUrl`, supporting the new instruction to complete the original quote. Older header wording that differed from current live output predated the paid review and was excluded. No candidate was prepared or sent.
