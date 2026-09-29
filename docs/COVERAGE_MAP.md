# Coverage Map — Pursekeeper Item 5

**Last reconciled:** 2026-09-29, against Blocks 028–033, upstream HEAD `7bfb2e2567770563f697d6f33eb2fcabe0d6f108`, the current wanted list, and Pursekeeper inbox.
**Purpose:** Preserve where Item 5 hunts have looked, what they actually covered, and what remains without a systematic audit. This is a navigation aid, not proof that a document is currently accurate. Revalidate HEAD, diffs, live behavior, review cutoff, and duplicate status before each hunt.

## Coverage states

- **Targeted audit recorded** — a specific passage, changed diff, structure, or behavior was examined. This does not mean every line was audited.
- **Reported / fixed or credited** — a historical finding exists; do not reopen unless a later change creates a distinct error.
- **Open — not systematically audited** — the work log does not show a dedicated Item 5 audit. It may still have been opened incidentally.
- **Out of Item 5 scope by default** — evidence/research artifacts that are not reader-facing Pursekeeper service instructions. Reconsider only if a later change makes them operational instructions.

## Audited or previously reported surfaces

| Surface | Recorded coverage | Current handling |
|---|---|---|
| Repository `README.md` | Prior review and bounty wording; Block 013 compared the x402 settled-hash sentence with the later `/v1/fetch` credit-return code. | Block 013 report was confirmed and paid as ledger #292 on 2026-09-28 04:43 UTC; corrected in `32ac90e`. Do not resend or reopen the same exception. |
| `examples/no-node.md` | Paid reports #228, #279, #289, #307, #319, #323 and credited #281 are recorded; Blocks 010–011 and 025/030 screened specific deltas. Block 032 read the complete guide line by line against current code and official protocol docs. | Latest relevant prose/code cutoff: #323 fix in `b438d56` (2026-09-28 22:25 UTC), which changed paid-work limits/concurrency wording. Current source matches. `7bfb2e2` later changes `no-node.js`, not `no-node.md`; retry behavior was checked. Full guide audit found no qualifying post-cutoff mismatch. An older caveat remains: `/v1/receivable` caps each response at 100; one `receive` run can leave later sends if there are >100, but this predates the 2026-09-10 paid review (endpoint cap exists in `b947aa1`, 2026-09-08), so it is excluded. See Block 032 checkpoint; reopen only on a later relevant diff. |
| `examples/buy-from-nanogpt.md` | Block 009 and Block 022 checked post-review guide changes, unpaid quotes, and linked evidence; earlier paid rows concerned other passages. | New post-review Notes-bullet report #307 was paid and fixed by `31da309` (2026-09-28 16:52:29 UTC). Block 025 screened the correction against the wanted-list payment terms and current `/examples/*` route. No new actionable error established. Targeted delta review, not a complete line-by-line audit. |
| `examples/purchases/README.md` | Historical accepted report #266 covered the seller-first `/v1/work` flow. | Reopen only if a later change affects the instructions. |
| `examples/research/README.md` | Historical accepted reports and the paid #285 cross-surface timing contradiction; Block 006 checked table/link structure; later ruling rows were compared with public decision data. | Ledger/index and selected changed rows were checked, not every linked research report or evidence file. |
| Generated `/` and `/api` text | Historical paid #282 checked the x402 hand-back claim; Block 012 traced later `dd419256` redirect wording against `fetchText()` and the 400 path. | Previously reported/fixed area; any new report needs a distinct post-fix error and consequence. |
| `/facilitator` | Historical accepted report #269; `ab1799a` fixed seller labels. Block 006 made two unauthenticated body-size probes. Block 031 audited the full `/settle` docs against `facilitator.js`/`x402.js` and Nano fork behavior. | Cancellation wording about publishing any block to withdraw an unsettled send is a legacy concern: it predates the paid facilitator-doc review. `b438d56`/`7bfb2e2` do not alter the facilitator path because `settleRequest()` does not pass `hash`/`landed` to `x402.settle()`. No eligible reopening or report; do not re-audit absent a later relevant change. |
| `/sellers`, `/offers`, `/sellers.json` | Historical accepted reports #266/#275 and one `checked_at` lead marked not reproduced; later seller-flow diffs were revisited in Block 014. | Search prior rulings first; do not revive stale or duplicate leads without new evidence. |
| Endpoint/docs behavior: `/v1/requests`, `/v1/process`, `/v1/fetch`, `/v1/hash`, `/v1/credit`, `/.well-known/x402` | Covered in specific historical reports/probes, including paid reports #266/#275/#276/#282 and current no-node/API checks. | Coverage is finding-specific, not an exhaustive endpoint audit. Revalidate source and current public behavior. |
| Homepage campaign date and paid-work GPU wording | Block 014 checked provenance/cutoff; campaign text predated its paid-review cutoff, GPU wording also predates review. | Excluded for timing. Do not re-open without a later relevant text/code change. |

