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
| NEXT-ITEM-5 | Post-review discrepancy: research README versus decision 459 / mail on 17:36:49 vs 17:42 | **Accepted / paid (claim framing incorrect; underlying cross-surface contradiction confirmed)** | 2026-09-27; report sent 18:18:19 UTC | Pursekeeper replied 20:01:08 UTC: README was accurate; decision 459 and earlier mails carried the wrong time. Paid 1 XNO, ledger #285, for documenting a real cross-surface contradiction despite the report's claim failing. Original mail remains unchanged. Latest commit dd419256bd5a741887d680fa801bdcf9b5035a93 adds a correction note. |
| NEXT-ITEM-5-FOLLOWUP | Post-review documentation hunt after paid reviews #279–282; revalidate HEAD, wanted-list status, inbox, diffs, implementation, and duplicates | **Closed, no qualifying finding** | 2026-09-27 18:32–18:47 UTC | Upstream HEAD remains `aee28ed7b60365e844ec26edf64877199f1e5d56`; wanted-list section revalidated; Gmail search after 18:18 UTC found no Pursekeeper reply to report `1a0e416e0283ed66`. See Block 005 checkpoint. Duplicate/rejected leads: README credit exception repeats paid #282; README GPU guarantee repeats paid #279 (and no-node breaker claim was credited to Ops Control HQ, #281); current `no-node.md` matches `server.js`; NanoGPT documented alias remains in official endpoint matrix and our network timeout was inconclusive. No Nano spent, no new report drafted or sent. |
| NEXT-ITEM-5-NEXT | Structural and cross-document Item 5 hunt: headings, table/list scope, wrapped continuations, code examples, links, and document-to-implementation consistency | **Closed, no qualifying finding** | 2026-09-27 19:01–19:10 UTC | GitHub-rendered README links verified; current rows parsed; facilitator 32,001- and 320,001-byte probes returned HTTP 400. The sole malformed table row predates the README's 2026-09-27 08:00 paid review, was unchanged after it, and did not show a clear wrong-action consequence. No email sent. See Block 006 checkpoint. |
| NEXT-ITEM-5-FUTURE | Post-reply, post-fix Item 5 hunt following commit dd419256 | **Closed, no qualifying finding** | 2026-09-27 17:21–17:27 America/Sao_Paulo | Reviewed every changed surface and compared docs with implementation, official exact scheme and free live 402; no action-causing mismatch. See Block 007. |

The 2026-09-27 candidate was sent once to `agent@pursekeeper.dev` at 18:18:19 UTC (15:18:19 America/Sao_Paulo). Gmail confirmed the SENT label, recipient, subject, and Message-ID above. Pursekeeper ruled at 20:01:08 UTC: the report's claim that the README backdated the fixes was wrong; decision 459 and prior mails had the wrong time. The cross-surface contradiction was confirmed and paid at 1 XNO, ledger #285. Do not resend the report or treat its framing as accepted.

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


## Block 006 findings (2026-09-27 19:01–19:10 UTC)

- **Rendered links checked:** GitHub's rendered `examples/research/README.md` resolves links written as `/examples/...` to repository files. The target files exist; the relative-link scan's initial false positives came from treating repository-root links as paths relative to the README directory.
- **Structural lead rejected:** one 2026-09-16 ShaXiaozhu row in the research index has four cells under a five-column header: its report link renders in the `paid` column and the `file` column is empty, while the amount text remains in the subject. This row predates the README's latest paid Item 5 review (08:00 UTC on 2026-09-27), was not changed by later fixes, and its possible reader consequence is not clear enough for a report. The current commits' newer rows have five cells.
- **Facilitator boundary lead rejected:** unauthenticated POST probes with 32,001-byte and 320,001-byte bodies to `/verify` both returned HTTP 400 and a 49-byte error response, without reaching payment verification; this matches the documented 32,000-byte rejection for the tested values. No Nano was spent.
- Reviewed recent structure changes in `examples/no-node.md`, `examples/research/README.md`, server `DOCS`, facilitator docs, NanoGPT guide and root README. The latest changes did not expose another distinct, post-cutoff structural or cross-document error with a reproducible wrong-action result.
- At Block 006's close there had been no reply yet and the timing report was then pending. Pursekeeper ruled at 20:01 UTC in email `1a0e4753adf9dbc7`: README was correct; decision 459 and earlier emails were wrong; paid Ӿ1 under ledger #285 for the cross-surface contradiction despite the report's incorrect framing.


## Block 007 start (2026-09-27 20:21 UTC)

- User started the next Item 5 hunt. Before investigating documentation changes, revalidated the inbox and found Pursekeeper's reply to report 1a0e416e0283ed66: on 2026-09-27 20:01:08 UTC they said the research README was correct, decision 459 and earlier mails were wrong about 17:42, and paid 1 XNO under ledger #285 because the cross-surface contradiction was real despite the report framing being wrong.
- Public upstream pursekeeper/api main HEAD advanced to dd419256bd5a741887d680fa801bdcf9b5035a93 (2026-09-27 20:00:11 UTC), parent aee28ed7b60365e844ec26edf64877199f1e5d56. Commit message says it adds the wrong-17:42 correction to the README and includes new no-node.md / no-node.js changes; inspect only changes after applicable paid review/fix cutoffs.
- Next: read the full diff, current wanted list and docs; compare changed instructions with implementation/live behavior; check prior rulings and reports before drafting. No report sent for this block.


## Block 007 findings (2026-09-27 20:21–20:27 UTC)

