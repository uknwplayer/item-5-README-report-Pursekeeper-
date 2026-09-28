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
| NEXT-ITEM-5-AFTER-007 | Post-block-007 Item 5 hunt: find distinct post-review actionable doc errors | **Closed, no qualifying finding** | 2026-09-27 17:41–17:48 America/Sao_Paulo | Revalidated latest commit/inbox and inspected all paths in dd419256; checked docs against code, official scheme and live responses. No reproducible wrong-action mismatch. See Block 008. |
| NEXT-ITEM-5-AFTER-008 | Next Item 5 hunt after block 008 | **Closed, no qualifying finding** | 2026-09-27 20:08–20:16 America/Sao_Paulo | Inspected the post-review 2026-09-18 buy-from-nanogpt.md edit and tested two unpaid live quotes. The added instruction not to re-quote before completing the same payment is supported by rotating quote data; header details that differ from current live output predate the 2026-09-10 paid review and were excluded. No report drafted or sent; no Nano spent. See Block 009. |

| NEXT-ITEM-5-AFTER-009 | Post-block-009 Item 5 hunt: audit new post-review document diffs and actionable consequences | **Closed, no qualifying finding** | 2026-09-27 22:30–22:42 America/Sao_Paulo | Inspected the post-review 2026-09-28 no-node.md changes in 8bf1f3c, compared them with source and free live 402/retry responses, and checked the wanted list, new email and issues. The new payment-error instruction matched the live response; timeout wording did not yield an actionable wrong-result chain. No report; no Nano spent. See Block 010. |

| NEXT-ITEM-5-AFTER-010 | Post-block-010 Item 5 hunt: revalidate and inspect new post-review documentation/fix diffs | **Closed, no qualifying finding** | 2026-09-28 01:49–01:54 UTC | Revalidated HEAD `8bf1f3c6e02e87a123d74dba4dad1c1efe113538`, wanted-list closure rule, full newest email, the 00:17 review/00:24 doc diff, current source/live 402 behavior, and duplicate issues. The new no-node.md error-location guidance matched both PAYMENT-REQUIRED.error and JSON error on an intentionally invalid unpaid retry; seller-specific work metadata matched source. Timeout language produced no actionable wrong result. No report or Nano spend. See Block 011. |
| NEXT-ITEM-5-AFTER-011 | Post-block-011 Item 5 hunt: revalidate and inspect new post-review document/fix diffs | **Closed, no qualifying finding** | 2026-09-28 02:04–02:12 UTC | Inspected the reopened `/api` prose in `server.js` changed by `dd419256` after the paid #284 review. A malformed redirect `Location` also enters the credit-return branch, but the broad sentence covers redirects that cannot be followed and the 400 note names the hash; no wrong-result chain for a reader following the docs was established without spending XNO. The post-review no-node.md changes were already checked in Block 011. No report or Nano spend. See Block 012. |
| NEXT-ITEM-5-AFTER-012 | Post-block-012 Item 5 hunt: revalidate and inspect post-review docs/fixes and live behavior | **Planned** | — | Revalidate upstream HEAD, inbox, wanted-list status, document-specific paid-review cutoffs, recent diffs, current behavior, duplicates, and issues before investigating. |
| NEXT-ITEM-5-AFTER-014 | Next post-review Item 5 hunt using the living coverage map; revalidate state and select an eligible open/reopened surface | **Closed, no qualifying finding** | 2026-09-28 04:19 UTC | Latest eligible no-node.md diff was already audited in Blocks 010–011. Open surfaces checked for cutoff/change history; stablecoin guide's own paid-review cutoff is unresolved and no later file diff exists. See Block 016. |
| NEXT-ITEM-5-AFTER-015 | Next Item 5 hunt guided by Block 016 coverage map | **Closed, no qualifying finding** | 2026-09-28 04:32 UTC | Revalidated upstream, wanted list, inbox, and live public docs. No changed eligible commit; live-only strategy/landscape leads lack a page-specific paid-review cutoff/versioned diff or clear wrong-result consequence. See Block 017. |
| NEXT-ITEM-5-AFTER-016 | Next Item 5 hunt after live-page coverage check | **Closed, no qualifying finding** | 2026-09-28 04:38–04:47 UTC | Revalidated checkpoint/coverage map, upstream HEAD and diffs, current wanted-list rule, and Pursekeeper mail. New HEAD `32ac90e2d1900dfc1fa5cfd0b0facf007d0cdc8e` (04:40:34 UTC) corrected the post-review `no-node.md` `maxTimeoutSeconds` placement; x402 v2 requires it at the top level and current `x402.js` emits it there. The README hand-back finding was confirmed and paid as ledger #292 at 04:43:18 UTC and fixed in the same commit. `llms.txt` now correctly marks the bounty closed. No current doc-to-behavior error remained; no new report or Nano spend. See Block 018 checkpoint. |
| NEXT-ITEM-5-AFTER-018 | Next Item 5 hunt after Block 018; delta review from current HEAD | **Closed, no qualifying finding** | 2026-09-28 05:09–05:10 UTC | Revalidated the current main HEAD, wanted-list changes, recent Pursekeeper inbox, and the coverage crosswalk. HEAD remains `32ac90e2d1900dfc1fa5cfd0b0facf007d0cdc8e`; no later commit or new Item 5 ruling appeared. The remaining mapped leads have no new post-cutoff diff: buy-from-nanogpt was already checked through its 2026-09-18 edit; BOUNTY has no later path change and no confirmed candidate-specific cutoff; the stablecoin guide lacks its own paid-review cutoff; live strategy/landscape still lack versioned source. No report or Nano spend. See Block 019 checkpoint. |
| NEXT-ITEM-5-AFTER-019 | Next Item 5 hunt after Block 019; verify current delta and cutoff-driven leads | **Closed, no qualifying finding** | 2026-09-28 05:13–05:14 UTC | Fresh HEAD remains `32ac90e2d1900dfc1fa5cfd0b0facf007d0cdc8e`; current wanted-list rule is unchanged, and inbox has no newer ruling than report #292. Reused the per-document crosswalk: no new eligible diff since Block 018; the latest changed docs were already audited. Remaining open areas retain documented cutoff/provenance blockers. No report or Nano spend. See Block 020 checkpoint. |
| NEXT-ITEM-5-AFTER-020 | Hunt Item 5 surfaces without a dedicated prior audit | **Closed, no qualifying finding** | 2026-09-28 05:19 UTC–05:31 UTC | Checked BOUNTY.md, the stablecoin guide, parent/individual purchase READMEs, cutoff records, path histories, wanted list, GitHub issues, and Pursekeeper inbox; no eligible distinct post-cutoff error. Block 021. |

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


