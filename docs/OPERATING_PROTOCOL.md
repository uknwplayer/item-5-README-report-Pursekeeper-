# Operating Protocol — Pursekeeper Item 5

## Purpose and boundaries

Investigate only actionable documentation errors eligible under Pursekeeper Item 5. The target is a reader-facing instruction or claim that leads a reasonable reader to an incorrect action or result when followed against the current implementation or live service.

In-scope surfaces may include:
- `pursekeeper.dev` documentation and live `/api` text;
- `no-node.md`;
- `buy-from-nanogpt.md`;
- facilitator documentation;
- a document reopened by code or documentation changes made after its last paid review.

Do not broaden an Item 5 investigation into general security testing, feature requests, style edits, or unrelated bounty categories.

## Required sequence

### 1. Revalidate current state

Before examining candidates, establish fresh evidence for:
- the current HEAD of `pursekeeper/api`;
- the current wanted list and its latest edits;
- recent commits, including author/time and the relevant diffs;
- current documentation text and live behavior where applicable;
- prior reports, issues, fixes, and decisions that may make a candidate duplicate or already resolved.

Record the date/time and exact commit identifiers in the checkpoint. Never treat a prior chat summary as current repository state.

### 2. Establish the review cutoff

For each document, identify the most recent paid review or fix that establishes its cutoff. Then inspect only changes made after that cutoff for the candidate error.

The proof should include:
- the cutoff review/fix and its commit or reliable timestamp;
- the later commit that introduced the discrepancy;
- commit timestamp and relevant diff;
- confirmation that the wording/behavior remains present now.

If a review cutoff cannot be substantiated, mark the candidate blocked or unverified; do not imply provenance.

### 3. Compare documentation with reality

Trace the exact instruction through:
- the cited document;
- implementation code and relevant commit history;
- endpoint behavior or public JSON when useful;
- official upstream documentation only when the finding depends on it.

Prefer a low-cost, read-only reproduction such as `curl`, `grep`, a public JSON response, or a small local code-path check. Do not make paid Nano calls unless they are indispensable and explicitly approved. Avoid destructive tests.

### 4. Prove practical consequence

State what a reader following the exact sentence does and what actually happens. The consequence must be concrete and reproducible: for example, an operation fails, credits are unavailable, a command targets the wrong resource, or the documented recovery path cannot work.

Do not report:
- grammar or formatting;
- ambiguity without a demonstrated consequence;
- a behavior that existed before the applicable cutoff;
- an issue already fixed or already reported;
- a theoretical outcome unsupported by reproduction or code.

### 5. Check for duplicates

Search all available sources before preparing a candidate:
- the current wanted list;
- prior sent reports and replies;
- issue tracker;
- relevant commits and changelogs;
- known fixes and reports from other operators, where visible.

Record what was searched, what matched, and why this finding is distinct. If the same issue was reported earlier by someone else, disclose that and do not present it as an original paid candidate.

### 6. Estimate confidence

Assign a confidence estimate and explain its basis:
- **High (8–10/10):** exact post-cutoff diff, current doc/code mismatch, and cheap reproduction all align.
- **Medium (5–7/10):** actionable mismatch is likely, but one evidence link or live confirmation is incomplete.
- **Low (0–4/10):** timing, consequence, or implementation behavior is speculative.

Only high-confidence candidates with a complete evidence chain should be proposed for submission. Medium candidates need more verification; low candidates should be discarded.

### 7. Present before sending

Prepare one English report for the operator, containing one document and one finding. Do not send it automatically. The operator reviews the candidate first. Send only when the operator explicitly says **“Enviar”**; then send the approved report once to `agent@pursekeeper.dev`.

After a confirmed acceptance/fix, update the cutoff to the new commit. If the fix introduces a new possible error, reopen only the affected document and inspect the new post-fix changes.

## Required report structure

Follow [REPORT_TEMPLATE.md](REPORT_TEMPLATE.md). A complete report includes:
1. operator;
2. one document;
3. one finding;
4. exact quotation;
5. reproduction;
6. observed result;
7. why the result contradicts the document;
8. practical consequence;
9. provenance and timing;
10. payout address.

Use the standard subject:
`Item 5 report — [short error description] — uknwplayer`

## Work-block discipline

At the end of every investigation block, update [the current checkpoint](checkpoints/CHECKPOINT_CURRENT.md), even when the outcome is no finding or blocked. Keep an auditable distinction between verified fact, inference, and open question.
