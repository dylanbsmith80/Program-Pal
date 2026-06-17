---
name: program-pal-program-audit
description: Use after Program Pal creates or revises a final workout workbook, and before delivery or Google Drive storage, to audit the program for client specificity, safety, workflow compliance, time realism, workbook quality, and storage readiness.
---

# Program Pal Program Audit Skill

Use this skill as the final quality gate for Program Pal workout programs.

This skill does not design the program, select exercises, format the workbook, or upload files. It checks whether the completed draft is ready for trainer review and storage.

## When To Use

Use this skill after:

- `program-pal-initial-assessment`
- `program-pal-intake-questions`
- `program-pal-program-design`
- `program-pal-exercise-selection`
- `personal-training-workbook-format`

Use it before:

- Delivering the final program to the trainer
- Uploading the finished workbook with `program-pal-google-drive-storage`
- Saying the program request is complete

If the trainer explicitly asks to skip audit, report that the audit was skipped and name any obvious residual risk.

## Audit Inputs

Review the available materials:

- Assessment brief or prior client context
- Intake readiness output
- Program Blueprint
- Exercise choices and rationale
- Finished workbook or workbook-generation script
- Trainer constraints, preferences, dislikes, and storage requirements

Do not audit from the workbook alone when assessment or trainer context is available.

## Required Audit Checks

### 1. Intake And Workflow Gate

Confirm:

- Intake readiness gate passed, or trainer explicitly approved assumptions
- Program Blueprint exists before the workbook
- Exercise choices align with the blueprint
- Workbook was created after the design and selection gates

### 2. Client-Specific Fit

Check that the program reflects:

- Primary and secondary goals
- Assessment findings
- Safety flags, pain notes, and movement limitations
- Schedule, session length, equipment, and difficulty target
- Exercise preferences and disliked movements
- Prior progress or previous-program notes when available

Flag generic workouts, unrelated exercises, or missing rationale.

### 3. Safety And Substitution Check

Confirm:

- Known contraindications and disliked exercises are avoided or clearly justified
- Pain-sensitive patterns include regressions or stop rules
- Loading, volume, range of motion, and progression match client readiness
- High-risk movements are justified by context and coachable within the session
- Cardio intensity and exercise complexity fit the client and session goal

### 4. Session Architecture And Timing

Confirm every session has:

- Warm Up
- Workout
- Cooldown
- A clear session goal and rationale
- Realistic density for the stated session length

Warm-ups should follow the current `program-pal-program-design` rule unless the trainer explicitly overrides it:

- 1-2 temperature-raising dynamic movements
- 3 movements that prepare for the main workout
- 2 client-specific mobility movements

For short sessions, it is acceptable to combine purposes into fewer drills when the assessment-specific intent is preserved and the workout would otherwise be crowded.

### 5. Progression And Tracking

Confirm:

- Progression method is clear
- Success metrics match the client's goals and assessment findings
- Retest or tracking priorities are named when relevant
- The trainer can tell how to progress, regress, or hold steady

### 6. Workbook Quality

Inspect the workbook or generation script for:

- Correct client/program title
- Overview and rationale sheet
- Correct number of weeks and sessions
- No copied placeholder content
- No empty session blocks or orphaned template sections
- Readable notes, wrapped text, and sensible row heights
- Print-friendly layout when applicable
- Consistent file name and program label

Render or open the workbook when visual layout risk is meaningful and tooling is available.

### 7. Privacy And Storage Readiness

Confirm:

- Local generated client files are not accidentally staged for git unless explicitly requested
- Client-identifying files are not placed in public docs or generic examples
- Google Drive destination follows `program-pal-google-drive-storage`
- Duplicate file handling is addressed before upload
- Final local and Drive file names follow the required naming convention

## Audit Result

Return one of these statuses:

### Pass

Use when the program is ready for trainer review, delivery, and storage.

Include:

- What was checked
- Any minor assumptions the trainer should know
- Final workbook path or expected upload name

### Pass With Notes

Use when the program is usable but has minor issues or trainer-review items that do not block delivery.

Include:

- Notes requiring trainer attention
- Why they are non-blocking

### Blocked

Use when the program should not be delivered or stored yet.

Include:

- Blocking issue
- Why it matters
- Exact fix needed
- Whether the workbook should be regenerated

Do not upload a workbook to Google Drive after a `Blocked` audit unless the trainer explicitly approves uploading a known draft.