## Paid-review scope crosswalk

Use this as a document-by-document index, not as proof that a whole page or file was audited. A payment batch may contain several findings; it does not merge the documents' cutoffs. Fixes reopen only the affected document for a distinct error introduced by that fix. “Cutoff not recorded” means do not invent one; inspect the source history and wanted-list record before claiming eligibility.

| Document / surface | Paid review or finding recorded | Cutoff and scope note |
|---|---|---|
| Pursekeeper homepage `/` | #217, #219 and #282 | Wanted list records the homepage review date as 2026-09-25 05:00 UTC. Report #282 later paid for the x402 hand-back wording and its fix in `97cbf38` reopened that changed prose for new errors. |
| Live `/api` documentation | #266 and #282; Ops Control HQ #284 review | #266 covered the wrapped `/v1/requests` line; #282 covered x402 hand-back prose. After #284, `dd419256` changed the redirect explanation (2026-09-27 20:00:11 UTC); only that post-review change was examined in Blocks 011–012. |
| `examples/no-node.md` | Paid reports #228 and #279, paid later-fix reports recorded in the research README (including the closed-bounty sentence corrected in `05d29c1`), and credited #281 are recorded. | The cutoff has advanced through later fixes; the latest pre-Block-025 reviewed no-node fix was #289 at 2026-09-28 00:17 UTC, with further paid/fix edits through `05d29c1` on 2026-09-28. Block 025 screened the new text and relevant source routes; no new actionable mismatch. See the Block 025 reconciliation; revalidate again on a new change. |
| `examples/buy-from-nanogpt.md` | Paid review recorded as 2026-09-10; report #307 paid for the previously unreviewed Notes-bullet stale-bounty claim | The correction was committed in `31da309` at 2026-09-28 16:52:29 UTC. Block 025 checked the corrected text for a new error and found none. Older header differences remain excluded because they predate the paid review. |
| `examples/purchases/README.md` | #266 | The paid finding covered the seller-first `/v1/work` instructions. It does not cover individual READMEs in `examples/purchases/*/`. |
| `examples/research/README.md` | #266 and #285 | Separate findings were paid in each review. Check the latest changed rows and ruling before reusing either cutoff; this index does not claim every linked research file was reviewed. |
| `/facilitator` | #269 | The paid finding concerned stale seller labels; fix `ab1799a` derived labels from verified listings. |
| `/sellers` and `/.well-known/x402` manifest | #266 | Separate findings in the same 10-XNO transfer: invoice-flow wording and the required `url` parameter/pre-charge behavior, respectively. |
| `/offers` and fetch/credit behavior | #275; #282 and #284 also touched fetch-related docs/code | #275 paid for the offer-trigger claim and fetch redirect behavior. Check whether a later commit changed the particular prose before treating it as a fresh document finding. Code-only findings in the same batch do not reset unrelated document cutoffs. |
| Repository `README.md` | #275 and #292 | #275 paid for the closed-bounty claim; #292 paid for the distinct x402 hand-back omission and fixed it in `32ac90e` (04:40:34 UTC). |
| `llms.txt` | New post-review bounty-status row recorded in upstream research README at `32ac90e` | It now says the agent-pair bounty is closed. No paid-review cutoff/ruling for this separate file is recorded here; current wording is accurate. |