## Block 009 start (2026-09-27 23:08 UTC)

- User requested the next Item 5 hunt. Revalidated public pursekeeper/api main: latest commit remains dd419256bd5a741887d680fa801bdcf9b5035a93. No Pursekeeper mail newer than 20:01:08 UTC was returned by Gmail search. The current checkpoint is Block 008; its previous report is settled at 1 XNO, ledger #285, with decision #463 live.
- Re-read the current hunt register; next investigation refreshes the wanted-list conditions and audits per-file paid-review/fix cutoffs, then checks only eligible document diffs against implementation/live behavior and duplicates. No report is authorized to send without presenting it to the operator first.


## Block 009 findings (2026-09-27 23:08–23:16 UTC)

- **Revalidation:** pursekeeper/api main remains at HEAD dd419256bd5a741887d680fa801bdcf9b5035a93 (latest commit timestamp 20:00:11 UTC). The current Item 5 wanted-list section was reread. Gmail search found no message newer than Pursekeeper's 20:01:08 UTC reply (email 1a0e4753adf9dbc7, ledger #285 / decision #463). The public issue search found no matching current guide defect; issue #2 is an earlier unrelated paid-review enquiry.
- **Eligible document and cutoff:** examples/buy-from-nanogpt.md was changed after its paid 2026-09-10 QA review in commits 432f34fab3588c7e2da330b327638da77133f538 (2026-09-18 12:06:03 UTC) and ca195622fe2be75adfce3039198b45b8e06d7b1f (2026-09-18 16:20:21 UTC). The 12:06 diff adds the single-use / same-quote warning; the 16:20 diff only adds a link to the evidence gist. The paid review itself did not test purchase-dependent completion, so the newly added note was checked against the cited report and current unpaid quote responses.
- **Live reproduction, no payment:** two consecutive unpaid POSTs to https://nano-gpt.com/api/x402/v1/chat/completions with x-x402: nano each returned HTTP 402 and a Nano accepted rail. payTo, paymentId, and completeUrl differed between the two quotes. This supports following the new instruction to preserve the first quote and complete its matching payment ID/URL; no send or Nano spend was performed.
- **Duplicate/provenance check:** the 2026-09-18 pyfile-toolkit gist linked by the new text documents the same rotating quote and quote-bound completion behavior. The current newly added instruction matches that firsthand report, so it is not a new mismatch to report. The guide's older prose about X-Payment-Address, X-Payment-Amount, and X-Payment-Id does not match the headers from today's live response, but that prose predates the 2026-09-10 paid review and was not introduced by either post-review diff; excluded under the timing rule.
- **Outcome:** no qualifying post-review documentation error found in this reopened document. No candidate drafted or sent; no Nano spent. Closed NEXT-ITEM-5-AFTER-008 and registered NEXT-ITEM-5-AFTER-009 as planned.


## Block 010 start (2026-09-27 22:30 America/Sao_Paulo / 2026-09-28 01:30 UTC)

