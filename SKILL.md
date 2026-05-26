---
name: personal-training-workbook-format
description: Format Excel workout programs in the TG 3.0 style: clean, modular, client-specific training workbooks with overview tabs, weekly/program tabs, reusable session blocks, readable tables, and consistent print-friendly layout.
---

# Personal Training Workbook Formatting Skill

Use this skill when creating Excel workout programs for personal training clients. This skill governs spreadsheet formatting and organization only. It must not assume a specific training split, number of sessions, exercise type, or program philosophy.

Every client's workout content can be different. Preserve the visual workbook system while adapting the sheet count, session count, section labels, and table headers to the client's actual program.

## Workbook Structure

Create one workbook with:
- An `Overview & Rationale` sheet first.
- One sheet per training week, phase, block, or cycle after the overview.
- Sheet names such as `Week 1`, `Week 2`, etc., unless another naming system better fits the program.
- Each training sheet may contain any number of session blocks: 1, 2, 3, 4, or more.
- Keep the workbook compact, print-friendly, and easy to scan during a training session.

Do not create empty session blocks just to match another template. If a client trains once per week, use one session block. If a client trains three times per week, stack three session blocks. If the program uses a different structure, adapt the number and labels while preserving the formatting rhythm.

## Global Style

Use Calibri throughout.
- Main workbook title: 16-18 pt, bold, white text.
- Training sheet title: 16 pt, bold, white text.
- Session headers: 13 pt, bold, white text.
- Table headers: 10 pt, bold, white text.
- Body cells: 10 pt.
- Long notes cells: 9 pt, wrapped text.
- Metadata rows: 9 pt, italic, muted dark gray.

Use fills instead of heavy borders. Organization should come from color bands, merged headers, spacing rows, alternating fills, and consistent alignment.

## Color System

Use a dark navy workbook/program header:
- Dark navy: `#1F2D3D` or `#1B3A6B`
- White text for major headers.

Use color families to visually separate sessions, not to enforce a training split.

Recommended color families:
- Blue header: `#2E75B6`
- Light blue row fill: `#DCE9F5`
- Very light blue alternate fill: `#F4F8FC`
- Mid blue accent: `#C2D8EE`

- Red header: `#B03030`
- Deep red session header: `#7B1A1A`
- Light red row fill: `#FAE2E0`
- Very light red alternate fill: `#FEF6F6`
- Mid red accent: `#F0C5C2`

Use pale yellow only for special notes, warm-ups, cautions, or important instructions:
- Pale yellow: `#FEFBD8`

For programs with more than two sessions per week, rotate color families or reuse the same neutral/dark session header style with alternating light fills. Do not imply that blue always means lower body or red always means upper body unless the client's actual program uses that distinction.

## Sheet Layout

Training sheets should use columns `A:G`.
- Column A: narrow outside margin, width about `1.5`.
- Column B: primary item/name column, width about `34`.
- Column C: first training variable column, width about `9`.
- Column D: second training variable column, width about `16`.
- Column E: third training variable column, width about `14`.
- Column F: notes/key points column, width about `58`.
- Column G: narrow outside margin, width about `1.5`.

Overview sheet should use columns `A:G`.
- A and G are narrow margins, width about `2`.
- B is the main label column, width about `24`.
- C:E are middle content columns, width about `18`.
- F is a slightly wider notes/status column, width about `22`.

Freeze panes on training sheets at `B3`, with the first two rows and first column frozen.

Training sheets should be landscape-oriented and fit to one page wide.

## Training Sheet Pattern

Each training sheet should begin with:
1. Row 1: merged title `A1:G1`, dark navy fill, white bold title.
2. Row 2: merged subtitle `A2:G2`, light gray-blue fill, italic summary text.
3. Row 3: spacer row, height about `10`.

Each session block should follow this pattern:
1. Session header row:
   - Merge `B:D` for the session name.
   - Put total time or session duration in `E:F` when available.
   - Height about `24`.
   - Use a strong session color with white bold text.
2. Metadata row:
   - Include useful session metadata, such as client name, day, date, location, equipment, warm-up/cool-down timing, or coach notes.
   - Height about `15`.
   - Small italic text.
3. Warm-up, prep, or instruction row when relevant:
   - Merge `B:F`.
   - Height about `16`.
   - Pale yellow fill.
   - Italic or small instructional style.
4. Spacer row:
   - Height about `5`.
5. Repeated formatted sections:
   - Section header row merged `B:F`, height about `18-20`.
   - Table header row.
   - Detail rows.

