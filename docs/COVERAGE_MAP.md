# Coverage Map — Pursekeeper Item 5

**Last reconciled:** 2026-09-28, against Block 016, upstream HEAD `8bf1f3c6e02e87a123d74dba4dad1c1efe113538`, current wanted list, and Pursekeeper inbox.  
**Purpose:** Preserve where Item 5 hunts have looked, what they actually covered, and what remains without a systematic audit. This is a navigation aid, not proof that a document is currently accurate. Revalidate HEAD, diffs, live behavior, review cutoff, and duplicate status before each hunt.

## Coverage states

- **Targeted audit recorded** — a specific passage, changed diff, structure, or behavior was examined. This does not mean every line was audited.
- **Reported / fixed or credited** — a historical finding exists; do not reopen unless a later change creates a distinct error.
- **Open — not systematically audited** — the work log does not show a dedicated Item 5 audit. It may still have been opened incidentally.
- **Out of Item 5 scope by default** — evidence/research artifacts that are not reader-facing Pursekeeper service instructions. Reconsider only if a later change makes them operational instructions.

## Audited or previously reported surfaces

| Surface | Recorded coverage | Current handling |
|---|---|---|
| Repository `README.md` | Prior review and bounty wording; Block 013 compared the x402 settled-hash sentence with the later `/v1/fetch` credit-return code. | Block 013 report was sent once and awaits decision. Do not resend. Check for a later ruling/fix and inspect only new changes. |
| `examples/no-node.md` | Paid reports #228, #279 and credited #281 are recorded. Blocks 010–011 checked post-review `8bf1f3c` wording against source and unpaid live 402/error responses. | Reopen only for a new post-cutoff change or later fix. |
| `examples/buy-from-nanogpt.md` | Block 009 checked post-review edits, two unpaid quotes, and the linked evidence; older header differences were excluded by cutoff. | Targeted delta review, not a complete line-by-line audit. |
| `examples/purchases/README.md` | Historical accepted report #266 covered the seller-first `/v1/work` flow. | Reopen only if a later change affects the instructions. |
| `examples/research/README.md` | Historical accepted reports and the paid #285 cross-surface timing contradiction; Block 006 checked table/link structure; later ruling rows were compared with public decision data. | Ledger/index and selected changed rows were checked, not every linked research report or evidence file. |
| Generated `/` and `/api` text | Historical paid #282 checked the x402 hand-back claim; Block 012 traced later `dd419256` redirect wording against `fetchText()` and the 400 path. | Previously reported/fixed area; any new report needs a distinct post-fix error and consequence. |
| `/facilitator` | Historical accepted report #269; `ab1799a` fixed seller labels. Block 006 also made two unauthenticated body-size probes. | No later relevant reopening recorded through Block 014. |
| `/sellers`, `/offers`, `/sellers.json` | Historical accepted reports #266/#275 and one `checked_at` lead marked not reproduced; later seller-flow diffs were revisited in Block 014. | Search prior rulings first; do not revive stale or duplicate leads without new evidence. |
| Endpoint/docs behavior: `/v1/requests`, `/v1/process`, `/v1/fetch`, `/v1/hash`, `/v1/credit`, `/.well-known/x402` | Covered in specific historical reports/probes, including paid reports #266/#275/#276/#282 and current no-node/API checks. | Coverage is finding-specific, not an exhaustive endpoint audit. Revalidate source and current public behavior. |
| Homepage campaign date and paid-work GPU wording | Block 014 checked provenance/cutoff; campaign text predated its paid-review cutoff, GPU wording also predates review. | Excluded for timing. Do not re-open without a later relevant text/code change. |

## Open areas — no dedicated Item 5 audit recorded

These are candidates for **cutoff discovery first**, not automatic report targets. Item 5 eligibility still requires a substantiated paid-review/fix cutoff and a later relevant diff.

| Surface | Next useful step |
|---|---|
| `BOUNTY.md` | Block 016 checked its path history: the latest listed change is `0b5151bc` on 2026-09-10 06:22:54 UTC; no newer change was found at current HEAD. No candidate-specific paid-review cutoff was established in the log. Revisit only if a later relevant change appears or a cutoff is substantiated. |
| `examples/get-nano-from-stablecoins.md` | Added by `eed1502` on 2026-09-25 21:16:27 UTC; no later edit appears in its path history at HEAD. The guide was read for provenance/scope, but no guide-specific paid review was found in the register/index. Its cutoff is unresolved, so no behavioral candidate was tested or qualified in Block 016. Reopen when its cutoff or a relevant post-cutoff change is established. |
| Individual `examples/purchases/*/README.md` files | Check each file's own cutoff and changed passages. The parent purchases README's paid review does not automatically cover these separate documents. |
| Purchase evidence JSON/TXT and scripts | Do not treat raw evidence as Item 5 instructions by default. Inspect only if a document points readers to it as an operational step or later text turns it into guidance. |
| Individual `examples/research/*.md` reports and research evidence folders | These are generally Item 2(a) research/evidence, not Item 5 service docs. Do not bulk-audit as Item 5. Reclassify a specific file only if it contains reader-facing service instructions and has an eligible post-review change. |
| Other public site pages/routes | No systematic page-by-page audit is recorded beyond the named homepage, `/api`, `/facilitator`, `/sellers`, and `/offers` surfaces. Inventory routes, find the applicable review cutoff, and prioritize changed reader instructions. |

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
