---
name: program-pal-initial-assessment
description: Use when Program Pal receives a completed or partially completed personal training initial assessment, intake form, client questionnaire, fitness test record, FMS notes, posture notes, SMART goals, or fitness-goal notes and needs to extract client context, identify safety flags, ask follow-up questions, and prepare programming inputs before creating a workout program.
---

# Program Pal Initial Assessment Skill

Use this skill to turn a client's initial assessment information into programming-ready context for Program Pal.

This skill governs assessment interpretation, missing-information discovery, safety review, and programming input preparation. It does not format the final workout workbook. For workbook formatting, use `personal-training-workbook-format`.

## Source Reference

For the assessment template fields and expected sections, read `references/initial-assessment-template.md` when needed.

## Core Workflow

When given an assessment, intake response, notes from an initial session, or a partially completed assessment:

1. Extract the client's known information.
2. Separate facts from assumptions and score the source confidence for each important finding.
3. Identify safety flags and programming constraints.
4. Identify missing information that matters before programming.
5. Summarize the client's goals, preferences, and training context.
6. Convert assessment results into programming implications.
7. Produce a concise programming brief that can feed the workout-program creation step.

Do not create a full workout program until enough safety, goal, schedule, equipment, and training-context information is available.

## Reading PDFs And Scans

Assessment PDFs may contain typed text, form fields, annotations, highlights, handwriting, or image-only marks.

Use the most reliable available method:

1. Try extracting text, form fields, and annotations.
2. If important answers are missing, render the pages and inspect the visual content.
3. If handwriting or marks are unclear, score the finding with low or medium confidence, record the uncertainty, and ask the trainer to confirm it when it affects safety or required programming readiness.
4. Do not invent missing assessment answers.

When the file appears blank through text extraction but filled visually, treat the rendered pages as the source of truth.

## Confidence Scoring

Every important extracted finding must include a source-confidence score. Confidence measures only how sure Program Pal is that the source says the extracted value. It does not measure whether the value is clinically important, complete, or sufficient for programming.

Use this scale:

- `Confidence: 5 Very High` for typed text, form-field data, a clear checkbox, or a clearly legible value.
- `Confidence: 4 High` for readable visual or handwritten data with minor ambiguity that does not change the meaning.
- `Confidence: 3 Medium` for a likely value when handwriting, scan quality, conflicting context, or inference creates real doubt.
- `Confidence: 2 Low` for a possible value that is unclear enough that using it could change programming.
- `Confidence: 1 Unusable` for data that is blank, illegible, cropped, contradictory without resolution, or not actually present.

Treat findings by score:

- `5 Very High` and `4 High`: Use normally in the assessment summary and programming implications.
- `3 Medium`: Use cautiously. Include an `Uncertainty:` note and do not let it drive high-risk programming alone.
- `2 Low`: Do not treat as settled. Include an `Uncertainty:` note and ask for clarification if it affects safety or required programming readiness.
- `1 Unusable`: Treat as missing. Include an `Uncertainty:` note when useful, ask for clarification if the field is required, and omit it from programming decisions otherwise.

Required programming-readiness fields must be confidence `3 Medium` or higher to count as known. Safety-critical findings involving pain, injury, medical concerns, contraindications, or major limitations must be confidence `4 High` or higher to proceed without clarification.

## Assessment Domains

Capture information under these domains when present:

- Client identity and session metadata
- Medical history and health concerns
- Medications or supplements
- Pain locations and pain notes
- Activity history
- Cardiorespiratory activity
- Resistance-training history
- Sedentary time
- Stress and stress-management habits
- Nutrition and hydration notes
- Body composition and measurements
- Cardiovascular endurance results
- Muscular endurance and strength results
- FMS results
- Additional assessments
- Posture notes
- SMART goals
- Exercise likes and dislikes
- Long-term fitness goals
- Short-term fitness goals
- What the client wants from the trainer
- What the client wants from the exercise program

