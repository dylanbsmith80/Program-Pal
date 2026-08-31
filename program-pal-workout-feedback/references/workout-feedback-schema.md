# Workout Feedback Schema

Use this schema to normalize feedback without making the trainer complete a form. Extract only what the trainer actually provides and leave missing optional fields out.

## Trainer Review Record

Store under `Workout Feedback` in the client's private memory:

```markdown
- YYYY-MM-DD — Program: file or version; stage: trainer review; rating: N/10 or not provided; keep: concise approved elements; change: concise requested edits; reason: trainer's rationale; scope: workout-only | client-specific | proposed trainer-wide; source
```

Rating interpretation is descriptive, not diagnostic:

- `1–3`: substantial mismatch
- `4–6`: usable only with meaningful changes
- `7–8`: good and mostly aligned
- `9–10`: very close to what the trainer wanted

Never infer the reason from the rating. Preserve the trainer's explanation or record `reason not provided`.

## Session Outcome Record

Store observed results under `Recent Progress` and update `Program History` status:

```markdown
- YYYY-MM-DD — Program/session; outcome: completed as written | completed with modifications | stopped | not performed | unknown; actual difficulty: N/10 or description; worked well: concise details; changed or problematic: concise details; pain/tolerance: supplied facts only; next-time implication; source
```

Use `completed` only when the trainer confirms the client performed the session. A created or approved file remains `planned` or `prescribed`.

## Durable Client Rule

When the trainer explicitly confirms a durable client-specific lesson, update the relevant section in addition to the feedback record:

- `Safety And Limitations` for pain, injury, medical, range, or contraindication facts
- `Preferences And Coaching Notes` for exercise likes/dislikes, effective cues, motivation, or pacing
- `Training History And Baselines` for demonstrated loads, reps, ability, or tolerance
- `Programming Decisions` for recurring split, order, volume, progression, or exercise-selection rules
- `Open Questions` for missing or conflicting facts that need later confirmation

Include the date, trainer source, and confirmation status for safety-critical or program-changing facts.

## Default Feedback Prompts

After delivery:

> Quick feedback whenever you’re ready: what would you rate this workout from 1–10, and what is the main thing I should keep or change? Tell me whether that lesson is just for this client or a general preference.

After execution:

> How did the session go compared with the plan—completed as written, modified, or not performed? What worked, what changed, and is there anything I should adjust next time?

Use shorter wording when the trainer has already supplied part of the answer. Do not ask for a rating again when one was already provided.