**Known cutoff gaps:** `examples/get-nano-from-stablecoins.md` has no guide-specific paid review in the register; `BOUNTY.md` has no substantiated candidate-specific cutoff; the homepage/strategy/landscape live-only files have no versioned content history in this repo. Do not borrow a neighboring document's review date.

## Open areas — no dedicated Item 5 audit recorded

These are candidates for **cutoff discovery first**, not automatic report targets. Item 5 eligibility still requires a substantiated paid-review/fix cutoff and a later relevant diff.

| Surface | Next useful step |
|---|---|
| `BOUNTY.md` | Blocks 016 and 021 checked the full path history and current text: latest change `0b5151bc57dfa206ada869f188f426772fcae287` (2026-09-10 06:22:54 UTC); current text says closed. Block 021 found no newer diff, no candidate-specific paid-review cutoff, and no issue/mail lead. Ineligible; reopen only if a later relevant change appears or a cutoff is substantiated. |
| `examples/get-nano-from-stablecoins.md` | Blocks 016/021/025 screened it for provenance and the evidence-only addendum; Block 033 checked its own paid-review cutoff. The file was created in `eed1502` (2026-09-25 21:16:27 UTC); `05d29c1` (2026-09-28 16:48:43 UTC) adds only a historical transaction record; no later path commit exists at HEAD. No guide-specific paid review/scope found in the public log, report register, or Gmail. The homepage's 2026-09-25 05:00 UTC cutoff predates the guide and cannot be borrowed. **Full line-by-line behavior audit remains open; eligibility unresolved.** Reopen on a guide-specific review/cutoff record or relevant later change. See Block 033.
| Individual `examples/purchases/*/README.md` files | Block 021 read the APFS Probe, NanoBazaar, Subnano, and Vend READMEs and checked each path history: each is an operational receipt/evidence log with only its initial publication, no later instruction-changing diff, and no individual paid-review cutoff. Out of Item 5 scope by default; parent purchases README's paid review does not cover these separate files. Reconsider only if later text turns one into service instructions and its own cutoff is established. |
| Purchase evidence JSON/TXT and scripts | Do not treat raw evidence as Item 5 instructions by default. Inspect only if a document points readers to it as an operational step or later text turns it into guidance. |
| Individual `examples/research/*.md` reports and research evidence folders | These are generally Item 2(a) research/evidence, not Item 5 service docs. Do not bulk-audit as Item 5. Reclassify a specific file only if it contains reader-facing service instructions and has an eligible post-review change. |
| Other public site pages/routes | Block 017 inspected live `/strategy` and `/landscape` in addition to `/`, `/api`, and `/bounty`. `site.js` reads STRATEGY.md/LANDSCAPE.md from external GAMBIT_WORKSPACE; those files are not tracked in the current GitHub tree, so no versioned content diff or paid-review cutoff was established. `/strategy` line “get XNO from USDC in one call” was compared with its linked guide's POST + deposit + polling flow, but the guide explains those steps and no clear wrong-result chain was established. `/landscape` metadata says last changed 00:28 UTC while its latest dated entry says 00:30 UTC; no practical reader consequence. Keep both as targeted live-only checks, not eligible findings, until cutoff/provenance and an actionable consequence are established. |

## How to use this map on every hunt

1. Read this map together with the checkpoint, work log, wanted list, current HEAD, and inbox before selecting a target.
2. Start with the strongest proven pattern: a post-review commit changes documentation, the current docs contradict current implementation/live data, and following the text produces a cheap, reproducible wrong result.
3. Rank eligible post-cutoff/reopened documents ahead of merely untouched documents. “Not systematically audited” never overrides the Item 5 cutoff rule.
4. Before testing, search the map, work log, sent reports/replies, issues, commits, and fixes for the same document, behavior, and consequence.
5. At block close, update this map with the exact passage/scope inspected, commit/cutoff, reproduction, disposition, and next open area. Keep rejected and inconclusive leads so later hunts do not repeat them.
6. Never upgrade “targeted audit” to “fully audited” unless the work log records the complete scope and method.

