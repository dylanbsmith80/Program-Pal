---
name: program-pal-program-design
description: Use when Program Pal needs to turn a client assessment brief, goals, constraints, schedule, equipment access, or trainer notes into a client-specific training program blueprint before creating the final workout workbook.
---

# Program Pal Program Design Skill

Use this skill to design the actual training program after client context has been gathered.

This skill governs training-cycle structure, session structure, split selection, phase logic, exercise-ordering decisions, and the Program Blueprint. It does not interpret raw assessments or format the final Excel workbook.

- For assessment extraction and safety context, use `program-pal-initial-assessment`.
- For final Excel workbook layout and formatting, use `personal-training-workbook-format`.

## Source Reference

For the required blueprint sections, read `references/program-blueprint-schema.md` when needed.

## Required Inputs

Before finalizing a blueprint, Program Pal must know:

- Client goals and SMART goal timeline when available
- Training frequency
- Session length: 30 minutes or 60 minutes
- Program duration or goal timeline
- Equipment access
- Relevant assessment findings
- Safety constraints, pain, injuries, or medical limitations
- Exercise preferences and dislikes

If session length is missing, ask whether sessions are 30 or 60 minutes.

If program duration is missing and no SMART goal timeline is available, ask for the intended cycle length.

Do not create a final workbook until the blueprint has enough information to support a safe, specific program.

## Program Structure Rules

Every session must follow this top-level structure:

1. Warm Up
2. Workout
3. Cooldown

The contents inside each section are flexible and should be determined by the client's assessment, goals, constraints, and session objective.

## Session Design Rules

Each session must have an overarching goal with a short rationale. The goal may be simple, such as "Work toward FMS squat level 3," but it must clearly connect to the client assessment, goals, or program phase.

Place the most challenging, highest-priority work early in the session while the client has the most energy.

Use these ordering principles:

- Warm-up, dynamic mobility, activation, and prep work come first.
- Heavy, high-skill, high-energy, or multi-joint movements usually come early in the workout.
- Accessory movements usually come later in the workout.
- Cardio or conditioning may come early when it is the highest-priority or most challenging work and the session does not include especially heavy lifting.
- Mobility and flexibility work that is non-weighted or very light belongs primarily in the warm-up or cooldown.
- Warm-ups and cooldowns should include dynamic stretching.
- Weighted corrective, posture, imbalance, or goal-specific work belongs in the workout.
- Exercises addressing medical circumstances, limitations, pain points, or client-specific needs may be placed anywhere if there is a clear reason for the placement.

Do not add corrective or mobility work as random filler. Its placement should have a reason.

## Split Selection

Choose the split that best aligns with the client's goals, schedule, recovery, and assessment findings. Do not default to a favorite split.

Possible splits include:

- Full body
- Upper/lower
- Push/pull/legs
- Strength plus conditioning
- Movement-quality focused
- Hypertrophy focused
- Corrective plus strength hybrid
- Sport or performance focused

Explain why the chosen split fits the client.

## Program Length And Phase Logic

Use the client's SMART goal timeline when available.

Structure phases based on client goals:

- Use periodization when the client goal benefits from staged progression, such as movement-quality base building, strength accumulation, hypertrophy blocks, performance preparation, or a specific deadline.
- Use simpler repeated weekly structure when the client mainly wants maintenance, general fitness, confidence, or consistency.
- Use session length to control workout density: 30-minute sessions should be tighter and more selective.
- Let 60-minute sessions include more complete warm-up, main work, accessory work, conditioning, and cooldown when appropriate.

Do not force every client into a complex periodized plan.

## Progression Guidance

Choose progression methods that match the client goal and safety context.

Useful progression levers include:

- More control or better technique
- More range of motion
- More reps
- More sets
- More load
- More time under tension
- Less assistance
- More stable or unstable variation, when appropriate
- Shorter rest or greater density
- Longer conditioning duration
- Higher conditioning intensity

For pain, movement-quality, mobility, or skill goals, progression may mean better execution rather than heavier loading.

## Safety And Preference Rules

Respect all safety flags from the assessment brief.

If a movement causes pain or conflicts with a known limitation, regress, modify, substitute, or ask for more information.

Use client preferences when possible. Avoid disliked exercises unless there is a strong programming reason, and explain that reason.

## Output

Produce a Program Blueprint before creating the final workbook.

The blueprint should make it clear:

- Why this program structure was chosen
- What each session is trying to accomplish
- How the program supports the client's goals
- What safety constraints shape the plan
- What should be tracked to judge progress

After the blueprint is complete and safe enough to proceed, use `personal-training-workbook-format` to create or format the final Excel workout workbook.