- User requested the next hunt. Revalidated `pursekeeper/api` main: new HEAD `8bf1f3c6e02e87a123d74dba4dad1c1efe113538` at 2026-09-28 00:24:47 UTC, following `dd419256`. Re-read the current wanted-list register; searched Gmail after 2026-09-27 and found a new Pursekeeper message at 00:26:34 UTC (`1a0e568152323871`) concerning released item 2(a) holds, plus the prior Item 5 ruling at 20:01:08 UTC. Full new message to read before proceeding.
- `NEXT-ITEM-5-AFTER-009` is now in progress. Scope: diff and inspect only documentation errors introduced after relevant paid-review/fix cutoffs; compare the new commit's documents to actual code/current public behavior, and check duplicates/issues before deciding whether a report exists.

## Block 010 findings (2026-09-27 22:30–22:42 America/Sao_Paulo / 2026-09-28 01:30–01:42 UTC)

- **Revalidation:** upstream main HEAD is `8bf1f3c6e02e87a123d74dba4dad1c1efe113538` (2026-09-28 00:24:47 UTC), parent `dd419256bd5a741887d680fa801bdcf9b5035a93`. The current wanted-list rule was read: Item 5 is closed for documents except mistakes introduced by later fixes or text added after the document's paid review. The newest Pursekeeper email is `1a0e568152323871` at 00:26:34 UTC about item 2(a) hold releases; it says nothing is outstanding for Item 5. The earlier Item 5 ruling remains email `1a0e4753adf9dbc7`, 20:01:08 UTC, ledger #285 / decision #463.
- **Eligible diff and cutoff:** the substantive new Item 5 text is in `examples/no-node.md`, added by commit `8bf1f3c` at 00:24:47 UTC after the newly noted paid review at 00:17 UTC. Its additions clarify seller-specific `extra` metadata, `maxTimeoutSeconds`, and refusal error delivery; the final review-history sentence records that paid correction. Other commit paths are item 2(a) research evidence, or a code-only no-node.js guard, and supplied no separate Item 5 documentation lead.
- **Cheap live check:** an unpaid POST to `https://pursekeeper.dev/v1/hash` returned HTTP 402 with `scheme: exact`, `network: nano:mainnet`, `maxTimeoutSeconds: 60`, and `extra.work: optional`. Retrying with a base64 `PAYMENT-SIGNATURE` whose `payload.block` was empty returned HTTP 402; the decoded fresh `PAYMENT-REQUIRED.error` and JSON body `error` were both `x402: payload.block is not a Nano state block`. The invalid block could not spend Nano. This confirms the added error-location instruction for the documented API and the example's live `extra` value.
- **Timeout lead checked, not reported:** the new phrase calls `maxTimeoutSeconds` a facilitator confirmation window. The official x402 v2 spec calls it the maximum time allowed for payment completion; Pursekeeper's facilitator implementation caps its own polling at 30 seconds even when requirements say 60. The no-node recipe's direct seller path does not use that facilitator confirmation poll, and the text says the field is not a retry budget. No reproducible buyer action and wrong result were established, so this wording did not meet the reporting bar.
- **Duplicates and outcome:** the 00:24 commit attributes the wording correction to pyfile-toolkit's 00:17 Item 5 review; the current text follows that report. Targeted issue search found no matching newly introduced no-node finding. Existing accepted/credited no-node findings and the 09-10 review were checked for scope/cutoff. No post-review error produced a clear document → implementation → wrong result chain. No candidate prepared or sent; no Nano spent. Closed `NEXT-ITEM-5-AFTER-009`; registered `NEXT-ITEM-5-AFTER-010` as planned.


## Block 011 findings (2026-09-28 01:49–01:54 UTC)

