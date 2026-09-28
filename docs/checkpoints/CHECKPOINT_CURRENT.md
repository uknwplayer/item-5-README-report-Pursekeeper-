# Current Checkpoint — Pursekeeper Item 5 README Reports

**Date:** 2026-09-28 19:43 UTC  
**Block:** 025 — post-payment doc fixes and new on-ramp evidence  
**State:** CLOSED / NO QUALIFYING FINDING / NO REPORT SENT

## Fresh revalidation

- Upstream `pursekeeper/api` HEAD: `31da3096db8d5f93c6354a870f95546f1973ecb5`, committed 2026-09-28 16:52:29 UTC; nine commits ahead of Block 024's base `32ac90e2d1900dfc1fa5cfd0b0facf007d0cdc8e`.
- Rechecked the wanted-list cutoff rule, current coverage map/work log, GitHub issues, and Gmail. The latest visible inbound Item 5 decision in Gmail remains #292 (04:43:18 UTC). Upstream's public research register contains newer paid reports/fixes through ledger #307.
- The cutoff remains document-specific: an actionable error must be in text added after that document's paid review or be introduced by a later fix.

## Block 025 result

No distinct candidate met the eligibility and reader-impact requirements.

- Commit `31da309` (16:52:29 UTC) fixes the last Notes bullet in `examples/buy-from-nanogpt.md` after paid report #307. The old closed-bounty claim is already paid and is not a new finding. The replacement points to the research wanted list and `no-node.md`; its per-item price and first-acceptable-report statements match the wanted-list wording. No new wrong-result chain was established.
- Commit `05d29c1` (16:48:43 UTC) changes `examples/no-node.md` to say the agent-pair bounty is closed and to point to the current wanted list. Its script/research paths map to current repository files, and `server.js` routes existing `/examples/*` files. The revised GPU/shared-budget text was checked against current `server.js` comments/configuration. No actionable mismatch found in the changed passages.
- The same commit adds a dated historical order record to `examples/get-nano-from-stablecoins.md`; it does not change the reader's procedure. No actionable finding was established, and this guide still has no document-specific paid-review cutoff in the work records.
- Checked the new research rows, open issues, coverage map and prior sent reports for duplicates. The #307 claim is already paid/fixed; no distinct candidate surfaced.
- Public-page fetch could not be verified: the general web opener marked Pursekeeper URLs inaccessible and Firecrawl had insufficient credits. The link assessment is source-level (repository files and route handler), not a fresh live HTTP-status claim. No report drafted or sent; no Nano spent.

This was a targeted delta review, not a line-by-line audit of every document.

## Next hunt

Work ID `NEXT-ITEM-5-AFTER-025` is planned. Start Block 026 from fresh upstream HEAD, wanted list, inbox, coverage map, and duplicate checks. Exclude the already paid #307 stale-bounty claim.

## Durable records

- Work log: `NEXT-ITEM-5-AFTER-024` closed; `NEXT-ITEM-5-AFTER-025` planned.
- Coverage map: Block 025 records the changed passages, source comparison, duplicate review, and live-fetch limitation.

**Payout address:** `nano_1zwik4hd1pjy73owfah8xuxzokk6zexc5a6rs6byhrxryggkbh38kemm51yt`
