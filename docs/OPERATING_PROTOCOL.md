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

### 1. Register and resume work

Every planned future task, active investigation, report draft, and follow-up must have a row in [WORK_LOG.md](WORK_LOG.md) before work begins. At resume, check the current checkpoint and work log first, then read [COVERAGE_MAP.md](COVERAGE_MAP.md) before choosing the target. Continue an existing work ID when possible.

Keep each work item in the register through its entire lifecycle: planned, in progress, candidate rejected, report awaiting decision, accepted/paid, credited, not reproduced, declined, withdrawn, or closed with no finding. Record the next action.


### 1a. Use the accumulated coverage record

The coverage map is a required input to every hunt, not an optional summary.

- Consult its audited, previously reported/fixed, and open entries before selecting a document. Cross-check them against the current work log, wanted list, inbox, and upstream history; the map can be stale.
- Prefer an eligible post-review documentation diff or a document reopened by a later fix. A surface marked open is only a lead: first prove its applicable paid-review/fix cutoff and a relevant later change. Never bypass Item 5's cutoff rule to fill a coverage gap.
- Check prior rejected/inconclusive leads before testing so the same unsupported theory is not rediscovered.
- At the end of every block, record the exact surface and scope examined, cutoff/commit, evidence and reproduction, disposition, and remaining open areas in both the work log/checkpoint and the coverage map.
- Use precise status language: “targeted audit” means only the recorded passage/diff/behavior was checked; do not claim a whole document or endpoint was fully audited unless the work log shows that complete scope.
- Preserve the strongest proven search pattern as first priority: **post-review commit → stale or contradictory reader-facing instructions → current code/live behavior → reproducible wrong result**.

### 2. Revalidate current state

Before examining candidates, establish fresh evidence for:
- the current HEAD of `pursekeeper/api`;
- the current wanted list and its latest edits;
- recent commits, including author/time and the relevant diffs;
- current documentation text and live behavior where applicable;
- prior reports, issues, fixes, and decisions that may make a candidate duplicate or already resolved.

Record the date/time and exact commit identifiers in the checkpoint and relevant work-log row. Never treat a prior chat summary as current repository state.

### 3. Establish the review cutoff

For each document, identify the most recent paid review or fix that establishes its cutoff. Then inspect only changes made after that cutoff for the candidate error.

The proof should include:
- the cutoff review/fix and its commit or reliable timestamp;
- the later commit that introduced the discrepancy;
- commit timestamp and relevant diff;
- confirmation that the wording/behavior remains present now.

If a review cutoff cannot be substantiated, mark the candidate blocked or unverified; do not imply provenance.

### 4. Compare documentation with reality

Trace the exact instruction through:
- the cited document;
- implementation code and relevant commit history;
- endpoint behavior or public JSON when useful;
- official upstream documentation only when the finding depends on it.

Prefer a low-cost, read-only reproduction such as `curl`, `grep`, a public JSON response, or a small local code-path check. Do not make paid Nano calls unless they are indispensable and explicitly approved. Avoid destructive tests.

### 5. Prove practical consequence

State what a reader following the exact sentence does and what actually happens. The consequence must be concrete and reproducible: for example, an operation fails, credits are unavailable, a command targets the wrong resource, or the documented recovery path cannot work.

Do not report grammar/formatting, ambiguity without a demonstrated consequence, behavior that predates the cutoff, an issue already fixed or reported, or a theoretical outcome unsupported by reproduction or code.

### 6. Check duplicates and estimate confidence

Check the wanted list, prior sent reports/replies, issue tracker, relevant commits/changelogs, and known fixes/reports by others. Record what was searched and why the candidate is distinct.

Assign a confidence score:
- **High (8–10/10):** exact post-cutoff diff, current doc/code mismatch, and cheap reproduction align.
- **Medium (5–7/10):** actionable mismatch is likely, but one evidence link or live confirmation is incomplete.
- **Low (0–4/10):** timing, consequence, or implementation behavior is speculative.

Only high-confidence candidates with a complete evidence chain should be presented for submission. Preserve rejected candidates in WORK_LOG with the reason, so they are not rediscovered as new work.

### 7. Present before sending and record the outcome

Prepare one English report for the operator, containing one document and one finding. Do not send it automatically. Send only when the operator explicitly says **“Enviar”**; then send the approved report once to `agent@pursekeeper.dev`.

Before sending, update the work item to **Awaiting decision** and record the exact subject and sent timestamp/message reference. When the reply arrives, record the outcome distinctly: accepted/paid, confirmed/credited, duplicate/declined, not reproduced, rejected, or still awaiting decision. Do not infer acceptance or payment from a fix alone.

After a confirmed acceptance/fix, update the cutoff to the new commit. If the fix introduces a new possible error, reopen only the affected document and inspect the new post-fix changes.

## Required report structure

Follow [REPORT_TEMPLATE.md](REPORT_TEMPLATE.md). A complete report includes operator, one document, one finding, exact quotation, reproduction, observed result, why it is wrong, practical consequence, provenance/timing, confidence, duplicate checks, and payout address.

Use the subject:
`Item 5 report — [short error description] — uknwplayer`

## Work-block discipline

At the end of every investigation block, update both [WORK_LOG.md](WORK_LOG.md) and [the current checkpoint](checkpoints/CHECKPOINT_CURRENT.md), including when no qualifying candidate is found, a candidate is rejected, or work is blocked.
