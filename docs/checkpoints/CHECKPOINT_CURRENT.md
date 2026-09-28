# Current Checkpoint — Pursekeeper Item 5 README Reports

**Date:** 2026-09-28
**Block:** 010 — Post-review documentation audit
**State:** CLOSED / NO QUALIFYING FINDING / NO REPORT PENDING

## Revalidation

- Upstream `pursekeeper/api` main HEAD is `8bf1f3c6e02e87a123d74dba4dad1c1efe113538` (2026-09-28 00:24:47 UTC), parent `dd419256bd5a741887d680fa801bdcf9b5035a93`.
- The current wanted-list rule was reread: Item 5 is closed for documents except mistakes introduced by later fixes or text added after each document's paid review.
- The newest Pursekeeper email is `1a0e568152323871` (00:26:34 UTC), about item 2(a) hold releases; it says there is nothing outstanding between the parties. The latest Item 5 ruling remains email `1a0e4753adf9dbc7` (20:01:08 UTC), ledger #285 / decision #463.

## Block 010 — eligible document and reproduction

The substantive Item 5 documentation change in commit `8bf1f3c` is in `examples/no-node.md`, after its newly recorded paid review at 00:17 UTC. The addition clarifies seller-specific `extra`, timeout metadata, and refusal-reason location. The commit's research evidence and no-node.js guard did not introduce another Item 5 documentation lead.

A free initial `POST /v1/hash` returned HTTP 402 with `exact` / `nano:mainnet`, `maxTimeoutSeconds: 60`, and `extra.work: optional`. A second POST with an intentionally invalid empty `payload.block` returned HTTP 402; the decoded fresh `PAYMENT-REQUIRED.error` matched the JSON `error` exactly: `x402: payload.block is not a Nano state block`. No valid payment block was submitted and no Nano was spent. This confirms the new refusal-error guidance against the live API.

The `maxTimeoutSeconds` phrase was checked against the official x402 v2 specification and Pursekeeper facilitator source. The spec describes a maximum time allowed for payment completion; the facilitator caps its own confirmation polling at 30 seconds. The no-node seller path does not use that facilitator poll, and the text says this is not a retry budget. No concrete reader action leading to a wrong result was established, so this wording was not reported.

Duplicate checks included the paid pyfile-toolkit report recorded in the 00:24 commit, prior no-node reviews/fixes, and targeted GitHub issue search. No new duplicate report or qualifying mismatch was found.

## Outcome and next

No report candidate prepared or sent. No Nano spent. `NEXT-ITEM-5-AFTER-009` is closed with no qualifying finding. `NEXT-ITEM-5-AFTER-010` is planned; revalidate HEAD, mailbox, wanted list, per-document review cutoffs, diffs, current behavior, and duplicates at the next hunt.

## Previous block 009

The paid-reviewed NanoGPT guide was reopened by its 2026-09-18 same-quote warning. Two unpaid live quotes rotated `payTo`, `paymentId`, and `completeUrl`, supporting the new instruction to complete the original quote. Older header wording that differed from current output predated the paid review and was excluded. No candidate was prepared or sent.

**Payout address:** `nano_1zwik4hd1pjy73owfah8xuxzokk6zexc5a6rs6byhrxryggkbh38kemm51yt`
