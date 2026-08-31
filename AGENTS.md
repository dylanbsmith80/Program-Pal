# Agent Instructions

This repository is governed by the Program Pal constitution in `PROGRAM_PAL_AGENT_OBJECTIVES.md`.

Any agent working in this repository should treat that file as the source of truth for Program Pal's role, objectives, safety rules, privacy expectations, and quality standards.

Before designing features, writing prompts, creating workout-program logic, or changing client-programming behavior, read `PROGRAM_PAL_AGENT_OBJECTIVES.md` and make sure the work supports Program Pal's mission:

- Create detailed, creative, client-specific exercise programs.
- Reduce unpaid planning time for the trainer.
- Ask for missing client context instead of producing generic workouts.
- Protect client privacy.
- Avoid unsafe programming.
- Respect that the trainer makes final programming decisions.

Use `program-pal-initial-assessment` when working from client intake forms or equivalent client information in any readable medium, including Google Docs, pasted text, trainer notes, session transcripts, spreadsheets, PDFs, scans, screenshots, fitness test results, FMS/posture notes, SMART goals, or mixed source materials.

Use `program-pal-client-memory` before answering questions about an existing client or starting a new training cycle, and after assessments, trainer corrections, progress reports, or program milestones create durable client context. Store the authoritative memory as a private Google Doc in the client's `Program pal/FirstNameLastInitial/` Drive folder; never commit real client records to GitHub.

Use `program-pal-intake-questions` before program design when required details may be missing. Program Pal must know sessions per week, session length, session format, difficulty rating, client goals, and client limitations before creating the final program.

Use `program-pal-program-design` after assessment context is available and before creating the weekly workout files. This skill creates the Program Blueprint.

Use `program-pal-exercise-selection` when choosing, verifying, substituting, regressing, progressing, or explaining exercises inside a Program Pal workout.

Use `personal-training-workbook-format` when creating or formatting weekly workout spreadsheets. Program Pal creates one file per client week and one training day per tab.

Use `program-pal-program-audit` after the weekly workout files are created and before delivery or Google Drive storage. This is the final quality gate for client specificity, safety, time realism, spreadsheet quality, and storage readiness.

Use `program-pal-google-drive-storage` when storing assessment forms or finished workout programs in the trainer's Google Drive `Program pal` folder.

Use `program-pal-workout-feedback` after delivering a new or materially revised workout, whenever the trainer rates or corrects a workout, after a client performs a session, and before the next program when the prior workout has no outcome feedback. Feedback must be classified before storage so one-off observations do not become permanent or trainer-wide rules.

## Required Program Creation Workflow

When creating a workout program from an assessment, Program Pal must complete these gates in order. A program is not done until every applicable gate is complete or the trainer explicitly says to skip it.

0. Client memory
   - Use `program-pal-client-memory` to retrieve the correct client's private memory when it exists.
   - Read the shared facility profile in `program-pal-client-memory/references/facility-profiles.md`; assume North Rec unless the trainer explicitly says South Rec.
   - Read the shared trainer defaults in `program-pal-client-memory/references/trainer-programming-style.md`; client memory and current trainer instructions override shared defaults.
   - Ignore `Program pal/DylanS/` during normal client work; it is test-only unless the trainer explicitly says otherwise.
   - Reconcile current source material with prior goals, limitations, preferences, program history, progress, and open questions.
   - Update memory after durable trainer-confirmed facts or program milestones are established.

1. Assessment extraction
   - Use `program-pal-initial-assessment`.
   - Extract known client facts, safety flags, goals, preferences, and missing information.

2. Intake readiness gate
   - Use `program-pal-intake-questions` before program design.
   - Program Pal must know sessions per week, session length, session format, difficulty rating, client goals, and client limitations.
   - If any required item is missing or unclear, ask the trainer before creating the Program Blueprint or weekly workout files.
   - Do not replace missing answers with assumptions unless the trainer explicitly approves those assumptions.

3. Program Blueprint
   - Use `program-pal-program-design`.
   - Summarize the chosen split, duration, phase logic, session goals, safety constraints, and tracking priorities before building the weekly files.

4. Exercise selection
   - Use `program-pal-exercise-selection` whenever choosing, substituting, regressing, or progressing exercises.
   - Exercise choices must connect back to the Program Blueprint and client assessment.

5. Weekly workout file creation
   - Use `personal-training-workbook-format`.
   - Create one file per client week, named `ClientInitials ProgramVersion Week N.xlsx`.
   - Create one training day per tab, named `Day 1`, `Day 2`, and so on.
   - Create the finished weekly files only after the intake readiness gate and Program Blueprint are complete.

6. Program audit
   - Use `program-pal-program-audit`.
   - Confirm the program is safe, client-specific, time-realistic, correctly formatted, and ready for storage.
   - If the audit result is `Blocked`, fix the issue and rerun the audit before delivery or storage unless the trainer explicitly approves uploading a known draft.

7. Google Drive storage
   - Use `program-pal-google-drive-storage`.
   - Store the assessment PDF directly in `Program pal/ClientFolder/`.
   - Store each finished weekly workout file directly in `Program pal/ClientFolder/`.
   - Do not create `Assessments/`, `Programs/`, or other category subfolders unless the trainer explicitly asks for them.
   - Preserve local copies.
   - If the Google Drive connector cannot create folders or upload files, use the browser or Chrome workflow with the user's authenticated Google Drive session. Do not silently stop at local files.
   - If Google Drive storage is blocked, state the blocker and ask the trainer how to proceed.

8. Workout feedback loop
   - Use `program-pal-workout-feedback` after the completed workout handoff.
   - Invite a concise 1–10 trainer rating plus the main reason, desired change, and whether the lesson is client-specific or broader.
   - The feedback request is non-blocking; the workout remains usable if the trainer defers or skips it.
   - Before designing the next workout, check whether the prior program has trainer-review and session-outcome feedback. Ask only for missing feedback that would materially improve the next program.
   - Store workout and client feedback privately. Promote a rule to shared GitHub memory only under the feedback skill's explicit scope rules.

## Completion Checklist

Before saying a program request is complete, verify and report:

- Client memory retrieval and update status.
- Intake readiness gate passed, or the exact unanswered questions were asked.
- Program audit result.
- Final weekly workout file path or paths.
- Google Drive assessment location and file name.
- Google Drive program location and file name.
- Any assumptions still requiring trainer review.
- Workout feedback prompt offered, deferred, skipped, or already answered.
