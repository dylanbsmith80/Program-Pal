---
name: program-pal-client-memory
description: Retrieve, create, or update the private long-term memory for one Program Pal client. Use before answering client-specific questions or designing a new training cycle, and after assessments, trainer corrections, progress reports, or program milestones produce durable client facts.
---

# Program Pal Client Memory

Maintain one factual, private memory record per client so future Program Pal work can build on prior assessments, decisions, programs, and progress.

This skill manages durable client context. It does not replace the current assessment, the intake-readiness gate, program design, or the trainer's judgment. Conversation state is not client memory: retrieve the record again in a future task rather than assuming prior chat context is available.

## Storage Contract

Use the trainer's authenticated Google Drive and the existing Program Pal client-folder convention:

`Program pal/FirstNameLastInitial/Client Memory - FirstNameLastInitial`

Create the memory as a private Google Doc in the client's existing folder. Use `program-pal-google-drive-storage` to locate or create the root and client folder. Use the Google Drive or Google Docs connector for document reads and writes; use an authenticated Browser or Chrome session only when connector writes are unavailable.

The Google Doc is the authoritative record. Do not store real client memory, exports, cached copies, or health details in GitHub. The repository contains only this reusable skill and its sanitized schema.

Non-sensitive shared facility context is the exception to the client-record rule. Read [references/facility-profiles.md](references/facility-profiles.md) when location or equipment affects a response, intake decision, Program Blueprint, exercise choice, or session flow. Unless the trainer explicitly names South Rec, use the North Rec default documented there. Do not copy the full facility inventory into every client memory document; store only durable client-specific location or equipment exceptions in the private record.

Do not change sharing permissions or generate a public link unless the trainer explicitly asks. If Drive access is unavailable, continue using facts supplied in the current task but report that persistent memory could not be read or updated. Do not silently substitute a repository file, Downloads folder, or another cloud provider.

## Identity Gate

Resolve the client before reading or writing memory.

- Derive `FirstNameLastInitial` only from the trainer's request or a supplied source.
- Ask for the last initial when it is not known and a folder or memory record must be created.
- If two clients could map to the same folder key, ask the trainer to disambiguate; do not guess.
- Search for the memory document only inside the resolved client folder.
- If more than one memory document exists there, do not merge or overwrite them until the trainer identifies the authoritative copy.

Never combine facts from similar names, adjacent folders, search snippets, or another client's program.

## Retrieve Memory

Retrieve memory before:

- answering a question about an existing client;
- evaluating readiness for a new program;
- creating a Program Blueprint;
- selecting exercises or progressions;
- interpreting a progress update; or
- revising an existing client program.

Read the whole memory document. Use the current items most relevant to the task, including active goals, safety constraints, preferences, schedule, equipment, training history, open questions, and the most recent program status.

After resolving the client's private memory, resolve facility context separately:

- Use an explicit location stated for the current task when available.
- Otherwise, apply the North Rec default from `references/facility-profiles.md`.
- Treat facility availability as shared planning context, not proof that a specific exercise is suitable for the client.
- When South Rec is explicitly named, do not import North Rec assumptions.

Treat the memory as evidence, not unquestionable truth:

- Prefer a newer, explicit trainer statement or dated assessment over an older entry.
- Surface conflicts that affect identity, safety, goals, scheduling, or program design.
- Do not remove an injury, pain flag, medical constraint, or exercise restriction merely because a newer source is silent about it.
- Treat items with old `last confirmed` dates as potentially stale and ask when freshness materially affects the answer.
- Keep required intake questions active even when memory is incomplete.

State briefly when memory materially influenced the answer or program. Do not expose the full private record unless the trainer asks to review it.

## Update Memory

Update memory when a task produces durable client facts, such as:

- a first assessment or corrected intake detail;
- a trainer-confirmed goal, limitation, preference, schedule, or equipment change;
- a progress report or measurable result;
- an approved Program Blueprint or programming decision;
- a program that has been prescribed, started, paused, or completed; or
- an unresolved question that should be asked next time.

Do not save model guesses, research claims, speculative diagnoses, or unapproved recommendations as client facts. Distinguish `planned`, `prescribed`, `in progress`, and `completed`; creating a workout file does not prove the client completed it.

For every update:

1. Load the current authoritative memory document before editing it.
2. Read [references/client-memory-schema.md](references/client-memory-schema.md) and preserve its section meanings.
3. Apply only facts supported by the trainer or an identified client source.
4. Record a date, source, and confirmation status for safety-critical or program-changing facts.
5. Move superseded facts into the history or decision log instead of erasing useful context.
6. Update `Last reviewed` and append a concise change-log entry.
7. Re-read the saved document and verify the client key, changed facts, and unresolved questions.

Ask before writing when the proposed change is ambiguous, conflicts with a safety-critical fact, or could belong to another client. A normal, unambiguous memory update that the trainer requested does not need a second confirmation.

## Privacy And Data Minimization

Store only information needed for safe, personalized programming. Do not add passwords, payment information, government identifiers, unrelated family details, or full contact records. Prefer the folder key and first name plus last initial over a full legal name.

Record health-related details only as supplied by the trainer or client source, using neutral language such as `trainer reported` or `assessment states`. Do not turn observations into diagnoses.

Never reveal, compare, or reuse one client's memory while working on another client. Never commit client memory to Git, an issue, a pull request, a test fixture, or an example.

## Completion Receipt

Report:

- `Memory status:` retrieved, created, updated, not found, or blocked;
- `Client:` the resolved folder key;
- `Location:` the private Drive path, without changing its permissions;
- `Used:` the categories that materially affected the work;
- `Updated:` the categories changed, or `None`; and
- `Needs confirmation:` unresolved or stale facts that could change future programming.

When facility context materially affects the work, also report `Facility used:` North Rec, South Rec, or Unknown.
