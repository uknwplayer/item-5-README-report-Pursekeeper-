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

The entries below are grounded in the Pursekeeper email replies reviewed on 2026-09-27. Dates are UTC where the reply provides them; otherwise the date is the report/reply date. Payment values are per finding; entries sharing one transfer are marked accordingly.

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
| NEXT-ITEM-5 | Post-review error candidate: research README backdates fixes that public log and Pursekeeper replies place live at 17:42 UTC | **Awaiting decision** | 2026-09-27; upstream revalidated at HEAD `aee28ed7b60365e844ec26edf64877199f1e5d56`; report sent once at 2026-09-27 18:18:19 UTC | Await Pursekeeper’s ruling; do not resend. Email subject: `Item 5 report — research README backdates the 17:42 fixes — uknwplayer`; Gmail message ID `1a0e416e0283ed66` (Message-ID `<CAMonF9B4cyHFS-V-fnj-jySykYmdFRhdAaZcDCA0ZgOHwA6Z5Q@mail.gmail.com>`). Exact report: [sent-report candidate](candidates/ITEM5-2026-09-27-research-readme-fix-time.md). |
| NEXT-ITEM-5-FOLLOWUP | Post-review documentation hunt after paid reviews #279–282; revalidate HEAD, wanted-list status, inbox, diffs, implementation, and duplicates | **Closed, no qualifying finding** | 2026-09-27 18:32–18:47 UTC | Upstream HEAD remains `aee28ed7b60365e844ec26edf64877199f1e5d56`; wanted-list section revalidated; Gmail search after 18:18 UTC found no Pursekeeper reply to report `1a0e416e0283ed66`. See Block 005 checkpoint. Duplicate/rejected leads: README credit exception repeats paid #282; README GPU guarantee repeats paid #279 (and no-node breaker claim was credited to Ops Control HQ, #281); current `no-node.md` matches `server.js`; NanoGPT documented alias remains in official endpoint matrix and our network timeout was inconclusive. No Nano spent, no new report drafted or sent. |
| NEXT-ITEM-5-NEXT | Structural and cross-document Item 5 hunt: headings, table/list scope, wrapped continuations, code examples, links, and document-to-implementation consistency | **In progress** | 2026-09-27 19:01 UTC | Revalidated upstream HEAD `aee28ed7b60365e844ec26edf64877199f1e5d56`; re-read current wanted-list section and checked Gmail (no newer Pursekeeper reply). Inspect only post-review or later-reopened documents; record duplicate and non-actionable leads. |
| NEXT-ITEM-5-FUTURE | Next Item 5 hunt after structural/cross-document pass | **Planned** | 2026-09-27 | Start from revalidated upstream HEAD, latest mailbox, current wanted list, document-specific cutoffs, and the findings recorded in Block 006. |

The 2026-09-27 candidate was sent once to `agent@pursekeeper.dev` at 18:18:19 UTC (15:18:19 America/Sao_Paulo). Gmail confirmed the SENT label, recipient, subject, and Message-ID above. The latest mailbox check at 18:32 UTC found no newer Pursekeeper reply. The report remains awaiting a response; do not infer acceptance or payment from any fix alone.

## Mandatory registration rule

For every future work item:

1. Add a row here **before starting**. Give it a stable work ID, scope, status, start date/time, and next action.
2. As work progresses, update status and link the checkpoint/evidence. Record rejected candidates too, with the reason.
3. Before sending, mark **Awaiting decision**, record the exact email subject and sent timestamp/message reference, and ensure the approved report is the exact version sent.
4. When a reply arrives, change the status to the exact outcome, add payment/ledger or refusal reason, and update the relevant cutoff.
5. Keep the current checkpoint synchronized at the end of the same work block.
6. Never infer a decision or payment from a code fix alone.

Do not delete closed rows. Correct mistakes with a dated note so the history remains auditable.


## Block 005 hunt notes (2026-09-27 18:32–18:47 UTC)

- Revalidated pursekeeper/api default branch main: current HEAD aee28ed7b60365e844ec26edf64877199f1e5d56 (2026-09-27 17:43:24 UTC); wanted-list section in examples/research/README.md re-read; current root README, examples/no-node.md, examples/research/README.md, server code and recent diffs checked. Gmail search found no new message from Pursekeeper after the prior report was sent at 18:18:19 UTC.
- **Duplicate, not resubmitted:** root README x402 sentence still generalizes zero credit; it is the same refused-redirect credit exception accepted as report #282 and fixed in live `/`/`/api` in 97cbf38.
- **Duplicate, not resubmitted:** root README still says paid work is always GPU; this repeats report #279's GPU guarantee finding. examples/no-node.md breaker wording currently matches server.js: only thrown GPU failures (timeout/network/JSON parse) open the 60-second breaker; a valid JSON reply without work falls through without opening it. The breaker wording was credited to Ops Control HQ (#281).
- **Not reproduced / inconclusive:** NanoGPT guide's endpoint alias was not shown broken: the current official endpoint matrix lists `/api/x402/v1/chat/completions`. A no-cost curl reached the proxy but timed out before any response bytes (HTTP 200 headers, curl 28), which is not endpoint-failure evidence.
- **Pending report qualification:** the already-sent research README timing report remains unruled. Its 17:42 comparison conflicts with commit aee28ed7's message stating that times were corrected to the clock (live 17:36:49, paid 17:37–17:38, published 17:39). Keep the exact sent mail unchanged and await Pursekeeper's ruling; do not resend or infer the outcome.


## Block 006 start (2026-09-27 19:01 UTC)

- User approved a deeper hunt focused on document structure and cross-document scope. Revalidated `pursekeeper/api` main HEAD `aee28ed7b60365e844ec26edf64877199f1e5d56` (latest upstream commit timestamp 17:43:24 UTC), re-read the initiative #5 wanted-list section, searched recent Pursekeeper mail, and refreshed this checkpoint.
- The prior research README timing report, sent 18:18:19 UTC (Gmail ID `1a0e416e0283ed66`), remains awaiting a ruling; no newer Pursekeeper mail was found. Do not resend.
- Investigation scope: post-review changes and documents explicitly reopened by later code/text; inspect heading/list/table scope, line wrapping, rendered Markdown, code examples, links, cross-document contradictions, and current endpoint behavior. Do not count editorial-only defects or duplicate paid findings.
