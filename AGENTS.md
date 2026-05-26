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

Use `program-pal-program-design` after assessment context is available and before creating the final workout workbook. This skill creates the Program Blueprint.

Use `program-pal-exercise-selection` when choosing, verifying, substituting, regressing, progressing, or explaining exercises inside a Program Pal workout.

Use `personal-training-workbook-format` when creating or formatting final Excel workout-program workbooks.