- **Revalidation:** upstream `pursekeeper/api` main is still `8bf1f3c6e02e87a123d74dba4dad1c1efe113538` (00:24:47 UTC), parent `dd419256bd5a741887d680fa801bdcf9b5035a93`. The wanted list still closes Item 5 documents except errors introduced by later fixes or text after the paid review. The newest Pursekeeper email, read in full, is `1a0e568152323871` at 00:26:34 UTC: it only records three released Item 2(a) holds and says nothing else is outstanding. The last Item 5 ruling remains ledger #285 / decision #463.
- **Eligible diff and cutoff:** the only newly actionable Item 5 documentation diff after a paid review is `examples/no-node.md`: pyfile-toolkit's review was recorded at 00:17 UTC and commit `8bf1f3c` added the new seller-specific `extra` and refusal-error guidance at 00:24:47 UTC. The other commit paths are a no-node.js guard and Item 2(a) evidence/records. The research README's entry describes this same reviewed/fixed report; no separate actionable instruction was introduced there.
- **Source and protocol comparison:** `x402.js` builds this API's `extra.work: optional` and defines the `error` member in `PaymentRequired`; `server.js` derives a refusal hint from the verification result and passes it to that builder; `facilitator.js` advertises `work: required` plus `workThreshold`. That supports the new direction to read `extra` from the seller's own 402. The official x402 v2 specification defines `maxTimeoutSeconds` as the maximum time allowed for payment completion; the wording did not produce a concrete wrong buyer action.
- **Current reproduction, no payment:** an unpaid `POST /v1/hash` returned HTTP 402 with `exact`, `nano:mainnet`, `maxTimeoutSeconds: 60`, and `extra.work: optional`. A retry with base64 `PAYMENT-SIGNATURE: eyJ4NDAyVmVyc2lvbiI6Mn0=` (only `{"x402Version":2}`, no payment block) was rejected with HTTP 402. Its fresh `PAYMENT-REQUIRED.error` decoded to `x402: payload does not match x402 v2 PaymentPayload schema`, identical to the JSON `error`. No valid block was supplied and no Nano was spent.
- **Duplicate and outcome:** issue search returned only old issue #2, an unrelated 2026-09-10 paid-review enquiry about separating payment flows; it is not the new metadata/error-location claims. Commit `8bf1f3c` attributes these clarifications to pyfile-toolkit's 00:17 paid review. Prior paid/credited no-node findings were checked; none duplicates a new defect because no such defect reproduced. No candidate prepared or sent. Confidence in the no-finding conclusion: high for this eligible diff. Closed `NEXT-ITEM-5-AFTER-010`; registered `NEXT-ITEM-5-AFTER-011` as planned.


## Block 012 findings (2026-09-28 02:04–02:12 UTC)

- **Revalidation:** upstream `pursekeeper/api` main remains `8bf1f3c6e02e87a123d74dba4dad1c1efe113538` (2026-09-28 00:24:47 UTC). The newest Pursekeeper email remains `1a0e568152323871` at 00:26:34 UTC; its full text records only Item 2(a) hold releases. Wanted-list rule remains: Item 5 is closed except errors introduced by later fixes or text after a paid review.
- **Eligible document inspected:** `server.js`'s live `/api` documentation was revised in commit `dd419256bd5a741887d680fa801bdcf9b5035a93` (2026-09-27 20:00:11 UTC), following Ops Control HQ's paid #284 review, whose report window is recorded as 18:35–19:43 UTC and whose fix was live at 19:58:56 UTC. The same current text is served at `https://pursekeeper.dev/api` and remains present at current HEAD.
- **Potential omission traced, not reported:** the new parenthetical enumerates a refused address check, absent `Location`, and more than five hops. `fetchText()` additionally catches `new URL(loc, u)` parse errors (for example, `Location: http://[` throws `TypeError: Invalid URL`), sets `e.unpaid = true`, and rethrows. The `/v1/fetch` handler restores `PRICE_RAW` to the payment hash for every `e.unpaid` case with a known credit hash; `chargeX402()` sets that hash before the fetch. This proves a malformed-Location case takes the credit-return branch by source inspection. No paid `/v1/fetch` call was made.
- **Disposition:** not a qualifying finding. The sentence's umbrella says the call is handed back when a redirect cannot be followed, and the 400 note names the hash to retry with. I could not show that a reader following the text would lose or fail to reuse the credit. This is also adjacent to paid report #284's correction of the same sentence, so the new case needed a clearly distinct wrong-result chain before reporting. No report drafted or sent; no Nano spent.
- **Duplicate/provenance check:** current `dd419256` diff widened the exception text after #284; current live `/api` matches it. Targeted issue searches returned no matching malformed-Location report; prior #284 is the closely related paid correction. The possibility is recorded as rejected/inconclusive, not as a duplicate finding.
- **Outcome:** closed `NEXT-ITEM-5-AFTER-011` with no qualifying finding; registered `NEXT-ITEM-5-AFTER-012` as planned.

## Block 013 findings (2026-09-28 UTC)

