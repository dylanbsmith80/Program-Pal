---
name: program-pal-exercise-selection
description: Use when Program Pal needs to choose, verify, substitute, regress, progress, or explain exercises for a client-specific workout program based on goals, assessment findings, safety flags, equipment, preferences, and the Program Blueprint.
---

# Program Pal Exercise Selection Skill

Use this skill when choosing exercises for a client program or revising exercises inside an existing program.

This skill governs exercise selection, verification, substitutions, regressions, progressions, placement, and exercise rationale. It should be used after client context exists and alongside `program-pal-program-design`.

## Source References

Read these references when needed:

- `references/verified-exercise-sources.md` for approved external exercise sources.
- `references/exercise-entry-schema.md` for the structure Program Pal should use when describing or evaluating exercises.

## Core Workflow

When selecting exercises:

1. Start from the client assessment, goals, safety flags, preferences, equipment, and Program Blueprint.
2. Identify the training purpose of each exercise slot.
3. Prefer verified exercises from approved sources or the trainer's own approved notes.
4. Match exercise difficulty to the client's ability, constraints, and session goal.
5. Choose regressions or substitutions when pain, equipment, skill, preference, or safety requires it.
6. Place the exercise in Warm Up, Workout, or Cooldown according to `program-pal-program-design`.
7. Explain why the exercise fits when the choice is not obvious.

Do not select exercises just because they are popular, novel, or difficult.

## Verified Source Rule

Prefer exercises that can be verified through:

- ACE Fitness Exercise Library
- NASM Exercise Library
- NSCA exercise tutorials/videos
- The trainer's own approved exercise library or notes
- Previously validated Program Pal references

When using exercises from non-verified sources, apply extra caution.

For non-verified exercises:

- Check whether a verified alternative can accomplish the same goal.
- Avoid risky novelty movements.
- Avoid exercises that are hard to coach or hard to set up safely.
- Make sure the exercise matches the client's ability and constraints.
- Explain why the non-verified exercise is appropriate.
- Use the simplest effective option when possible.

If a verified exercise can accomplish the same training purpose, prefer the verified option.

## Selection Criteria

Choose exercises based on:

- Client goal
- Session goal
- Movement pattern needed
- Muscle group or quality trained
- Safety constraints
- Pain or injury considerations
- Training age and technical skill
- Equipment access
- Session length
- Exercise preferences and dislikes
- Program phase
- Progression target

Do not let one factor dominate automatically. For example, a client preference matters, but not more than safety.

## Placement Rules

Follow the program design structure:

1. Warm Up
2. Workout
3. Cooldown

Use these placement defaults:

- Dynamic stretching, light mobility, activation, and prep work usually belong in the Warm Up.
- Heavy, high-skill, high-energy, or multi-joint exercises usually belong early in the Workout.
- Weighted corrective, posture, imbalance, or goal-specific strength work belongs in the Workout.
- Accessory and isolation work usually belongs later in the Workout.
- Cardio or conditioning can be early when it is the highest-priority work and heavy lifting is not the main demand.
- Flexibility, light mobility, dynamic cooldown work, and recovery-oriented movement usually belong in the Cooldown.

Exercises for medical circumstances or limitations may appear anywhere if their placement has a clear reason.

## Substitution And Regression Rules

Substitute or regress an exercise when:

- It causes pain.
- It conflicts with a known limitation.
- The client lacks the needed equipment.
- The client lacks the technical skill to perform it safely.
- The exercise does not fit the session length.
- A disliked exercise is not essential.
- A safer exercise can accomplish the same purpose.

When substituting, preserve the training purpose whenever possible.

Example:

- If the purpose is squat-pattern strength but back squats are inappropriate, consider goblet squats, box squats, leg press, split squats, or assisted squat variations depending on the client.

## Progression Rules

Progressions should match the client's goal and safety context.

Progression can mean:

- Better technique
- Better control
- More range of motion
- More reps
- More sets
- More load
- Slower tempo
- Less assistance
- More difficult variation
- Greater conditioning duration or intensity

For mobility, skill, pain-sensitive, or movement-quality goals, do not treat heavier loading as the only valid progression.

## Output Expectations

When exercise selection is central to the task, include enough rationale for the trainer to audit the choices.

Useful fields include:

- Exercise name
- Placement: Warm Up, Workout, or Cooldown
- Purpose
- Verified source or source status
- Equipment
- Difficulty
- Main coaching notes
- Regression
- Progression
- Substitution options
- Safety notes

Use `references/exercise-entry-schema.md` when a structured exercise entry is needed.

## Handoff

After exercises are selected, pass the choices back to `program-pal-program-design` for blueprint coherence and then to `personal-training-workbook-format` when creating the final Excel workbook.
