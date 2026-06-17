---
name: program-pal-intake-questions
description: Use after reviewing the assessment, intake notes, or trainer-provided context when Program Pal is still missing required client or program information before creating a Program Blueprint, exercise selections, or final workout workbook. This skill checks required inputs and asks focused follow-up questions only for unanswered items.
---

# Program Pal Intake Questions Skill

Use this skill before Program Pal designs a program, selects exercises, or creates a final workout workbook. Program Pal may still summarize an assessment before this gate, but it must pass this gate before creating the actual program.

This skill is a readiness gate. Its job is to confirm Program Pal has the minimum required information to build a safe, specific, client-centered program.

## Context-First Rule

Before asking any question, Program Pal must review the available assessment document, intake notes, trainer notes, prior chat context, and any existing programming brief.

Only ask questions for required items that are not answered there.

Do not ask a question if the answer is already clearly present in the assessment or trainer-provided context.

If an item is present but vague, contradictory, illegible, or not specific enough to affect programming decisions safely, ask a focused clarification question for that item only.

If the existing programming brief includes confidence scores, use them when deciding whether an item is known. Confidence measures source certainty only.

## Required Knowledge

Program Pal must know these five items before creating a program:

1. How many sessions per week
2. Session length: 30 minutes or 60 minutes
3. Difficulty rating on a 1-10 scale, with 10 being the most challenging
4. Client goals
5. Client limitations

If any of these are missing, unclear, or contradictory, ask before moving on.

When confidence scores are available, a required item counts as known only at confidence `3 Medium` or higher. Client limitations that involve pain, injury, medical concerns, movement restrictions, contraindications, or exercises to avoid must be confidence `4 High` or higher to proceed without clarification.

## Question Rules

Ask focused questions instead of guessing.

Use these rules:

- Check the assessment and existing notes first.
- Ask only for missing or unclear required information.
- Group questions together when multiple required items are missing.
- Keep questions plain and easy for the trainer to answer quickly.
- Do not ask for information that is already clearly stated.
- Do not treat vague answers as complete if they could materially change the program.
- Do not treat confidence `1 Unusable` or `2 Low` readiness data as complete.
- Ask about confidence `1-3` safety or limitation data when uncertainty could change exercise selection, intensity, range of motion, loading, volume, or progression.
- When limitations are unclear, ask about pain, injuries, medical constraints, movement restrictions, and exercises to avoid.
- When goals are broad, ask for the primary goal and any secondary goals.

## Required Question Prompts

Use or adapt these prompts:

### Sessions Per Week

"How many training sessions per week should this program include?"

### Session Length

"Are the sessions 30 minutes or 60 minutes?"

### Difficulty Rating

"What difficulty level should this program target on a 1-10 scale, with 10 being the most challenging?"

### Client Goals

"What are the client's main goals for this program? If there are multiple goals, which one is the top priority?"

### Client Limitations

"What limitations should Program Pal account for? Include pain, injuries, medical considerations, movement restrictions, exercises to avoid, or anything the client cannot or should not do."

## Readiness Output

When checking readiness, output one of these:

### Ready For Program Design

Use when all five required items are known.

Include:

- Sessions per week
- Session length
- Difficulty rating
- Client goals
- Client limitations

If confidence scores are present, include the confidence for each item. Do not output `Ready For Program Design` when any required item is confidence `1 Unusable` or `2 Low`, or when safety-critical limitations are below confidence `4 High`.

### Missing Required Information

Use when one or more required items remain missing after reviewing the assessment and available context.

Include:

- Known information
- Missing information
- Focused questions for the missing items

Treat confidence `1 Unusable` and `2 Low` required items as missing. Treat confidence `1-3` safety-critical limitations as needing clarification unless the trainer explicitly approves conservative assumptions.

## Handoff

Once all five required items are known, hand off to `program-pal-program-design` to create the Program Blueprint.

If exercise choices are needed, use `program-pal-exercise-selection` after the Program Blueprint has enough structure.

Do not create the final Excel workbook until this readiness gate has passed.

The readiness gate has passed only when the output explicitly says `Ready For Program Design` and includes all five required items with acceptable confidence when scores are available. If the output says `Missing Required Information`, stop and ask the listed questions. Do not continue to program design, exercise selection, workbook generation, or Google Drive storage until the trainer answers or explicitly approves assumptions.