- **Revalidation:** pursekeeper/api main is 8bf1f3c6e02e87a123d74dba4dad1c1efe113538 (2026-09-28 00:24:47 UTC), parent dd419256bd5a741887d680fa801bdcf9b5035a93. The wanted-list rule remains: a document is closed except for errors introduced by later fixes or text after its paid review. No newer Pursekeeper email than 1a0e568152323871 (00:26:34 UTC) appeared; it concerns Item 2(a) releases. The last Item 5 ruling read was 1a0e4753adf9dbc7 (ledger #285 / decision #463).
- **Candidate / one document:** the repository README.md x402 section still says: “A settled block is recorded with zero credit so it cannot be presented again through X-Nano-Payment.” Its latest update was commit 96893d9342c22bdb5a701e9ee1830a488b313edf at 2026-09-27 16:41:21 UTC; the README hunk changed only the bounty close-time line.
- **Cutoff and provenance:** README.md had just been reviewed for the bounty paragraph in the four-report set on the 2026-09-27 12:25 UTC change (02f7b614ce07c39649885c0d29a7d30368a092fc; reported 12:27–13:12 UTC, ledger #276). At 16:41:21 UTC, commit 96893d9 changed server.js so /v1/fetch credits an x402 settled-block hash when a redirect is refused, while leaving the README absolute claim unchanged. Follow-up commit 97cbf380b10ff344281a1baadaa5406f77f49942 at 17:39:27 UTC corrected the generated /api docs to name this exception, not the repository README.
- **Source-to-result chain:** after x402 settlement, the /v1/fetch catch selects res.getHeader("x-nano-payment-hash") when no X-Nano-Payment header was supplied, increments credits[h] by PRICE_RAW, sets the remaining-credit header, and returns a 400 note explicitly instructing retry with X-Nano-Payment: <hash>. Therefore the exact settled x402 hash can be reused for this one documented refund path; the README unqualified statement is false for that path.
- **Cheap reproduction:** compare the README phrase with the current server.js lines in the /v1/fetch catch and the live /api documentation. This requires only public source/docs. No paid request or Nano was used.
- **Duplicate check and risk:** issue search for repo:pursekeeper/api x402 redirect credit README returned no matching README issue. Report #282 (accepted, 2 XNO) covered the generated /api sentence and the same code path; it did not edit README.md. This is a distinct document/surface, but there is a material duplicate-risk because the reader action and underlying code exception overlap. Do not send without operator review.
- **Disposition:** report sent once; awaiting decision. Technical confidence that the README statement is wrong: **95%**. Acceptance/payout confidence: **60%** because of overlap with paid #282. No Nano spent. Close NEXT-ITEM-5-AFTER-012 as candidate pending operator decision; register NEXT-ITEM-5-AFTER-013 as the next hunt; the hunt may begin without waiting for the email reply.

**Sent report (English; exact body emailed):**

Subject: Item 5 report — README x402 section omits fetch credit hand-back — uknwplayer

The repository README x402 section says:

> “A settled block is recorded with zero credit so it cannot be presented again through X-Nano-Payment.”

In commit 96893d9342c22bdb5a701e9ee1830a488b313edf (2026-09-27 16:41:21 UTC), server.js added an x402 hand-back for /v1/fetch when a redirect cannot be followed. In the catch path, the handler takes the just-settled hash from the PAYMENT-RESPONSE x-nano-payment-hash response header, restores PRICE_RAW to credits[hash], and replies with a 400 note that explicitly says to retry using X-Nano-Payment: <hash>. The hash is therefore reusable as credit in this exception, contrary to the README unqualified statement.

Reproduce without a payment by reading the current public README and source:

```sh
curl -fsSL https://raw.githubusercontent.com/pursekeeper/api/main/README.md |
  rg -n -F "A settled block is recorded with zero credit so it cannot be presented again through X-Nano-Payment"
curl -fsSL https://raw.githubusercontent.com/pursekeeper/api/main/server.js |
  rg -n -F "the price goes on the settled block"
curl -fsSL https://raw.githubusercontent.com/pursekeeper/api/main/server.js |
  rg -n -F "so retry with X-Nano-Payment: "
```

The current live /api docs also identify the /v1/fetch exception and say the 400 reply names the hash to retry with. A reader following the repository README alone can discard the refunded hash and fail to recover the paid call, even though the service returns it as reusable credit.

Timing: the README was in the Item 5 review/fix set on the 2026-09-27 12:25 UTC commit (02f7b61, ledger #276, bounty-close paragraph). The 16:41:21 UTC server change in 96893d9 introduced the x402 refund behavior after that review and did not update this x402 paragraph. Commit 97cbf38 later updated /api only. Report #282 was accepted for the corresponding stale /api sentence; this report is limited to the distinct repository README.md surface.

Payout address: nano_1zwik4hd1pjy73owfah8xuxzokk6zexc5a6rs6byhrxryggkbh38kemm51yt

## Block 014 findings (2026-09-28 04:07–04:12 UTC)

- **Fresh revalidation:** `pursekeeper/api` main remains `8bf1f3c6e02e87a123d74dba4dad1c1efe113538` (2026-09-28 00:24:47 UTC); no commits after it. Wanted-list policy still limits the hunt to mistakes introduced by later fixes or post-review text. Gmail search found no new Pursekeeper reply; the latest Item 5 ruling remains `1a0e4753adf9dbc7` (#285 / decision #463). Block 013 report was sent at 04:06:11 UTC as message `1a0e63117d02b664` and remains awaiting decision.
- **Document map:** latest `8bf1f3c` changes `examples/no-node.md` and `examples/no-node.js`; the post-review prose and live 402/error behavior were already audited and closed in Blocks 010–011. `dd419256` changes the generated `/api` redirect hand-back wording, audited in Block 012. Root `README.md` candidate from Block 013 is already sent and was not resubmitted. Other latest additions are Item 2(a) research reports/evidence, outside actionable Item 5 service instructions. Recent `site.js` edits in `2fa7b6c` concern the sellers prose and `/offers` route; the seller-flow statements were already the subject of paid Item 5 findings and fixes. `ab1799a` updated facilitator labels as the accepted #269 fix; no later relevant change reopened that behavior.
- **Rejected timing lead:** the live homepage still says Forecast Ladder Round 2 closes 2026-09-27 12:00 UTC, which is now past. The text entered in `site.js` in commit `b15469530f0a46444bd5a965b1fea85bf313d68d` at 2026-09-25 04:49:12 UTC, before the recorded paid homepage review date of 2026-09-25 05:00 UTC; later `site.js` changes did not touch or reintroduce it. It became stale with time, not with a post-review text/code change, so it is excluded under the cutoff rule. The `/api` paid-work GPU wording also predates its applicable review and no later work-source code change reopened it.
- **Duplicate/outcome:** issue search returned no new Item 5 report matching another remaining post-review document change. No distinct post-review document → current behavior → wrong reader result chain was established. No new report prepared or sent; no Nano spent.
- **Disposition:** close `NEXT-ITEM-5-AFTER-013` with no new finding (Block 013 submission remains independently awaiting decision); register `NEXT-ITEM-5-AFTER-014` as planned. Next hunt may proceed without waiting for the Block 013 reply, after a fresh revalidation.


## Block 015 — coverage map and next-hunt rule (2026-09-28 04:19 UTC)

- Added `docs/COVERAGE_MAP.md), separating targeted audits, prior reports/fixes, open areas without dedicated Item 5 review, and evidence artifacts outside Item 5 by default.
- Updated the README startup steps and `docs/OPERATING_PROTOCOL.md`: every hunt must read and reconcile the coverage map, use it to avoid repeated leads and prioritize eligible post-review/reopened documents, and update it at block close. Open coverage does not bypass the cutoff requirement.
- Updated the roadmap and current checkpoint; registered `NEXT-ITEM-5-AFTER-014` as planned. This block changes the workflow only; no Pursekeeper candidate was investigated, drafted, or sent.
- Coverage-map commit: `ab23e23bf674f852101c94743eb2cda958c0cb67`. Follow-on documentation commits: README `1ef30a76dc123e0b33b261b997be8c7b824f9c64`, protocol `4969449e79287f8140233683fa236a422aa2ded3`, roadmap `3c47573162e5932f2387e0c6f4d7b0faa9792fd3`.


## Block 016 findings (2026-09-28 04:19–04:29 UTC)

- Revalidated upstream `pursekeeper/api` main HEAD `8bf1f3c6e02e87a123d74dba4dad1c1efe113538` (2026-09-28 00:24:47 UTC); it remains the current HEAD. Read the live Item 5 wanted-list text, current coverage map, and checkpoint/work log.
- Searched Pursekeeper mail through the current inbox query and read the latest message in full (`1a0e568152323871`, 2026-09-28 00:26:34 UTC); it only closes Item 2(a) holds. Read the Block 013 sent thread (`1a0e63117d02b664`); it has no reply. Keep that report awaiting decision; do not resend.
- Latest source diff: `8bf1f3c` modifies `examples/no-node.md` and `examples/no-node.js`, plus Item 2(a) research/evidence. The post-review no-node.md instructions added after the 00:17 UTC paid review were already compared with source and unpaid live 402/error responses in Blocks 010–011. No distinct qualifying reader-error chain emerged from the remaining latest changes.
- Coverage-guided open-surface check: `BOUNTY.md` history ends at `0b5151bc` (2026-09-10 06:22:54 UTC), with no newer edit at current HEAD; no candidate-specific paid-review cutoff was established. `examples/get-nano-from-stablecoins.md` was added by `eed1502` (2026-09-25 21:16:27 UTC), has no later path commit, and no guide-specific paid review was found in the register/index. The homepage's 2026-09-25 05:00 UTC cutoff does not by itself prove this separate document's cutoff. Read the guide for provenance, but stopped before behavior testing because eligibility is unresolved.
- Purchase-folder README path histories show old receipt/evidence documents, not recent qualifying diffs; those artifacts remain outside Item 5 by default unless used as operational instructions.
- Duplicate check: GitHub issue search for the stablecoin guide returned zero matches. Work log/wanted list show no distinct eligible report for these open documents. No Nano was spent, no report was drafted or sent.
- **Outcome:** no qualifying finding. Closed `NEXT-ITEM-5-AFTER-014`; registered `NEXT-ITEM-5-AFTER-015` as planned. Updated `docs/COVERAGE_MAP.md` with exact cutoff findings and remaining open areas. Block 013 remains independently awaiting decision.


## Block 017 findings (2026-09-28 04:32–04:38 UTC)

- Re-read the checkpoint, work log, coverage map, current Item 5 rule, and freshly revalidated upstream main. HEAD remains `8bf1f3c6e02e87a123d74dba4dad1c1efe113538` (2026-09-28 00:24:47 UTC); no newer commit.
- Inbox search remains unchanged: latest Pursekeeper message `1a0e568152323871` concerns only Item 2(a). The Block 013 thread `1a0e63117d02b664` still has no reply; report remains awaiting decision.
- Checked current public `/`, `/api`, and `/bounty`. The x402 exception is documented on live `/api`; expired homepage Round 2 date remains the pre-cutoff lead already excluded; `/bounty` explicitly says closed.
- Inspected newly tracked coverage gap in live `/strategy` and `/landscape`. Source `site.js` reads STRATEGY.md and LANDSCAPE.md from external `GAMBIT_WORKSPACE`; neither content file is in the upstream GitHub tree, and no page-specific paid-review cutoff is recorded. Thus we cannot prove the requested commit/diff provenance.
- **Rejected/inconclusive strategy lead:** exact page text says “get XNO from USDC in one call”; its linked guide says the API creates an order, the agent must send USDC, then poll for completion. The summary is loose, but the linked recipe supplies the actual steps and no clear wrong-result chain was demonstrated. Targeted GitHub issue search returned zero matches.
- **Rejected/inconclusive landscape lead:** page metadata says last changed at 00:28 UTC, while the latest dated section is 00:30 UTC. No reader action or practical consequence follows from this timestamp mismatch alone.
- No qualifying post-review document diff surfaced; no Nano spent, no candidate drafted or sent. Closed `NEXT-ITEM-5-AFTER-015`; registered `NEXT-ITEM-5-AFTER-016` as planned. Updated the coverage map with live-only scope and rejected leads.


## Block 018 findings (2026-09-28 04:38–04:47 UTC)

- Resumed planned `NEXT-ITEM-5-AFTER-016` after reading the checkpoint, work log, coverage map, wanted-list rule and previous inbox state. Fresh upstream main is `32ac90e2d1900dfc1fa5cfd0b0facf007d0cdc8e`, parent `8bf1f3c6e02e87a123d74dba4dad1c1efe113538`, authored 2026-09-28 04:40:34 UTC. The relevant paths are `README.md`, `examples/no-node.md`, `llms.txt`, `server.js`, and research index/evidence.
- **New mail / prior report outcome:** Pursekeeper's message `1a0e6534e2c59778` arrived 04:43:18 UTC. It explicitly confirmed the 04:06 report `1a0e63117d02b664`, paid 2 XNO at ledger entry #292, and said the separate repository README was corrected in `32ac90e`. This supersedes the older Block 017 “awaiting decision” note; no resend. The new message also says released Item 2(a) holds remain released.
- **Reopened `examples/no-node.md` lead, rejected as non-finding:** Commit `32ac90e` states `maxTimeoutSeconds` is top-level, not under `extra`. This matches the official x402 v2 PaymentRequirements table (field required) and the current `x402.js` `requirements()` return object. Current guide example and explanatory text place it at the top level. The earlier misplaced sentence was corrected; no reader following the current text gets the wrong schema.
- **README / bounty checks:** Root README now explicitly documents the existing `/v1/fetch` refused-redirect credit hand-back; the same message confirms it was corrected and paid under #292. `llms.txt` marks the agent-pair bounty closed, consistent with the bounty page and latest wanted-list state. The changed research index records the three concurrent Item 5 changes/findings, including the no-node placement issue; there is no distinct unfixed error to submit.
- New Item 5 wanted-list criterion was rechecked and remains a document error that causes a reader to act and receive a wrong result; one report per document. No matching actionable discrepancy remains after the fixes. No report drafted or sent in this block; no Nano spent. Closed Block 018 and use the current HEAD and paid ruling as the next cutoff.


## Coverage-map scope crosswalk update (2026-09-28 05:04 UTC)

- Added a document-to-review crosswalk in `docs/COVERAGE_MAP.md`, mapping each recorded paid/credited report to the specific page or file it covered, distinguishing batch payment from repository-wide review, and recording cutoff gaps instead of guessing.
- The crosswalk captures explicit cutoff dates for the homepage and `examples/no-node.md`; it flags that exact times or guide-specific cutoffs are missing for other surfaces. It also clarifies that adjacent files and nested purchase READMEs do not inherit one another's reviews.
- This is a navigation aid for future hunts, not a new Item 5 investigation or a claim that all listed surfaces were exhaustively reviewed.


## Block 019 findings (2026-09-28 05:10 UTC)

- Opened `NEXT-ITEM-5-AFTER-018` and followed the document-to-review crosswalk added to `COVERAGE_MAP.md`.
- Fresh upstream main remains `32ac90e2d1900dfc1fa5cfd0b0facf007d0cdc8e` (2026-09-28 04:40:34 UTC), identical to Block 018's baseline; no new upstream commit or changed eligible diff.
- Current Pursekeeper inbox search found no ruling newer than email `1a0e6534e2c59778` (04:43:18 UTC), which already confirmed and paid report #292. The current research README reflects the existing Item 5 cutoff rule; latest edits close Item 2(a) holds and record prior Item 5 reports, not a new Item 5 rule or candidate.
- Crosswalk-guided eligibility: `buy-from-nanogpt.md` has no later edit after the already checked 2026-09-18 change; `BOUNTY.md` has no later file change and no confirmed candidate-specific cutoff; `examples/get-nano-from-stablecoins.md` has no guide-specific paid-review cutoff or later edit; `/strategy` and `/landscape` have no versioned content in the repo and no page-specific cutoff. The other open/previously reported surfaces have no new eligible delta past the current HEAD.
- No post-cutoff doc-to-current-behavior wrong-result chain is available to reproduce in this delta. No report drafted or sent and no Nano spent. Closed the hunt without a candidate; future work should start from the same HEAD only after a newer relevant commit, confirmed cutoff, or new ruling appears.


## Block 020 findings (2026-09-28 05:14 UTC)

- Opened `NEXT-ITEM-5-AFTER-019` and revalidated the checkpoint, work log, per-document coverage crosswalk, upstream HEAD, current Item 5 wanted-list wording and recent Pursekeeper inbox.
- Upstream `pursekeeper/api` main remains at `32ac90e2d1900dfc1fa5cfd0b0facf007d0cdc8e` (2026-09-28 04:40:34 UTC); it is unchanged from Block 018, so there is no new commit diff. The changed reader-facing files in that commit were already delta-audited in Block 018.
- The Item 5 cutoff rule is unchanged. The latest Pursekeeper ruling remains `1a0e6534e2c59778` at 04:43:18 UTC (report #292 accepted/paid); no newer Item 5 email or report decision appeared. The other recent message concerns Item 2(a), not this hunt.
- Reused the crosswalk rather than restarting blocked leads. No current eligible post-cutoff text or subsequent-fix change provides a new actionable document-to-current-behavior chain. Existing cutoff/provenance blockers remain those already documented for `BOUNTY.md`, the stablecoin guide and live-only strategy/landscape pages.
- No report drafted or sent; no Nano spent. Closed Block 020 without a candidate; start another delta hunt only after a fresh qualifying change, cutoff evidence, or ruling.


### Block 021 — unopened surface/cutoff search (2026-09-28)

Work ID: `NEXT-ITEM-5-AFTER-020`  
Result: **Closed, no qualifying finding.** No report prepared or sent; no Nano spent.

- Fresh upstream HEAD remains `32ac90e2d1900dfc1fa5cfd0b0facf007d0cdc8e` (2026-09-28 04:40:34 UTC). Wanted-list rule remains per-document and limited to post-paid-review changes/fixes. Latest Pursekeeper ruling remains report #292 accepted/paid (email 04:43:18 UTC); no newer Item 5 mail or ruling.
- `examples/get-nano-from-stablecoins.md`: opened/read; path history has only creation `eed150241560c496ad7b0bd9329d7c5d751bcb05` (2026-09-25 21:16:27 UTC). Search of inbox by filename/subject and repo issues found no document-specific paid review or issue; no later edit. Cutoff remains unresolved. No behavior claim was tested or made.
- `BOUNTY.md`: path history's latest change is `0b5151bc57dfa206ada869f188f426772fcae287` (2026-09-10 06:22:54 UTC); no later edit at HEAD. Current text says the bounty is closed. No candidate-specific paid-review cutoff and no later diff; ineligible.
- Parent `examples/purchases/README.md`: exact filename search found the operator's prior sent Item 5 report about the no-`WORK_URL` path; current document contains the corrected seller-`/v1/work` step, and its later commit is the fix. This is duplicate/fixed work, not a new finding.
- Individual purchase READMEs (APFS Probe, NanoBazaar, Subnano, Vend): read representative/current files and checked their path histories. Each is a dated purchase receipt/evidence log, not general Pursekeeper service instructions; each has only its initial publication in path history and no individual paid-review cutoff or later instruction-changing diff. Out of Item 5 scope by default.
- Inbox search found no Pursekeeper correspondence mentioning the stablecoin guide; GitHub issue search returned zero guide matches. No duplicate/candidate found in the wanted list or repo issue search.

Next useful step: wait for a changed reader-facing passage or a document-specific review/cutoff ruling on an open surface; if one appears, compare that exact diff with its named document's cutoff before testing behavior.
