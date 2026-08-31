---
name: personal-training-workbook-format
description: Create or format Program Pal weekly workout spreadsheets using one file per client week, one training day per tab, compact warm-up/workout/cooldown layouts, concise coaching cues, and trainer-preferred file naming.
---

# Personal Training Workbook Formatting Skill

Use this skill when creating or formatting Program Pal workout spreadsheets. It governs client-facing spreadsheet organization and visual formatting, not program design or exercise selection.

Preserve the trainer's weekly-file/day-tab system while adapting the number of days, exercises, prescriptions, and coaching notes to the client's actual program.

## Reference Asset

Use `assets/generic-workout-format-reference.xlsx` as the visual and structural reference when a concrete example is useful.

The asset is sanitized and contains generic placeholder programming. Use it to inspect weekly file structure, day-tab layout, color usage, spacing, column widths, timing formulas, and table rhythm. Do not copy its exercise choices or day count unless they fit the actual client.

## Weekly File Structure

Create one workout spreadsheet file per client per training week.

Name each file:

`ClientInitials ProgramVersion Week N.xlsx`

Examples:

- `MZ 2.0 Week 1.xlsx`
- `TG 2.0 Week 2.xlsx`

Use the trainer-provided program version. When the active convention is `2.0` and no different version is supplied, use `2.0`. Do not add a date prefix to weekly workout files unless the trainer explicitly asks for one.

Create one tab per scheduled training day:

- `Day 1`
- `Day 2`
- `Day 3`
- Continue only for the number of days actually prescribed.

Do not place multiple training days on one tab. Do not create an `Overview & Rationale` tab by default. Keep the Program Blueprint, deeper rationale, and trainer learning notes outside the client-facing weekly file unless the trainer explicitly requests an overview.

## Day Tab Structure

Each day tab should present one complete session at a glance.

Include:

- `Client Name:`
- `Day:`
- `Date:`
- `Total Time:` for the main workout block
- `Warm Up:` with its estimated time
- `Cool Down:` with its estimated time
- `Conditioning:` as the default main-section label
- Main table: `Exercise | Sets | Reps | Est Time | 3 key Points`

The main-section label may change when another label clearly describes the session better, but `Conditioning:` is the default trainer convention.

Display Warm Up and Cool Down beside the main workout when practical. Keep the tab compact rather than stacking large standalone sections vertically.

## Default Sheet Layout

Use columns `A:K` as the default day-tab grid:

- `A:B`: Warm Up items and estimated time
- `C:D`: Cool Down items and estimated time
- `E`: narrow visual spacer
- `F`: main-section label
- `G`: Exercise
- `H`: Sets
- `I`: Reps
- `J`: Est Time
- `K`: 3 key Points

Recommended widths:

- A and C: `22-26`
- B and D: `8-10`
- E: `2-3`
- F: `12-16`
- G: `26-32`
- H: `7-9`
- I: `9-11`
- J: `9-11`
- K: `38-48`

Freeze the top metadata/header area when the sheet is long enough to benefit. Hide gridlines when explicit fills and borders define the layout. Use landscape orientation and fit to one page wide when print settings are available.

## Time Accounting

The displayed `Total Time` should equal the sum of the `Est Time` values in the main workout table.

Show Warm Up and Cool Down estimates separately. Five minutes each is the trainer's common default, but use the Program Blueprint when it specifies another duration.

Also calculate or verify the complete session envelope internally:

`Warm Up + Total Time + Cool Down`

The complete session envelope must fit the client's available session length. Do not silently shorten or omit warm-up or cooldown work to make the main table fit.

## Prescription Rules

Allow exercise prescriptions such as:

- Numeric repetitions: `8`, `10`, `12`
- Per-side repetitions: `8 ea`, `10 each`
- Duration or distance: `30 sec`, `200 m`
- RPE targets
- Drop sets
- Tempo instructions
- Exercise-specific timing or progression notes

Use typed numeric values for sets and estimated minutes when practical so timing formulas remain auditable. Use text where the prescription genuinely contains units or per-side language.

## Coaching Notes

The `3 key Points` column is client-facing and concise. Use it for only the most important execution instructions, such as:

- RPE target
- Tempo
- Range-of-motion limit
- Equipment setup
- Drop-set or progression instruction
- Safety reminder
- One or two critical technique cues

It may be blank when no extra cue is needed. Do not place lengthy exercise rationales in the weekly workout file. Keep deeper reasoning in the Program Blueprint or private trainer notes.

## Visual Style

Use Calibri throughout unless the trainer supplies another reference.

- Workbook title: 16-18 pt, bold, white text
- Major section labels: 10-12 pt, bold
- Table headers: 10 pt, bold, white text
- Body cells: 10 pt
- Long coaching notes: 9-10 pt, wrapped
- Metadata: 9-10 pt, muted dark gray

Retain the established Program Pal palette:

- Dark navy: `#1F2D3D` or `#1B3A6B`
- Blue header: `#2E75B6`
- Light blue: `#DCE9F5`
- Very light blue: `#F4F8FC`
- Pale yellow for warm-up, cooldown, cautions, or special instructions: `#FEFBD8`

Use fills, whitespace, and light structural borders. Avoid heavy boxes around every cell. Alternate light fills in the workout table when it improves scanning.

## Content Flexibility

The formatting system must support:

- Any number of training days in the week
- Any safe, client-specific number of exercises
- Strength, hypertrophy, conditioning, mobility, rehabilitation, sport performance, endurance, testing, or mixed sessions
- Normal and buddy sessions
- Supersets, circuits, intervals, or standalone exercises

Keep related movements adjacent. Explain pairing, station flow, or rest rules briefly in `3 key Points`. Do not add empty tabs or placeholder rows merely to match the reference asset.

## Lettered Block Labels

- Labels such as `A1` and `A2` indicate movements performed in the same block or superset. Use `A1` alone when the block contains only one movement.
- Put multiple exercises under the same letter only when they use the same equipment or station.
- If exercises require different machines, benches, cable towers, racks, or gym areas, give them different sequential letters even when they are located on the same floor.
- Do not use shared letters only to show that exercises are related. The labels must describe an executable session flow.

## Verification

Before delivery or Google Drive storage:

- Confirm the file name follows `ClientInitials ProgramVersion Week N.xlsx`.
- Confirm one file represents one week.
- Confirm every scheduled day has exactly one correctly named tab.
- Confirm there is no default overview tab or copied placeholder content.
- Confirm Client Name, Day, Date, Total Time, Warm Up, Cool Down, and the main table appear on every day tab.
- Confirm `Total Time` equals the sum of main-table estimated times.
- Confirm the complete session envelope fits the client's session length.
- Confirm long notes are wrapped and visible.
- Confirm no important text is clipped and no empty template blocks remain.
- Confirm formulas contain no spreadsheet errors.
- Confirm every multi-exercise lettered block uses one shared equipment setup or station, unless the trainer explicitly approved an exception.

## Final Workbook Inspection Gate

Open or render every generated day tab and inspect the same file that will be delivered or uploaded.

Confirm the workbook opens without errors; expected day tabs are present; headers, colors, borders, row heights, and column widths render as intended; formulas display correctly; and the file remains compact and print-friendly.

If visual rendering is unavailable, perform the strongest available programmatic check of sheet names, used ranges, representative values, formulas, merged ranges, and print settings. State that visual rendering was unavailable and summarize the fallback checks.

Do not upload a generated weekly workout file until this inspection gate passes or the trainer explicitly approves skipping it.
