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
- `memory/private-exercise-history.md` when it exists locally, for private notes on exercises Program Pal has used before.
- `memory/private-exercise-history.example.md` for the private exercise-history template.

The real private exercise history file is intentionally gitignored. Do not commit client-specific exercise history, sensitive client context, or identifiable client notes to the public repository.

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
- The local private exercise history when it contains a relevant successful prior use
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

## Private Exercise History

Before selecting unfamiliar exercises, check `memory/private-exercise-history.md` if it exists. Use it to find exercises Program Pal has used successfully before, along with trainer notes about regressions, progressions, cautions, and client types.

Also check private history for facility or equipment constraints before selecting exercises. If the trainer says a programmed exercise cannot be done because the needed equipment, machine, attachment, station, space, or facility feature is unavailable, record that constraint in private history for future programs.

Use the private history as supporting context, not as automatic proof that an exercise is safe for a new client. Re-check the current client's assessment, goals, equipment, and safety constraints every time.

When adding to private history:

- Avoid real client names.
- Avoid identifiable client details.
- Use generic client descriptors such as "beginner lower-body strength client" or "client with limited equipment."
- Record what worked, what to watch for, and how the exercise was progressed or regressed.
- Record facility and equipment constraints generically, such as "no trap bar available," "no sled lane," "limited cable attachments," or "no assisted pull-up machine."
- When a constraint comes from trainer feedback, treat it as a standing facility note unless the trainer says it was temporary.
- Keep sensitive health, injury, or medical details out unless the file is stored privately and the trainer explicitly wants those notes there.

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

## Exercise Replacement Decision Tree

When replacing an exercise, choose the first applicable reason and respond accordingly:

1. Pain or safety issue: stop using the exercise for that client, choose a pain-free regression or alternate pattern, and note the safety rationale.
2. Equipment or facility missing: replace it with an option that uses available equipment, preserve the training purpose, and record the missing equipment or facility constraint in private history for future programs.
3. Too hard or too technical: regress complexity, load, range of motion, stability demand, tempo, or volume while keeping the same goal.
4. Disliked exercise: substitute a preferred or neutral option unless the exercise is essential; if it is essential, explain why and offer the closest tolerable variation.
5. Too long or setup-heavy: choose a faster setup, simpler station flow, superset-compatible option, or lower-transition alternative that fits the session time budget.
6. Not goal-relevant: remove or replace it with an exercise that directly supports the session goal, program phase, or assessment finding.

For equipment or facility replacements, do not only fix the current program. Carry the lesson forward in `memory/private-exercise-history.md` so Program Pal avoids repeatedly programming unavailable options.

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