- **New reply and cutoff:** Pursekeeper's 20:01:08 UTC email (Gmail `1a0e4753adf9dbc7`) said the research README was correct about 17:36:49 UTC; decision 459 and earlier mails were wrong. The reported contradiction was confirmed as real and paid 1 XNO, ledger #285, even though the report's main claim failed. The README note added in `dd419256` accurately identifies the wrong public figure and the service log time.
- **Cutoff/HEAD:** Revalidated main HEAD `dd419256bd5a741887d680fa801bdcf9b5035a93` (2026-09-27 20:00:11 UTC), parent `aee28ed7b60365e844ec26edf64877199f1e5d56`. Search after the work confirmed no later commit or Pursekeeper reply.
- **`examples/no-node.md` x402 paragraph:** compared the post-20:00 text with the exact scheme source in `x402nano/schemes/exact.md`, current `x402.js`, and live response. Unpaid `POST /v1/hash` with `{}` returned 402; decoded `PAYMENT-REQUIRED` header was x402 v2, exact/nano:mainnet, amount `1000000000000000000000000000`, matching `payTo` and `extra.work: optional` in the guide. Its `PAYMENT-SIGNATURE` structure (`accepted`, `payload.block`) matches both scheme and example client. No Nano was spent.
- **`server.js` public `/api` text:** new broadened redirect hand-back cases were compared with `fetchText` and the 400 handler; the listed missing-Location, rejected-next-target and hop-limit cases match the code's refusal paths and hash-credit recovery description. Existing paid #282 is duplicate/context, not reopened as a fresh lead absent a new mismatch.
- **Research README postscript:** checked the live Speedbot collaboration guide and `/api/launch`; `directed_test` specifies one rewarded test per operator and wallet, up to six funded runs per service, a 72-hour provider window, and no approval/reservation on submission. The postscript's operational summary matches the live object.
- **`examples/no-node.js`:** reviewed the commit patch plus current retry flow; subtype follows the rebuilt block after refresh, and receive retry checks that the send remains receivable before rebroadcast. The adjacent docs claim that these script fixes are in place accurately.
- **Duplicates:** the targeted API issue search found no Item 5 issue for the 17:42 contradiction or the x402 instructions; prior paid/credited entries in the research register were checked. No actionable post-cutoff documentation error reproduced; no candidate prepared or sent; no Nano spent.
- Closed `NEXT-ITEM-5-FUTURE`; created `NEXT-ITEM-5-AFTER-007` as planned for the next explicitly requested hunt.


## Block 008 start (2026-09-27 20:41 UTC)

- User requested the next Item 5 hunt. Revalidated upstream main: latest visible commit remains `dd419256bd5a741887d680fa801bdcf9b5035a93` (2026-09-27 20:00:11 UTC). Re-read the current work log/checkpoint and checked Gmail after 2026-09-27; latest Pursekeeper mail remains the 20:01:08 UTC ruling on report `1a0e416e0283ed66`, paid Ӿ1, ledger #285. No newer reply surfaced.
- Current pass begins by refreshing the wanted-list rules and reviewing only eligible documentation changed after the relevant paid review/fix cutoff. Compare exact commit diffs with source/current behavior, public JSON and external official docs as needed; verify consequences and duplicates. No report is authorized for sending without operator review.


## Block 008 findings (2026-09-27 20:41–20:48 UTC)

- **Revalidation:** upstream main remained at `dd419256bd5a741887d680fa801bdcf9b5035a93`; no later commit or Pursekeeper reply was found. Re-read the Item 5 wanted-list rules and prior paid/credited findings. Public `/log.json` now contains decision #463, correcting #459's 17:42 time; ledger #285's note and README correction are consistent.
- **Changed-file inventory:** GitHub API listed `examples/no-node.js`, `examples/no-node.md`, the Copperglass QA research report, `examples/research/README.md`, and `server.js`. Reviewed the post-20:00 diff for all five paths. The updated Copperglass postscript matches the current Speedbot collaboration guide and `/api/launch` JSON (one directed-test reward per operator and wallet; six funded runs per service; 72-hour provider window; submission alone neither approves nor reserves a reward).
- **`server.js` / `/api`:** live unauthenticated GET `/api` returned 200 and contains the new hand-back description. The `fetchText` redirect loop permits five hops and refuses a sixth; missing Location and disallowed next URL are also refused before fetching the new host. The 400 handler places credit on the paid block hash and includes the retry hash as documented. No new mismatch; #282 is a duplicate historical context.
- **`examples/no-node.md`:** live unauthenticated GET `/examples/no-node.md` returns 200 with the x402 v2 example. Its server example's key terms match the no-cost live 402 from POST `/v1/hash` and the official Nano `exact` scheme; no payment was sent.
- **`examples/no-node.js`:** compared the modified retry path with the prose identifying the new fixes; open/receive subtype is derived from each rebuilt block and a pending receive is re-checked after refresh. No documentation claim contradicted the implementation.
- **Research README:** inspected its new Item 5 ruling rows and updated chronology. Decision #463 now documents the earlier public-time contradiction; the ledger, README note and decision agree. No actionable structural or factual mismatch found.
- **Duplicate checks:** targeted issue search for `17:42` returned no related Item 5 issue; x402 search hits were existing general seller discussions, not reports of this exact post-cutoff text. All paid #279/#282 and #284 scopes were excluded as duplicates.
- **Outcome:** no qualifying error meeting the document -> current behavior -> reproducible wrong-action chain. No candidate prepared or sent; no Nano spent. Closed `NEXT-ITEM-5-AFTER-007`; created `NEXT-ITEM-5-AFTER-008` as planned.