## Hunt-selection priority

Prefer, in order:
1. A new post-review documentation diff tied to a fix or paid review.
2. A document reopened by a later implementation change.
3. A distinct, documented surface with a verifiable cutoff and recent change.

For each, require the chain **document says X → current code/live state does Y → a reader following X gets a reproducible wrong result**. If no candidate meets that chain, close the block without a report and use the updated map to guide the next hunt.


## Block 016 reconciliation (2026-09-28 04:29 UTC)

- Upstream HEAD, wanted-list text, inbox, and the Block 013 sent thread were freshly rechecked. No new Item 5 email/reply or upstream commit appeared.
- The only post-review no-node.md wording diff remains the 00:24 UTC addition in 8bf1f3c, already checked against current source and unpaid live 402/error behavior in Blocks 010–011. Other latest additions are Item 2(a) research evidence. No new eligible candidate was identified.
- The stablecoin guide's initial addition is post the homepage's 2026-09-25 05:00 UTC cutoff, but that does not establish a paid-review cutoff for this separate guide. Its own history contains only its creation commit; no later guide diff or guide-specific paid review was found. Eligibility remains unresolved, so no Item 5 behavior finding is claimed.
- GitHub issue search for the guide returned zero matches. No Nano was spent; no report drafted or sent.


## Block 017 reconciliation (2026-09-28 04:38 UTC)

- Fresh current state still showed upstream HEAD `8bf1f3c6e02e87a123d74dba4dad1c1efe113538`, no new wanted-list rule, and no new Pursekeeper mail or reply to Block 013.
- Current public `/`, `/api`, and `/bounty` were checked. The `/api` x402 hand-back exception is present; the homepage's expired Round 2 date remains pre-cutoff as already recorded; bounty text says closed and points to the current wanted list.
- Live `/strategy` and `/landscape` are rendered from files in external `GAMBIT_WORKSPACE`, not tracked in the upstream repository. Page mtime/datestamps therefore do not provide the requested commit diff or a page-specific paid-review cutoff. The strategy's “one call” shorthand is followed by a link to a guide that accurately requires creating an order, sending USDC, and polling; no wrong result from following the linked recipe was established. The landscape's 00:28 metadata vs 00:30 dated-entry mismatch has no demonstrated reader consequence.
- Issue search for the strategy wording returned zero matches. These are documented as rejected/inconclusive leads, not candidate reports. No Nano spent and no report drafted or sent.


## Block 018 reconciliation (2026-09-28 04:47 UTC)

- Upstream HEAD advanced from the Block 017 checkpoint to `32ac90e2d1900dfc1fa5cfd0b0facf007d0cdc8e` at 04:40:34 UTC. Current Item 5 criterion was rechecked; current inbox contains a new ruling at 04:43:18 UTC.
- The repository README hand-back exception is now fixed and report #292 is explicitly accepted/paid (2 XNO). The prior “awaiting decision” status is superseded.
- The new `examples/no-node.md` change postdates its 2026-09-25 12:50 UTC paid-review cutoff and is a valid correction to its prior `extra.maxTimeoutSeconds` placement. Official x402 v2 schema marks `maxTimeoutSeconds` required on PaymentRequirements; local `x402.js` sets it on the top-level requirements object; the current prose and example agree. No candidate remains.
- `llms.txt` now marks the agent-pair bounty closed; this is consistent with the current bounty state. The research README records the same three post-review changes, so the affected leads are accounted for and not duplicates waiting to be submitted.
- This was a targeted audit of the new diff and current cited schema/code, not a whole-repository audit. No report sent and no Nano spent. Next hunt starts from this commit and ruling.


## Block 019 reconciliation (2026-09-28 05:10 UTC)

