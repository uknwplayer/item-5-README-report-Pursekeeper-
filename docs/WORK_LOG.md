# Work Log — Pursekeeper Item 5

This is the durable register for completed, declined/non-reproduced, active, and future Item 5 work. Each finding gets its own row even when several findings share one email or payment. Never treat an absent reply as acceptance or rejection.

## Status vocabulary

- **Planned** — authorized future work, not started.
- **In progress** — investigation or report preparation is underway.
- **Candidate ready — awaiting operator review** — evidence and draft are recorded; the operator has not yet approved sending.
- **Awaiting decision** — sent once; no ruling yet.
- **Accepted / paid** — Pursekeeper explicitly accepted and states payment/ledger details.
- **Confirmed / credited** — finding confirmed but credited to the operator due to prior report; no payment to this operator.
- **Not reproduced** — recipient could not reproduce the claimed behavior; no payment. Reopen only with new evidence.
- **Declined / duplicate** — explicit refusal, duplicate, or out-of-scope ruling. Record exact reason.
- **Withdrawn** — operator stopped the work before a decision.
- **Closed, no qualifying finding** — investigation ended without a submission.

## Historical register

The entries below are grounded in the Pursekeeper email replies reviewed on 2026-09-27. Dates are UTC where the reply provides them; otherwise the date is the report/reply date. Payment values are per finding; entries sharing a transfer are marked accordingly.

| Date | Work / finding | Document or surface | Status | Payment / evidence |
|---|---|---|---|---|
| 2026-09-24 | Claims-pilot sentence remained after the budget/round was exhausted | Pursekeeper front page | **Accepted / paid** | 2 XNO, ledger 217 |
| 2026-09-24 | ClawHub listing still described as pending after publication | Pursekeeper front page | **Accepted / paid** | 2 XNO, ledger 219; listing sentence corrected |
| 2026-09-25 | No-node limits text omitted the shared GPU budget condition for free work | `examples/no-node.md` | **Accepted / paid** | 2 XNO, ledger 228; cutoff reset to 2026-09-25 12:50 UTC |
| 2026-09-27 | GET `/v1/requests` line split the `/v1/process` continuation | `/api` text | **Accepted / paid** | Part of five-finding batch, 2 XNO; shared transfer ledger 266 |
| 2026-09-27 | MindStudio, Activepieces, and n8n wording was incorrectly grouped in the Hermes parenthetical | Research README | **Accepted / paid** | Part of batch; shared transfer ledger 266 |
| 2026-09-27 | Purchases README did not accurately describe the seller-first `/v1/work` flow | Purchases README | **Accepted / paid** | Part of batch; shared transfer ledger 266 |
| 2026-09-27 | `/sellers` wording excluded parley's documented Nano invoice flow | `/sellers` | **Accepted / paid** | Part of batch; shared transfer ledger 266 |
| 2026-09-27 | `/v1/fetch` manifest omitted the required URL parameter/pre-charge validation behavior | `/v1/fetch` discovery manifest | **Accepted / paid** | Part of batch; shared transfer ledger 266 |
| 2026-09-27 | Two facilitator listings had no seller labels in the stale label file | `/facilitator` | **Accepted / paid** | 2 XNO, ledger 269; corrected by deriving labels from verified listing blocks |
| 2026-09-27 | GitHub API README advertised a closed agent-payment bounty | API repository README | **Accepted / paid** | Part of five accepted findings; shared transfer ledger 275 |
| 2026-09-27 | `/offers` promised an event-triggered purchase without an observable trigger path | `/offers` | **Accepted / paid** | Part of batch; shared transfer ledger 275 |
| 2026-09-27 | `/v1/fetch` redirect handling did not validate each hop before following it | Fetch behavior/docs | **Accepted / paid** | Part of batch; shared transfer ledger 275; redirect handling and per-hop checks changed |
| 2026-09-27 | Concurrent requests could reuse a fresh X-Nano-Payment credit during an await window | Payment-credit implementation | **Accepted / paid** | Part of batch; shared transfer ledger 275; per-hash lock added |
| 2026-09-27 | `/v1/hash` could charge before rejecting a request body over 1 MB | Hash endpoint behavior | **Accepted / paid** | Part of batch; shared transfer ledger 275; body read/limit check moved before charge |
| 2026-09-27 | `checked_at` appeared older than seller verification records | `/sellers.json` | **Not reproduced** | No payment. Pursekeeper reported probe rounds every ten minutes and requested response headers if the stale value is observed again. Reopen only with such evidence. |
| 2026-09-27 | Paid-work wording promised unlimited work always from GPU | `examples/no-node.md` | **Accepted / paid** | 2 XNO, ledger 279; phrase traced to 2026-09-25 correction |
| 2026-09-27 | Manifest was gzipped even with `Accept-Encoding: gzip;q=0` | API README / x402 manifest | **Confirmed / credited** | No payment to uknwplayer: Ops Control HQ reported it first. Fixed in commit `96893d9`; uknwplayer credited by name. |
| 2026-09-27 | GPU breaker sentence overstated which failures open the breaker | `examples/no-node.md` | **Confirmed / credited** | No payment to uknwplayer: Ops Control HQ reported it 31 minutes earlier and received ledger 281. Rewritten in `97cbf38`; user credited by name. |
| 2026-09-27 | x402 text said payment blocks cannot be reused as credit, omitting refused-redirect recovery | Pursekeeper front page and `/api` x402 text | **Accepted / paid** | 2 XNO, ledger 282; corrected in `97cbf38`, live on `/` and `/api` |

## Future and active work

| Work ID | Scope / question | Status | Started | Next action |
|---|---|---|---|---|
| NEXT-ITEM-5 | Post-review error candidate: research README backdates fixes that public log and Pursekeeper replies place live at 17:42 UTC | **Candidate ready — awaiting operator review** | 2026-09-27; upstream revalidated at HEAD `aee28ed7b60365e844ec26edf64877199f1e5d56` | Review [candidate draft](candidates/ITEM5-2026-09-27-research-readme-fix-time.md). It has not been emailed. If approved with “Enviar”, send this exact version once; otherwise revise or close it with the reason. |
| NEXT-ITEM-5-FOLLOWUP | Continue Item 5 after this candidate’s decision; revalidate latest upstream HEAD, wanted list, mailbox, duplicate reports, and applicable per-document cutoff | **Planned** | Not started | Start after the candidate is approved, declined, or withdrawn; use any accepted/fix commit as the new cutoff for that document. |

The mailbox and public log were rechecked during the 2026-09-27 hunt. The candidate remains operator-review-only; no outgoing email was sent.

## Mandatory registration rule

For every future work item:

1. Add a row here **before starting**. Give it a stable work ID, scope, status, start date/time, and next action.
2. As work progresses, update status and link the checkpoint/evidence. Record rejected candidates too, with the reason.
3. Before sending, mark **Awaiting decision**, record the exact email subject and sent timestamp/message reference, and ensure the approved report is the exact version sent.
4. When a reply arrives, change the status to the exact outcome, add payment/ledger or refusal reason, and update the relevant cutoff.
5. Keep the current checkpoint synchronized at the end of the same work block.
6. Never infer a decision or payment from a code fix alone.

Do not delete closed rows. Correct mistakes with a dated note so the history remains auditable.
