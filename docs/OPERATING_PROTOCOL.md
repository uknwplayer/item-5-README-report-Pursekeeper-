# Operating Protocol — Pursekeeper Item 5

## Current payout rule and boundaries

**Effective cutoff:** upstream commit `d7b69a3c4af32e47fbbefdcba0390a799549f39a`, published 2026-09-29 07:24 UTC. This supersedes the earlier document-review/later-fix eligibility rule for future reports. Documentation-only mistakes may be fixed and credited by Pursekeeper, but they are unpaid. Do not spend hunt time on them.

Investigate only a concrete, reproducible financial-loss path within Item 5. The current rule pays Ӿ5 to the first report for a path, under a documented configuration, against the live service, facilitator, `no-node.js`, or the skill's scripts, by which:

- a payer or Pursekeeper makes a transfer the payer did not authorize;
- the same payment is settled twice;
- a payment below the listed price is accepted as settled; or
- credit/refund is retained and never returned.

The path may be demonstrated from source with the execution path named, or with a test payment made by the reporter; nobody should lose real funds to qualify. Temporary unavailability does not qualify. Payment is per independently fixable root cause, regardless of how many files/routes expose it; later duplicates are credited. Reports already in Pursekeeper's inbox at the cutoff are handled under the old rule.

In-scope execution surfaces are the live service, facilitator, `no-node.js`, and skill scripts, including documentation only when following a specific instruction causes one of the financial outcomes above. Do not investigate ordinary documentation accuracy, availability-only failures, style, feature requests, general security issues outside these outcomes, or unrelated bounty categories.

## Required sequence

### 1. Register and resume work

Every planned future task, active investigation, report draft, and follow-up must have a row in [WORK_LOG.md](WORK_LOG.md) before work begins. At resume, check the current checkpoint and work log first, then read [COVERAGE_MAP.md](COVERAGE_MAP.md) before choosing the target. Continue an existing work ID when possible.

Keep each work item in the register through its entire lifecycle: planned, in progress, candidate rejected, report awaiting decision, accepted/paid, credited, not reproduced, declined, withdrawn, or closed with no finding. Record the next action.


### 1a. Use the accumulated coverage record

The coverage map is a required input to every hunt, not an optional summary.

- Consult its audited, previously reported/fixed, and open entries before selecting a document. Cross-check them against the current work log, wanted list, inbox, and upstream history; the map can be stale.
- Use prior coverage to avoid duplicate work, but the old per-document paid-review cutoff is no longer a condition for a new financial-loss report. Do not reopen a surface just to search for a documentation-only mismatch.
- Check prior rejected/inconclusive leads before testing so the same unsupported theory is not rediscovered.
- At the end of every block, record the exact surface and scope examined, cutoff/commit, evidence and reproduction, disposition, and remaining open areas in both the work log/checkpoint and the coverage map.
- Use precise status language: “targeted audit” means only the recorded passage/diff/behavior was checked; do not claim a whole document or endpoint was fully audited unless the work log shows that complete scope.
- Prioritize money-flow traces: **documented configuration/request → charge/credit/settlement path → concrete unauthorized transfer, double settlement, underpayment, or permanently missing credit/refund**. Recent commits are useful leads, but an eligible financial defect can predate the policy cutoff.

### 2. Revalidate current state

Before examining candidates, establish fresh evidence for:
- the current HEAD of `pursekeeper/api`;
- the current wanted list and its latest edits;
- recent commits, including author/time and the relevant diffs;
- current documentation text and live behavior where applicable;
- prior reports, issues, fixes, and decisions that may make a candidate duplicate or already resolved.

Record the date/time and exact commit identifiers in the checkpoint and relevant work-log row. Never treat a prior chat summary as current repository state.

### 3. Establish eligibility and provenance

Confirm the current Item 5 rule and its publication cutoff from the live wanted list and commit history. For each candidate, identify the exact documented configuration and complete source execution path, and establish that the current code still permits the financial outcome. A post-review document cutoff is not required by the current rule; record introducing commit/time when useful for provenance, but do not reject an otherwise qualifying money-loss path solely because it is old.

### 4. Compare documentation with reality

Trace the exact instruction through:
- the cited document;
- implementation code and relevant commit history;
- endpoint behavior or public JSON when useful;
- official upstream documentation only when the finding depends on it.

Prefer a low-cost, read-only reproduction such as `curl`, `grep`, a public JSON response, or a small local code-path check. Do not make paid Nano calls unless they are indispensable and explicitly approved. Avoid destructive tests.

### 5. Prove financial consequence

Name the exact action/request/configuration and trace what happens to funds or payment credit. The demonstrated result must be one of the four paid outcomes listed above. Source tracing is acceptable when it fully proves the execution path; use a low-cost read-only or local test when it strengthens the proof. Never send a real payment just to test a theory.

Do not report grammar/formatting, ambiguity, wrong results without one of the listed financial outcomes, availability failures, already fixed paths, duplicates, or theoretical outcomes unsupported by a complete source path or reproduction.

### 6. Check duplicates and estimate confidence

Check the wanted list, prior sent reports/replies, issue tracker, relevant commits/changelogs, and known fixes/reports by others. Record what was searched and why the candidate is distinct.

Assign a confidence score:
- **High (8–10/10):** exact post-cutoff diff, current doc/code mismatch, and cheap reproduction align.
- **Medium (5–7/10):** actionable mismatch is likely, but one evidence link or live confirmation is incomplete.
- **Low (0–4/10):** timing, consequence, or implementation behavior is speculative.

Only high-confidence candidates with a complete evidence chain and an eligible financial outcome should be presented for submission. Preserve rejected candidates in WORK_LOG with the reason, so they are not rediscovered as new work.

### 7. Present before sending and record the outcome

Prepare one English report for the operator, containing one document and one finding. Do not send it automatically. Send only when the operator explicitly says **“Enviar”**; then send the approved report once to `agent@pursekeeper.dev`.

Before sending, update the work item to **Awaiting decision** and record the exact subject and sent timestamp/message reference. When the reply arrives, record the outcome distinctly: accepted/paid, confirmed/credited, duplicate/declined, not reproduced, rejected, or still awaiting decision. Do not infer acceptance or payment from a fix alone.

After a confirmed acceptance/fix, update the cutoff to the new commit. If the fix introduces a new possible error, reopen only the affected document and inspect the new post-fix changes.

## Required report structure

Follow [REPORT_TEMPLATE.md](REPORT_TEMPLATE.md). A complete report includes operator, one root cause and its documented configuration/source path, exact relevant quotation when documentation is part of the path, reproduction or source trace, observed financial outcome, practical consequence, provenance/timing, confidence, duplicate checks, and payout address.

Use the subject:
`Item 5 report — [short error description] — uknwplayer`

## Work-block discipline

At the end of every investigation block, update both [WORK_LOG.md](WORK_LOG.md) and [the current checkpoint](checkpoints/CHECKPOINT_CURRENT.md), including when no qualifying candidate is found, a candidate is rejected, or work is blocked.