## Safety Review

Before programming, scan for red flags and constraints. Flag anything that should affect exercise selection, intensity, range of motion, loading, volume, or progression.

Examples include:

- Current pain
- Recent or unresolved injury
- High blood pressure or concerning cardiovascular markers
- Medication or supplement considerations
- Major strength asymmetries
- Movement pain during FMS or other screens
- Poor balance, instability, or movement-control issues
- Very low training history
- Older adult or high-risk client context
- Very high sedentary time
- Excessive stress, poor recovery, or nutrition concerns
- Goals that conflict with safety or available time

If information suggests medical clearance may be needed, state that clearly and avoid prescribing high-risk programming.

## Missing Information Rules

Ask follow-up questions when missing details could change the program.

Prioritize questions about:

- Pain, injury, or medical constraints
- Training frequency and session length
- Program duration
- Available equipment and training environment
- Main goal and secondary goals
- Current training baseline
- Exercise experience and technical confidence
- Movement limitations
- Exercise preferences and dislikes
- Client schedule and recovery capacity
- Any previous program results

Keep follow-up questions focused. Ask the smallest useful set needed to move toward a safe, specific program.

## Programming Interpretation

Translate assessment data into practical programming implications.

Use this pattern:

- **Finding:** What the assessment says, with inline confidence.
- **Meaning:** Why it matters for training.
- **Programming implication:** How it should influence the plan.

Examples:

- If the client reports low resistance-training history, start with lower complexity, clear coaching notes, and conservative progression.
- If the client reports pain during a movement screen, avoid loading that pattern aggressively and consider alternatives or prep work.
- If the client has a short-term goal with a deadline, structure the cycle around measurable progress markers.
- If the client dislikes certain exercises, avoid them unless there is a strong reason and provide a trainer-facing rationale.
- If the client has high sedentary time, consider mobility, posture, aerobic base, and gradual work-capacity progression.
- If a programming implication depends on confidence `1-3` source data, name that confidence in the implication and choose a conservative action until clarified.

## Output Format

When processing assessment information, produce a programming brief with these sections:

1. `Client Snapshot`
2. `Primary Goals`
3. `Training Background`
4. `Preferences And Constraints`
5. `Assessment Findings`
6. `Safety Flags`
7. `Programming Implications`
8. `Missing Information`
9. `Recommended Next Step`

Keep the brief practical and trainer-facing. The brief should help the trainer quickly understand what matters before building the program.

Use compact inline confidence for important findings:

```text
- Knee pain: Reports right knee pain during squats. Confidence: 3 Medium. Uncertainty: Handwritten side marker appears to be "R," but is unclear.
- Sessions per week: 3. Confidence: 5 Very High.
```

Include `Uncertainty:` only when confidence is `1 Unusable`, `2 Low`, or `3 Medium`.

For `Programming Implications`, include confidence only when the implication depends on uncertain source data:

```text
- Use conservative squat progressions until knee pain side is confirmed. Based on confidence 3 knee-pain note.
```

## Privacy Rules

Client assessment information is private. Do not expose one client's details to another client, another user, or public-facing output.

Use client identifiers only as provided by the trainer. If creating examples, use generic placeholder clients.

## Handoff To Program Creation

After assessment interpretation, Program Pal may create the workout program only when:

- Goals are clear enough.
- Safety constraints are understood.
- Training frequency and session length are known.
- Equipment access is known.
- Program duration or cycle length is known.
- Major pain, injury, or medical concerns have been addressed.

Required programming-readiness fields with confidence `1 Unusable` or `2 Low` do not count as known. Safety-critical findings with confidence `1-3` must be clarified before program design proceeds unless the trainer explicitly approves conservative assumptions.

When ready to build the workout workbook, combine this assessment brief with the Program Pal constitution in `PROGRAM_PAL_AGENT_OBJECTIVES.md` and the formatting rules in `personal-training-workbook-format`.
