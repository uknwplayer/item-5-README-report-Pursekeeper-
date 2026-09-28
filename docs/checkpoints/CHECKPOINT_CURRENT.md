# Current Checkpoint — Pursekeeper Item 5 README Reports

**Date:** 2026-09-27 / 2026-09-28 UTC  
**Block:** 010 — Post-review documentation audit  
**State:** CLOSED / NO QUALIFYING FINDING / NO REPORT PENDING

## Revalidation

- Block 009 confirmed upstream main HEAD `dd419256bd5a741887d680fa801bdcf9b5035a93` (2026-09-27 20:00:11 UTC) and found no newer Pursekeeper email than the 20:01:08 UTC ruling (`1a0e4753adf9dbc7`). The wanted-list and prior report record were re-read.

- Upstream pursekeeper/api main HEAD remained `dd419256bd5a741887d680fa801bdcf9b5035a93` (2026-09-27 20:00:11 UTC).
- Re-read current wanted-list rules, work log, relevant paid and credited reports, and Gmail. No commit or Pursekeeper email newer than the previously reviewed 20:01:08 UTC reply was found.
- The prior report's outcome is settled: email `1a0e4753adf9dbc7` says its main claim was wrong but the cross-surface timing contradiction was real; Pursekeeper paid Ӿ1 under ledger #285. Public `/log.json` now has decision #463 correcting decision #459's 17:42 time.

## Changed surfaces and reproduction

GitHub's changed-file inventory for `dd419256` lists `examples/no-node.js`, `examples/no-node.md`, the Copperglass QA research report, `examples/research/README.md`, and `server.js`. All five were inspected.

- **Live docs:** unauthenticated GET `/api` returned 200 and serves the widened redirect hand-back explanation. GET `/examples/no-node.md` returned 200 and serves the updated x402 paragraph.
- **Redirect docs vs implementation:** the source loop permits five redirect hops and refuses a sixth, a missing Location, or a next URL rejected by `checkFetchUrl`. It hands the paid amount back on the block hash and includes that hash in the 400 note as described. Existing paid #282 is duplicate context.
- **x402:** the no-node example matches the official Nano `exact` scheme and a free live unpaid POST to `/v1/hash`: HTTP 402 with decoded x402 v2 `PAYMENT-REQUIRED`, scheme `exact`, network `nano:mainnet`, the documented raw amount/payTo, and `extra.work: optional`. The `PAYMENT-SIGNATURE` structure is accepted + payload.block. No Nano spent.
- **no-node.js:** the retry derives open/receive from the rebuilt block and checks a pending send again after refresh. Its adjacent note that these fixes are present matches the code.
- **Copperglass postscript:** compared with live Speedbot collaboration guide and `/api/launch`. Directed-test limit is one per operator and wallet, maximum six funded runs per service, 72-hour provider window, and submission alone does not approve or reserve a reward. Wording matches.
- **Research README:** added ruling/chronology rows were checked against the email, ledger, decision #463 and live service log. No actionable structural or factual mismatch found.
- Targeted GitHub issue search for the timing/x402 content found no duplicate report. Other matches were unrelated existing seller discussions.

## Outcome

No qualifying document-to-current-behavior mismatch with a concrete reproducible wrong-action result. No report drafted or sent. No Nano spent. No Item 5 report is awaiting a decision.

## Next

- `NEXT-ITEM-5-AFTER-007` is closed with no qualifying finding.
- `NEXT-ITEM-5-AFTER-008` is planned. Revalidate HEAD, inbox, wanted-list rules, document cutoffs, live behavior and duplicate reports at the next hunt.
- Payout address: `nano_1zwik4hd1pjy73owfah8xuxzokk6zexc5a6rs6byhrxryggkbh38kemm51yt`

## Block 009 — eligible NanoGPT guide edit

The paid NanoGPT/facilitator QA cutoff is 2026-09-10. `examples/buy-from-nanogpt.md` was edited on 2026-09-18 in `432f34f` (adds the same-quote warning) and `ca19562` (adds only an evidence-gist link). The warning was the sole substantive eligible change. Two unpaid POSTs to `https://nano-gpt.com/api/x402/v1/chat/completions` returned HTTP 402 with distinct Nano `payTo`, `paymentId`, and `completeUrl` values. That live quote rotation supports the instruction to complete the original payment ID/URL and not re-quote after sending. The linked pyfile-toolkit report already documents this behavior; no new mismatch is present.

The guide's older sentence describing `X-Payment-Address`, `X-Payment-Amount`, and `X-Payment-Id` headers differs from today's live response, but that sentence predates the 2026-09-10 paid review. Its provenance fails the post-review timing gate, so it was excluded. No candidate prepared or sent. No Nano spent.

## Outcome and next

`NEXT-ITEM-5-AFTER-008` is closed with no qualifying finding. `NEXT-ITEM-5-AFTER-009` is planned: at the next hunt, revalidate HEAD, mailbox, wanted list, per-document cutoffs and all new actionable documentation changes before testing.



## Block 010 start (2026-09-27 22:30 America/Sao_Paulo / 2026-09-28 01:30 UTC)

Revalidated upstream main at `8bf1f3c6e02e87a123d74dba4dad1c1efe113538` (2026-09-28 00:24:47 UTC), reread the current wanted-list rules, and searched the Pursekeeper mailbox. A new email at 00:26:34 UTC (`1a0e568152323871`) concerns item 2(a) hold releases; read it before proceeding. The prior Item 5 ruling remains the 20:01:08 UTC email (`1a0e4753adf9dbc7`). Next inspect the exact upstream commit diff and per-file cutoffs, then compare eligible documentation changes with current behavior and duplicates.

## Block 010 findings — post-review no-node update

Upstream pursekeeper/api main was revalidated at `8bf1f3c6e02e87a123d74dba4dad1c1efe113538` (2026-09-28 00:24:47 UTC). The latest mailbox item from Pursekeeper (`1a0e568152323871`, 00:26:34 UTC) concerns item 2(a) holds; there is no new Item 5 decision. The wanted-list still limits Item 5 to errors introduced after paid review/fix cutoffs.

`examples/no-node.md` was the only substantive eligible Item 5 documentation change in this commit. It followed a paid review at 00:17 UTC and clarifies seller-specific `extra`, timeout metadata, and where a refusal reason appears. A free initial `POST /v1/hash` returned 402 with `exact` / `nano:mainnet`, `maxTimeoutSeconds: 60`, and `extra.work: optional`. A second POST with an invalid empty block returned 402; the decoded `PAYMENT-REQUIRED.error` matched the JSON `error` exactly (`x402: payload.block is not a Nano state block`). No valid payment block or Nano was sent.

The `maxTimeoutSeconds` phrase was checked against the official x402 v2 specification and Pursekeeper's facilitator source (which caps its own confirmation polling at 30 seconds). The spec defines a maximum time allowed for payment completion; the no-node seller path does not use the facilitator poll and the new text says this is not a retry budget. No concrete wrong action/result was established, so it was not reported. No issue duplicate found; the 00:17 pyfile-toolkit report is the existing paid correction already cited by the new text.

No qualifying finding, no report prepared or sent, no Nano spent. `NEXT-ITEM-5-AFTER-009` is closed; `NEXT-ITEM-5-AFTER-010` is planned.
