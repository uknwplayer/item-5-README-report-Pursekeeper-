# Continuity Rules — Item 5 README Reports

These rules preserve work state across chats, operators, agents, and tool sessions.

## Language

Repository documentation, work log entries, reports, issues, and Pursekeeper correspondence are in English. Operator conversation may be in Portuguese.

## Resume order

At the start of every work block:

1. Read `docs/checkpoints/CHECKPOINT_CURRENT.md`.
2. Read `docs/WORK_LOG.md` and identify active, planned, or awaiting-decision work.
3. Revalidate any time-sensitive source state before using it.
4. Continue an existing work ID when applicable; do not create a duplicate work item.

## Work registration

Every task must be added to `docs/WORK_LOG.md` before work begins, including future tasks, candidate investigations, report preparation, and follow-up after a Pursekeeper decision. Update the row when work starts, pauses, changes scope, is rejected, is sent, receives a response, or closes.

Each row must carry a status and next action. Do not infer acceptance, rejection, or payment without a direct ruling.

## Checkpoint rule

Update `docs/checkpoints/CHECKPOINT_CURRENT.md` at the end of every work block. A work block includes:
- adding or changing documentation;
- starting, advancing, or closing a work item;
- making a material decision;
- completing a reproduction;
- sending or receiving a report;
- recording payment, credit, rejection, or non-reproduction.

The checkpoint must summarize this block and link to the relevant work-log ID and evidence.

## Evidence and outcomes

Preserve exact commits, relevant diff paths, timestamps, reproduction results, email subject/message reference, and ledger number where available. Mark unknown details as unknown. Keep payment, second-reporter credit, duplicate, not reproduced, rejected, withdrawn, and pending outcomes distinct.

Never state “paid” without a payment amount or reliable ledger/email confirmation. Never state “rejected” when the actual decision was only “not reproduced.”

## Safety and send-once rule

Do not send reports automatically. The operator must review the exact report and explicitly say “Enviar.” Send that reviewed report once to `agent@pursekeeper.dev`; register it as awaiting decision immediately. Store no wallet seed, private key, credential, token, or reusable payment header.
