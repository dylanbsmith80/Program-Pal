---
name: program-pal-program-audit
description: Use after Program Pal creates or revises weekly workout files, and before delivery or Google Drive storage, to audit the program for client specificity, safety, workflow compliance, time realism, spreadsheet quality, and storage readiness.
---

# Program Pal Program Audit Skill

Use this skill as the final quality gate for Program Pal workout programs.

This skill does not design the program, select exercises, format spreadsheets, or upload files. It checks whether the completed weekly files are ready for trainer review and storage.

## When To Use

Use this skill after:

- `program-pal-initial-assessment`
- `program-pal-intake-questions`
- `program-pal-program-design`
- `program-pal-exercise-selection`
- `personal-training-workbook-format`

Use it before:

- Delivering the final program to the trainer
- Uploading the finished weekly files with `program-pal-google-drive-storage`
- Saying the program request is complete

If the trainer explicitly asks to skip audit, report that the audit was skipped and name any obvious residual risk.

## Audit Inputs

Review the available materials:

- Assessment brief or prior client context
- Intake readiness output
- Program Blueprint
- Exercise choices and rationale
- Finished weekly workout files or their generation script
- Trainer constraints, preferences, dislikes, and storage requirements

Do not audit from the workout files alone when assessment or trainer context is available.

## Required Audit Checks

### 1. Intake And Workflow Gate

Confirm:

- Intake readiness gate passed, or trainer explicitly approved assumptions
- Program Blueprint exists before the weekly workout files
- Exercise choices align with the blueprint
- Weekly workout files were created after the design and selection gates

### 2. Client-Specific Fit

Check that the program reflects:

- Primary and secondary goals
- Assessment findings
- Safety flags, pain notes, and movement limitations
- Schedule, session length, session format, equipment, and difficulty target
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

Confirm the displayed `Total Time` equals the sum of main-table `Est Time` values. Add Warm Up and Cool Down estimates separately to verify the complete session envelope fits the client's available session length.

For buddy sessions, confirm the program accounts for two-client logistics: shared equipment, station flow, coach attention, rest timing, and individual modifications where the clients differ.

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

### 6. Weekly File Quality

Inspect every weekly workout file or the generation script for:

- File name follows `ClientInitials ProgramVersion Week N.xlsx`
- One file represents one client week
- Correct client and program version
- Correct number of day tabs for the scheduled sessions
- Day tabs are named `Day 1`, `Day 2`, and so on
- No default `Overview & Rationale` tab unless the trainer explicitly requested it
- Every day tab includes Client Name, Day, Date, Total Time, Warm Up, Cool Down, and the main workout table
- Main workout table uses `Exercise | Sets | Reps | Est Time | 3 key Points` unless the session genuinely requires adapted dose fields
- No copied placeholder content
- No empty day tabs, exercise rows, or orphaned template sections
- Readable notes, wrapped text, and sensible row heights
- Print-friendly layout when applicable
- Consistent weekly naming and program version

Render or open every day tab when visual layout risk is meaningful and tooling is available.

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
- Final weekly file paths or expected upload names

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
- Whether one or more weekly files should be regenerated

Do not upload weekly workout files to Google Drive after a `Blocked` audit unless the trainer explicitly approves uploading a known draft.
