---
name: program-pal-workout-feedback
description: Collect, classify, and store trainer review feedback or post-session outcomes for a Program Pal workout so later programs improve without turning one-off events into permanent rules. Use after delivering a workout, when the trainer rates or corrects one, after a client performs it, or before the next program when the prior workout has no outcome feedback.
---

# Program Pal Workout Feedback

Create a lightweight, repeatable feedback loop between workout delivery, trainer review, session execution, private client memory, and the next program.

Feedback improves future work only when it is stored at the correct scope. A low rating alone is not a programming rule, a one-time equipment problem is not a client limitation, and one client's preference is not a trainer-wide default.

## Two Feedback Stages

### 1. Trainer Review — After Workout Delivery

After delivering a new or materially revised workout, invite feedback without delaying or weakening the completed handoff. Ask concisely:

1. Overall rating from 1–10.
2. The main reason for that rating: what should stay and what should change.
3. Whether the requested change is specific to this client or should apply more broadly.

The trainer may answer in one line, defer, or skip. Do not require feedback before the trainer can use the finished workout.

When the trainer gives review feedback, store the workout as `planned` or `prescribed`; review approval does not prove the session was completed.

### 2. Session Outcome — After The Client Performs It

When the trainer reports on a completed session, or before creating the next workout when the prior workout has no outcome, ask only for the missing information that would materially improve programming:

- Was it completed as written, modified, stopped, or not performed?
- What was the actual difficulty or effort compared with the target?
- Which exercises, transitions, cues, or time estimates worked especially well or poorly?
- Were there pain, tolerance, technique, equipment, or loading issues?
- What should change next time?

Do not block a new program merely because the trainer has no feedback or chooses to skip. Do pause for unresolved safety information when it could change the next workout.

## Classification And Storage

Read [references/workout-feedback-schema.md](references/workout-feedback-schema.md) before recording feedback.

Use `program-pal-client-memory` to retrieve and update the authoritative private client memory. Classify every feedback item before saving it:

- **Workout-specific:** Rating, approval, requested edit, or comment about one file. Store under `Workout Feedback` and the matching `Program History` entry.
- **Session-specific:** Observed performance, load, adherence, pace, modification, or tolerance from one completed session. Store under `Recent Progress`; keep it out of permanent preferences unless confirmed as durable.
- **Client-specific durable:** A confirmed preference, limitation, cue, progression rule, recurring pacing pattern, or programming decision. Update the matching private-memory section and preserve relevant history.
- **Trainer-wide:** A non-sensitive rule the trainer explicitly says should apply broadly. Update `program-pal-client-memory/references/trainer-programming-style.md` in GitHub only when the trainer clearly authorizes the broad scope.
- **Facility-wide:** A non-sensitive equipment or layout fact. Update the shared facility profile only when the trainer confirms it is a standing facility fact.
- **Safety-critical:** Pain, injury, medical restriction, adverse response, or clinician direction. Update private memory promptly, retain the prior safety history, and resolve conflicts before the next affected program.

Never store real client feedback, ratings, health details, or program outcomes in GitHub.

## Promotion Rules

- An explicit trainer correction about one client may update that client's durable memory immediately.
- Without explicit durable scope, keep a single observation session-specific.
- Repeated client feedback may justify asking whether a pattern should become a durable client rule; do not silently promote it.
- Do not convert feedback into a trainer-wide rule merely because it appears more than once. If the same preference appears across at least three distinct client-program feedback events, ask the trainer whether it should become a shared default.
- Trainer-wide rules never override a conflicting client-specific memory or a current instruction.
- Preserve the trainer's explanation. The reason for a rating is more useful than the number alone.

## Next-Program Use

Before designing the client's next workout:

1. Retrieve the most recent `Workout Feedback`, `Recent Progress`, `Program History`, and unresolved questions.
2. Identify what should be repeated, changed, regressed, progressed, or retested.
3. Reflect those decisions in the Program Blueprint.
4. Do not claim improvement solely because the new workout is different; connect changes to actual feedback.

## Completion Receipt

After recording feedback, report:

- `Feedback stage:` trainer review or session outcome;
- `Program:` file or version;
- `Rating:` value or not provided;
- `Memory updated:` private sections changed;
- `Promotion:` session-only, client-durable, trainer-wide, facility-wide, or none; and
- `Still needed:` any safety or outcome detail that could materially affect the next program.