- Revalidated the coverage crosswalk against upstream main and the latest Pursekeeper inbox. Upstream remains at `32ac90e2d1900dfc1fa5cfd0b0facf007d0cdc8e`; no later commit, Item 5 rule update, or email ruling appeared.
- No changed eligible diff remains since Block 018. The previously open leads retain their recorded blockers: the NanoGPT guide's last changed passage was already audited; `BOUNTY.md` has no newer file commit or candidate-specific paid-review cutoff; the stablecoin guide has no guide-specific cutoff or later edit; strategy/landscape content has no versioned source or page-specific cutoff.
- This was a delta revalidation using the existing map, not a claim that every document was reread. No candidate report and no Nano spend. Keep these blockers recorded; reopen only with new provenance/diff evidence.


## Block 020 reconciliation (2026-09-28 05:14 UTC)

- Revalidated the current main branch, wanted-list rule and Pursekeeper inbox. HEAD remains `32ac90e2d1900dfc1fa5cfd0b0facf007d0cdc8e`; no new Item 5 ruling or eligible post-cutoff diff has appeared.
- The latest documentation diff was already checked in Block 018. The existing cutoff and provenance blockers in the map remain unchanged; no additional candidate was established.
- This was a delta revalidation using the paid-review crosswalk, not a full reread of every document. No report sent and no Nano spent.


## Block 021 reconciliation (2026-09-28 05:25 UTC)

- Revalidated upstream main, wanted-list wording and Pursekeeper inbox; HEAD remains `32ac90e2d1900dfc1fa5cfd0b0facf007d0cdc8e`, latest Item 5 ruling remains #292 paid at 04:43:18 UTC.
- Searched previously untouched areas. `BOUNTY.md` has no later path change or candidate-specific cutoff. The stablecoin guide has only its creation commit and no guide-specific review evidence; cutoff unresolved. GitHub issue search for the guide returned zero; inbox searches found no guide-related review mail.
- Checked parent purchase README duplication: its current text includes the seller-`/v1/work` correction associated with the prior report. The individual APFS Probe, NanoBazaar, Subnano and Vend READMEs are purchase receipts, not general service instructions; their per-path history contains only initial publication.
- No new candidate met the chain of a named document's paid-review/fix cutoff, a later relevant diff, contradicted current behavior, and reproducible wrong reader result. No report or Nano spend. Coverage stays targeted; no whole-file certification is claimed.
- Next: monitor for document-specific paid-review evidence or a new relevant text/code change; then open only that document's delta and verify consequences before drafting.


## Block 022 reconciliation (2026-09-28 05:30 UTC)

- Revalidated HEAD `32ac90e2d1900dfc1fa5cfd0b0facf007d0cdc8e`, wanted-list scope, and latest inbox ruling #292 (04:43:18 UTC).
- Audited the precise post-review diff in `examples/buy-from-nanogpt.md`: `432f34f` (2026-09-18 12:06:03 UTC) added the single-use quote warning; `ca19562` (2026-09-18 16:20:21 UTC) added its evidence link. Current official NanoGPT docs and linked firsthand evidence support the changed warning.
- Two unpaid, unauthenticated quote requests were made to the old documented path and current official path. Both returned HTTP 402 with payment options; no Nano payment was sent. The endpoint path difference did not produce a wrong result.
- This is a targeted delta/behavior check, not a full audit of the guide. No distinct actionable error or report candidate; no report sent and no Nano spent.
- Next: only reopen on a new relevant diff or newly substantiated per-document cutoff.


## Block 023 reconciliation (2026-09-28 06:08 UTC)

