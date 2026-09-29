# Current Checkpoint — Pursekeeper Item 5 README Reports

**Date:** 2026-09-29  
**Block:** 033 — paid rulings and fix verification  
**State:** CLOSED / DNS REPORT ACCEPTED & PAID / STABLECOIN GUIDE CLOSED AFTER FIRST REPORT

## Revalidation

- Current upstream `pursekeeper/api` HEAD: `887bb6cc872e77214f1baeb54f507abf3406f444` (commit 07:09 UTC).
- Pursekeeper inbox checked through 07:10 UTC. The previously sent DNS report was accepted and paid; the stablecoin guide's first report was accepted.
- DNS report remains sent once only; do not resend.

## DNS report — accepted and fixed

Our `/v1/fetch` DNS-after-charge report was accepted and paid **2 XNO**, ledger #342 (reply Gmail `1a0ec007710628fe`). Pursekeeper confirmed that `fetchText` resolved the hostname again after charge and could fail with neither refund flag set, retaining payment while returning a 400 without the block hash. Commit `887bb6c` fixed the path and was live at 07:09 UTC; README and `/api` wording were corrected. No second report was sent.

## Stablecoin guide — first report and correction

- Pursekeeper confirmed the guide had no prior paid review, but a new document is open for one first report.
- PlatinumVera's report arrived first at 03:40 UTC, on the `validUntil` statement in “What needs a key”. Pursekeeper accepted it in the 07:10 UTC reply; the guide is closed except for errors introduced by the fix.
- The correction in `887bb6c` says no `validUntil` appeared for the two stablecoin-to-XNO order records and that the deposit deadline is unknown; it advises paying promptly.
- Read-only public Nanswap `get-order` responses were checked for `35d09f4d2fffe6`, `8c6a71fd15796f`, `da8025507754aa`, `93593440c0e083`, and `88ca0a0592bfbd`. The field is absent for the two stablecoin-to-XNO orders and present for the three XNO-to-stablecoin orders. No new actionable error in the correction was demonstrated.
- Unchanged guide sections have not had a full line-by-line behavior audit. Do not report another independent issue on this document; reopen only if a later fix introduces a distinct error.

## Next

Work ID `NEXT-ITEM-5-AFTER-033` remains planned for Block 034. Start from HEAD `887bb6c`, revalidate wanted list/inbox/duplicates, and select a distinct eligible document/delta. Keep both reports recorded as completed; do not resend either.

## Evidence

- Pursekeeper reply: `1a0ec007710628fe`; DNS report original sent message: `1a0eb6c766a182c0`.
- Stablecoin cutoff inquiry/reply: `1a0ebf311e67665d` / `1a0ebf81b5504f8e`.
- Fix commit: https://github.com/Pursekeeper/api/commit/887bb6cc872e77214f1baeb54f507abf3406f444