The number of sessions per sheet is flexible. Stack as many session blocks as the client's program requires.

## Section Flexibility

Section names must match the client's actual workout. Do not force all programs into the same exercise categories.

Common section examples:
- `MAIN LIFTS`
- `ACCESSORY WORK`
- `CORE WORK`
- `CONDITIONING`
- `MOBILITY`
- `WARM-UP`
- `SKILL WORK`
- `TECHNIQUE`
- `CIRCUIT`
- `INTERVALS`
- `REHAB / PREHAB`
- `RECOVERY`
- `TESTING`
- `COOLDOWN`

Use whatever labels fit the program. The formatting is the template, not the programming philosophy.

## Table Formatting

Use a five-column table across `B:F` by default.

Default strength table:
`Exercise | Sets | Reps / Duration | Rest | Notes / Key Points / Why`

Adapt table headers to the workout type when needed. Examples:
- Strength: `Exercise | Sets | Reps | Rest | Notes`
- Conditioning: `Movement | Rounds | Time / Distance | Rest | Notes`
- Mobility: `Drill | Sets | Duration | Focus | Notes`
- Rehab: `Exercise | Dose | Tempo | Constraint | Notes`
- Endurance: `Segment | Intensity | Duration | Recovery | Notes`
- Skill work: `Drill | Sets | Target | Rest | Coaching Notes`

Preserve the visual structure even when labels change:
- Column B should be left-aligned and bold for primary item names.
- Columns C, D, and E should usually be centered.
- Column F should be left-aligned, wrapped, and smaller text.
- Alternate detail rows with light and very-light fills from the current session color family.
- Use darker section bands to visually separate major sections.
- Use blank spacer rows between sections instead of heavy borders.

For supersets, circuits, or grouped work:
- Keep related rows adjacent.
- Use indentation or a marker such as `->` for dependent movements when helpful.
- Explain pairing, flow, or rest rules in the notes column.
- Do not create a separate visual system unless the workout structure truly requires it.

## Overview Sheet Pattern

The overview sheet should include:
1. Merged workbook title row `A1:G1`, height about `36`, dark navy fill, white bold text.
2. Merged goal/subtitle row `A2:G2`, height about `22`, blue fill or muted header fill.
3. Spacer row.
4. Program overview section:
   - Section header merged across `B:F`.
   - Table summarizing weeks, phases, sessions, goals, intensity, or other relevant structure.
5. Tracker section when useful:
   - Section header merged across `B:F`.
   - Compact table for important client measures, test results, milestones, attendance, or progress markers.
6. Rationale/notes section when useful:
   - Section header merged across `B:F`.
   - Two-column decision/rationale or note/explanation table.
   - Use taller wrapped rows, about `38` high.

The overview should explain the organization of the program, not duplicate every workout in full.

## Row Heights

Use deliberate row heights:
- Main title rows: `30-36`.
- Subtitle rows: `18-22`.
- Session headers: `24`.
- Metadata rows: `15`.
- Warm-up/prep/instruction rows: `16`.
- Section headers: `18-20`.
- Table header rows: `17`.
- Detail rows: about `40`.
- Spacer rows: `5-10`.
- Overview rationale rows: about `38`.

Adjust row count and row height when necessary so content is readable. Do not allow important text to be clipped.

## Content Adaptation Rules

This skill is formatting-only.

The agent must adapt to:
- Any number of training days per week.
- Any number of sessions per sheet.
- Any number of weeks, phases, or program blocks.
- Any training style, including strength, hypertrophy, conditioning, mobility, rehab, sport performance, testing, endurance, or mixed programs.
- Any section labels that fit the client's program.
- Any table headers that fit the type of work being prescribed.

The agent must preserve:
- One overview-style sheet when useful.
- Consistent sheet title and subtitle rows.
- Modular session blocks.
- Consistent section/table rhythm.
- Clear color-coded organization.
- Wide wrapped notes column.
- Print-friendly landscape layout.
- Clean spacing, alignment, and readable row heights.

## Verification

Before finalizing:
- Confirm all training sheets use consistent column widths.
- Confirm training sheets freeze at `B3`.
- Confirm long notes are wrapped and visible.
- Confirm no important text is clipped.
- Confirm merged title, subtitle, session, warm-up/prep, and section rows are consistent.
- Confirm the workbook does not contain empty blocks copied from another template.
- Confirm the format works for the actual client program structure, regardless of workout type.
