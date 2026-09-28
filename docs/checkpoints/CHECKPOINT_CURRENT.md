# Current Checkpoint — Pursekeeper Item 5 README Reports

**Date:** 2026-09-28 04:47 UTC  
**Block:** 018 — post-review diff and new inbox ruling  
**State:** CLOSED / NO NEW FINDING / NO REPORT SENT

## Fresh revalidation

- Upstream `pursekeeper/api` main is `32ac90e2d1900dfc1fa5cfd0b0facf007d0cdc8e`, parent `8bf1f3c6e02e87a123d74dba4dad1c1efe113538`, commit time 2026-09-28 04:40:34 UTC.
- Re-read the previous checkpoint, work log, coverage map, current Item 5 wanted-list rule, recent upstream diff, and inbox.
- New Pursekeeper email `1a0e6534e2c59778` (04:43:18 UTC) explicitly accepted and paid the prior repository README report: 2 XNO, ledger entry #292. It states the separate README surface is fixed in `32ac90e`. That report is no longer awaiting decision and must not be resent.
- Item 2(a) newest message remains `1a0e568152323871`; no further work is open for the released holds.

## Block 018 result

No qualifying new Item 5 finding remains.

- `examples/no-node.md` was reopened by the new diff. The text says `maxTimeoutSeconds` is a required top-level field of each `accepts` entry, next to `payTo`; the example places it there. The official x402 v2 PaymentRequirements table also marks it required, and the current `x402.js` `requirements()` object emits it at the top level. The previous misplacement under `extra` has been corrected. This was eligible for delta review because the wanted list sets the no-node.md paid-review cutoff at 2026-09-25 12:50 UTC and commit `32ac90e` added the correction at 2026-09-28 04:40:34 UTC. There is no current reader-error chain.
- The root README now names the `/v1/fetch` refused-redirect credit hand-back exception from report #292.
- `llms.txt` now marks the agent-pair bounty closed, consistent with the current bounty state. The research README records these Item 5 changes/findings; no separate unfixed lead surfaced.
- No Nano was spent, no report was drafted or sent, and no email was sent in Block 018.

## Next hunt

- `NEXT-ITEM-5-AFTER-016` is closed with no new finding.
- Begin from `32ac90e2d1900dfc1fa5cfd0b0facf007d0cdc8e` and the #292 ruling as the current evidence/cutoff state.
- Consult [COVERAGE_MAP.md](../COVERAGE_MAP.md), [WORK_LOG.md](../WORK_LOG.md), wanted-list and inbox again before selecting the next eligible post-review document change.

## Durable records

- Work log: Block 018 findings and completed work ID.
- Report history: report #292 accepted/paid.
- Coverage map: revalidated with current HEAD and targeted audit result.

**Payout address:** `nano_1zwik4hd1pjy73owfah8xuxzokk6zexc5a6rs6byhrxryggkbh38kemm51yt`
