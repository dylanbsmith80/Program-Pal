# Client Memory Schema

Use this structure when creating or materially updating a Program Pal client-memory document. Keep entries concise, dated, and factual. Omit empty optional bullets, but preserve the main section headings so future retrieval remains predictable.

```markdown
# Client Memory - FirstNameLastInitial

Client key: FirstNameLastInitial
Created: YYYY-MM-DD
Last reviewed: YYYY-MM-DD
Memory status: Active

## Current Snapshot

- Training status: Active | Paused | Inactive | Unknown
- Current program: Program/version or None
- Current phase: Phase/week or Unknown
- Sessions: frequency, duration, and format; last confirmed YYYY-MM-DD; source
- Equipment/access: summary; last confirmed YYYY-MM-DD; source

## Goals

### Active

- Goal; target or success measure; priority; last confirmed YYYY-MM-DD; source

### Completed

- Goal; outcome; completion date; source

### Future

- Goal; intended timing or prerequisite; last confirmed YYYY-MM-DD; source

## Safety And Limitations

- Constraint, pain flag, injury history, movement limit, or clinician instruction; programming impact; last confirmed YYYY-MM-DD; source

## Preferences And Coaching Notes

- Exercise preference, aversion, cue that works, motivation factor, or session-flow preference; last confirmed YYYY-MM-DD; source

## Training History And Baselines

- Relevant training age, prior program, assessment measure, performance baseline, or tolerance; date; source

## Program History

- Program/version; status (planned, prescribed, in progress, paused, completed); dates; outcome or reason for change

## Programming Decisions

- YYYY-MM-DD — Decision and concise rationale; trainer-approved, source, or pending review

## Workout Feedback

- YYYY-MM-DD — Program/version; stage (trainer review or session outcome); rating when supplied; what to keep; what to change; reason; scope; source

## Recent Progress

- YYYY-MM-DD — Observable result, adherence note, client feedback, or trainer observation; source

## Open Questions

- Missing, stale, or conflicting fact; why it matters; date first noted

## Change Log

- YYYY-MM-DD — Created/updated sections; source task or document
```

## Source Labels

Use short source labels that another Program Pal session can understand, for example:

- `Trainer statement in task, 2026-08-30`
- `Initial assessment dated 2026-08-22`
- `Progress report dated 2026-09-15`
- `Program Blueprint DS 2.0, approved 2026-08-30`

Do not use a source label that implies a document was reviewed when it was not.

## Update Semantics

- Replace the current value when the trainer explicitly corrects it, and retain the prior value only when it is useful history.
- Append progress, program milestones, and decisions chronologically.
- Use `Unknown` instead of guessing.
- Keep safety constraints active until explicitly cleared or superseded by an appropriate source.
- Keep a created or trainer-reviewed workout `planned` or `prescribed` until session completion is explicitly confirmed.
- Store one-off feedback without silently promoting it to a durable client rule. Follow `program-pal-workout-feedback` for client-wide, trainer-wide, and facility-wide promotion.
- Mark a fact `Needs confirmation` when it is old or conflicts with a newer source.
- Summarize repetitive history rather than letting the document grow without bound, but retain safety-critical history and program outcomes.