- Revalidated upstream HEAD `32ac90e2d1900dfc1fa5cfd0b0facf007d0cdc8e`, Item 5 wanted-list rule, and Pursekeeper inbox; latest Item 5 mail remains #292 paid at 04:43:18 UTC.
- GitHub issue [#68](https://github.com/pursekeeper/api/issues/68) targets the same post-review sentence in `examples/research/README.md` about Content-Length and truncated responses. The author states the report was already emailed; the public issue includes the full reproducer, the paid #274 ruling, and the later `32ac90e` range fix. Treat the same instruction/consequence as duplicate; do not report it.
- Current read-only checks after `32ac90e`: gzip HEADs for `/sellers.json` and `/log.json` returned true compressed lengths (20,722 and 316,992); identity GETs for `/log.json` and `/landscape` completed at their declared byte lengths; gzip GET `/log.json` completed; a 6,000-byte range returned 206 with a matching Content-Range and Content-Length. This environment did not reproduce issue #68's former truncation.
- No separate reader-facing wrong-result chain was found in this delta. Targeted check only; no candidate drafted/sent and no Nano spent.
- Next: select a distinct post-review/reopened document and issue only after another fresh state check; exclude #68's document sentence and consequence.


## Block 024 reconciliation (2026-09-28 06:14 UTC)

- Revalidated upstream HEAD `32ac90e2d1900dfc1fa5cfd0b0facf007d0cdc8e`, the current wanted-list rule, latest inbox ruling (#292, accepted/paid at 04:43:18 UTC), open Item 5 issues, and the existing coverage map/work log. No newer upstream commit, Item 5 rule change, or email ruling appeared.
- Audited the public GitHub tree recursively against the coverage map. No omitted first-party service-instruction Markdown was found. Remaining Markdown/TXT under `examples/research` and `examples/purchases` are research, receipts, or evidence artifacts, not Item 5 service instructions by default.
- Issue #68 remains a duplicate of the already emailed Content-Length/truncation report in `examples/research/README.md`; `32ac90e` includes the range fix, and current live behavior was already tested in Block 023. Other open issues concern different bounty items or seller onboarding.
- Rechecked remaining cutoff blockers: `BOUNTY.md` has no later diff or candidate-specific paid-review cutoff; the stablecoin guide has no later edit or its own paid-review cutoff; strategy/landscape content remains external/unversioned. The mapped post-review changes and fixes have already been screened.
- No distinct document/error chain meets the Item 5 rule. No report sent and no Nano spent. This was a tree/inventory and delta screen, not a line-by-line audit of every historical file.
- Next useful step: start Block 025 from fresh state after a new main-branch commit or a ruling establishing a document-specific cutoff/reopening. Exclude prior reported/fixed claims.


## Block 025 reconciliation (2026-09-28 19:35–19:43 UTC)

- Fresh upstream HEAD is `31da3096db8d5f93c6354a870f95546f1973ecb5`, nine commits ahead of Block 024's base `32ac90e2d1900dfc1fa5cfd0b0facf007d0cdc8e). Wanted-list rule remains document-specific. Gmail's latest visible inbound Item 5 ruling is #292; upstream's public research record includes later reports/fixes through #307.
- Screened the post-review/fix deltas in `examples/no-node.md` and `examples/buy-from-nanogpt.md`. The paid #307 stale-bounty claim was fixed in `31da309`; the replacement text agrees with the current wanted list's per-item prices and first-acceptable-report wording. The no-node fix points readers to that same list and to current example paths; source `server.js` serves existing `/examples/*` files, and the revised GPU/budget wording matches the current source comments/configuration. No new reader-action/wrong-result chain found.
- `examples/get-nano-from-stablecoins.md` received a transaction-evidence addendum in `05d29c1`, not a new procedure; no actionable error was established. Its per-document paid-review cutoff remains unsubstantiated.
- Checked issues, wanted/research rows and prior sent reports for duplicate claims. The closed-bounty claim is the already paid #307 report; no distinct candidate surfaced.
- Direct public-page retrieval could not be verified in this block: the web opener marked the target URLs inaccessible and Firecrawl had insufficient credits. Link assessment is therefore source-level, not a fresh live HTTP-status claim. No report sent and no Nano spent.
- Next: begin Block 026 from fresh state; reopen only eligible post-cutoff or later-fix text, and exclude the #307 claim.


## Block 026 reconciliation (2026-09-28 21:23–21:35 UTC)

- Fresh upstream HEAD `449391364ae6e6c37fa19699fe389426359a16cf`; paid/fix register now through ledger #319. Gmail's latest visible inbound Item 5 decision remains #292. The paid #316 correction is the cutoff for the re-opened `examples/buy-from-nanogpt.md` paragraph.
- Checked that correction against `examples/get-nano-from-stablecoins.md`: its stated audience holds USDC/USDT; order creation requires a Nanswap key, and the documented deposit pays from that balance. Link to `no-node.md` describes what to do after acquiring Nano. The fix resolves #316 and adds no newly demonstrated wrong-result step. #316 is already paid/fixed; duplicate excluded.
- Read the current README `/v1/work` table and compared the #317 post-fix route against `workGenerate()`: validation/capacity precede charge, failed generation hands credit back, and paid calls bypass the free per-IP counter. The README's no-limit paid claim matches. GPU fallback during the existing cooldown is older behavior, not introduced by the latest handler fix; no eligible report based on it.
- Current public `/v1/x402` JSON was not verified: curl timed out at 8 seconds. Conclusions are source-based. No candidate, no submission, no Nano spent. Block 026 was a targeted delta review, not a line-by-line audit.
- Next: Block 027 after fresh revalidation; preserve the stablecoin guide's unresolved review cutoff and prioritize eligible untouched docs.


## Block 027 reconciliation (2026-09-28 21:35–21:51 UTC)

- Fresh upstream HEAD remains `449391364ae6e6c37fa19699fe389426359a16cf`; no API repository commit landed after Block 026. The current register records paid Item 5 reports through #319; Gmail shows no inbound Item 5 decision after #292.
- Screened the recent research README additions/corrections: #319's payment row and two timestamp updates in `4493913`. They document historical events; neither gives operational instructions, and no reproducible wrong action or participation consequence was established. Prior #285 timing dispute/ruling checked for duplicate scope.
- No qualifying candidate. No send or Nano spend. Block 027 is a narrow review of the newest research-index edits, not a new full audit. Next action: Block 031 from fresh state; prioritize newly changed eligible passages and preserve the stablecoin-guide's unresolved cutoff.


## Block 028 reconciliation (2026-09-29)

- Fresh upstream state carried forward from the end of Block 027 and revalidated at Block 030: API HEAD 7bfb2e2567770563f697d6f33eb2fcabe0d6f108, parent b438d5653604422ca7be7eb09ab5dd967d409f90, committed 2026-09-29 02:50:50 UTC. The wanted list was read from the current examples/research/README.md; Pursekeeper inbox had no reply to the DNS report.
- Block 028's eligible root README /v1/fetch DNS hand-back discrepancy was retained for operator review; it is the same finding later sent once on 2026-09-29 (see Work Log and Block 029), so exclude it from future candidates.
- The send is recorded as Awaiting decision. The DNS lead is not pending operator review and must not be submitted again.

## Block 029 reconciliation (2026-09-29)

- Reconfirmed that the DNS report was sent once to agent@pursekeeper.dev (Message-ID 1a0eb6c766a182c0, SENT); no new Pursekeeper reply was present. No report was drafted or sent in this block.
- Carry-forward: begin Block 030 from current HEAD and screen fresh diffs, current wanted-list wording, exact code behavior, and report/issues history.

## Block 030 reconciliation (2026-09-29)

- Revalidated default branch main, API HEAD 7bfb2e2567770563f697d6f33eb2fcabe0d6f108 (2026-09-29 02:50:50 UTC), parent b438d5653604422ca7be7eb09ab5dd967d409f90, current wanted list, report history, issues, and the inbox. No reply to the DNS email; #292 remains the latest visible Item 5 ruling.
- Audited only post-review/later-fix surfaces: examples/no-node.md since review cutoff 2026-09-28 00:17 UTC; root README /v1/work changes through HEAD; examples/buy-from-nanogpt.md note revisions in 31da309 and follow-up fix b438d56; facilitator /settle documentation against current facilitator.js/x402.js behavior.
- no-node.md: current claims about the four-in-flight work limit, 503 before charge, GPU-first fallback, and maxTimeoutSeconds placement agree with workGenerate() and current server response code. Root README /v1/work GPU wording also matches workFor(). Root README /v1/fetch DNS refund claim still has the already-sent discrepancy from Block 028–029; exclude as duplicate.
- buy-from-nanogpt.md: the newly added 31da309 sentence says “a small seed is sometimes sent inside a held item.” The current wanted list says new Item 2(a) holds closed at 2026-09-28 12:00 UTC; only existing holds continue. This was logged as a near-miss, not a candidate: the sentence is non-committal (“sometimes”), and the page separately points readers with USDC/USDT to a working first-Nano route and then to no-node.md; available evidence did not establish that following the seed sentence necessarily causes a wrong result. The older NanoGPT recipe route/header text was not changed by these commits and has no eligible post-review provenance, so excluded even though current official NanoGPT docs now document accountless quotes at /api/v1/... with x-x402: true.
- Facilitator docs: current /settle page tells clients to check block status before retrying; recent code distinguishes definite rejection from uncertain transport failure and warns that a missing block may still arrive. No actionable documentation/code mismatch found.
- Duplicate check: current work log/report history, Item 5 wanted-list entries, and API issues were reviewed; no distinct new candidate duplicated by a prior report was found. No candidate ready. No email sent and no Nano spent.
- Scope limits: no paid requests, no Nano spend, and no destructive actions. This was a post-cutoff delta audit, not a line-by-line review of every eligible document. Next: Block 031 after fresh revalidation.


## Block 031 reconciliation (2026-09-29)

- Full facilitator `/settle` prose in current `facilitator.js` compared with current handlers and `x402.settle()`; the described timeout/polling, confirmation-timeout, hash checking, and same-block retry behavior agree with the source.
- The potentially unsafe “publish any block” cancellation instruction is not a new Item 5 candidate. It is present before the paid review, while later generic lost-reply changes do not affect the facilitator endpoint's call (the handler supplies no optional `landed` dependency). Record as a provenance-excluded legacy concern, not as a finding.
- Official Nano docs say competing blocks with the same previous hash are forks and that confirmation prevents replacement; no on-chain behavior was tested. No exact duplicate found in the register/issues search. No report sent; no Nano spent.
- Next: use the next eligible post-review document/code delta, or newly confirmed paid-review cutoff. Avoid reopening this passage unless a later relevant change makes the consequence new.


## Block 032 reconciliation (2026-09-29)

- Completed the requested line-by-line review of all `examples/no-node.md` instructions and examples against the current `server.js`, `x402.js`, and `examples/no-node.js`, plus official x402 v2 and Nano work-generation documentation.
- The last relevant text/code correction is the #323 work-limit fix in `b438d56`; its new wording matches current validation order, synchronous four-slot reservation, free/paid rate limits, GPU-first policy, fallback and breaker behavior. Later `7bfb2e2` changes the no-node script, not the Markdown guide, and no doc-to-current-code wrong-action chain was established.
- A `count: '100'` limit in `/v1/receivable` means a script receive run does not pocket more than the first 100 returned blocks. The same cap exists in endpoint-introduction commit `b947aa1` (2026-09-08), so this is a pre-review caveat and fails the Item 5 timing rule. It is retained in the map to prevent circular re-investigation.
- No matching duplicate issue was found; no report or Nano spend. See `docs/checkpoints/2026-09-29-block-032.md`.


### Block 033 — cutoff provenance (2026-09-29)

The stablecoin guide's own history begins after the homepage paid review. Its later edit is an evidence-only transaction addendum, and no paid review specific to this guide appears in the public log, report register, or Gmail searches. No cutoff can be asserted from the neighboring homepage review. The guide remains **open and not systematically audited**; do not report behavior findings until a document-specific paid-review cutoff/scope is established or an eligible later change appears.
