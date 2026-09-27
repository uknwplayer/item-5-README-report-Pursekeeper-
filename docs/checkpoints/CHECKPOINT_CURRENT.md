# Current Checkpoint — Pursekeeper Item 5 README Reports

**Date:** 2026-09-27  
**Block:** 008 — Post-cutoff Item 5 documentation review  
**State:** CLOSED / NO QUALIFYING FINDING / NO REPORT PENDING

## Revalidation

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
