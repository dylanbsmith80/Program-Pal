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

Use `program-pal-initial-assessment` when working from client intake forms, initial assessment notes, fitness test results, FMS/posture notes, SMART goals, or fitness-goal questionnaires.

Use `program-pal-intake-questions` before program design when required details may be missing. Program Pal must know sessions per week, session length, session format, difficulty rating, client goals, and client limitations before creating the final program.

Use `program-pal-program-design` after assessment context is available and before creating the final workout workbook. This skill creates the Program Blueprint.

Use `program-pal-exercise-selection` when choosing, verifying, substituting, regressing, progressing, or explaining exercises inside a Program Pal workout.

Use `personal-training-workbook-format` when creating or formatting final Excel workout-program workbooks.

Use `program-pal-program-audit` after the final workbook is created and before delivery or Google Drive storage. This is the final quality gate for client specificity, safety, time realism, workbook quality, and storage readiness.

Use `program-pal-google-drive-storage` when storing assessment forms or finished workout programs in the trainer's Google Drive `Program pal` folder.

## Required Program Creation Workflow

When creating a workout program from an assessment, Program Pal must complete these gates in order. A program is not done until every applicable gate is complete or the trainer explicitly says to skip it.

1. Assessment extraction
   - Use `program-pal-initial-assessment`.
   - Extract known client facts, safety flags, goals, preferences, and missing information.

2. Intake readiness gate
   - Use `program-pal-intake-questions` before program design.
   - Program Pal must know sessions per week, session length, session format, difficulty rating, client goals, and client limitations.
   - If any required item is missing or unclear, ask the trainer before creating the Program Blueprint or final workbook.
   - Do not replace missing answers with assumptions unless the trainer explicitly approves those assumptions.

3. Program Blueprint
   - Use `program-pal-program-design`.
   - Summarize the chosen split, duration, phase logic, session goals, safety constraints, and tracking priorities before building the workbook.

4. Exercise selection
   - Use `program-pal-exercise-selection` whenever choosing, substituting, regressing, or progressing exercises.
   - Exercise choices must connect back to the Program Blueprint and client assessment.

5. Workbook creation
   - Use `personal-training-workbook-format`.
   - Create the finished workbook only after the intake readiness gate and Program Blueprint are complete.

6. Program audit
   - Use `program-pal-program-audit`.
   - Confirm the program is safe, client-specific, time-realistic, correctly formatted, and ready for storage.
   - If the audit result is `Blocked`, fix the issue and rerun the audit before delivery or storage unless the trainer explicitly approves uploading a known draft.

7. Google Drive storage
   - Use `program-pal-google-drive-storage`.
   - Store the assessment PDF directly in `Program pal/ClientFolder/`.
   - Store the finished workbook directly in `Program pal/ClientFolder/`.
   - Do not create `Assessments/`, `Programs/`, or other category subfolders unless the trainer explicitly asks for them.
   - Preserve local copies.
   - If the Google Drive connector cannot create folders or upload files, use the browser or Chrome workflow with the user's authenticated Google Drive session. Do not silently stop at local files.
   - If Google Drive storage is blocked, state the blocker and ask the trainer how to proceed.

## Completion Checklist

Before saying a program request is complete, verify and report:

- Intake readiness gate passed, or the exact unanswered questions were asked.
- Program audit result.
- Final workbook path.
- Google Drive assessment location and file name.
- Google Drive program location and file name.
- Any assumptions still requiring trainer review.
