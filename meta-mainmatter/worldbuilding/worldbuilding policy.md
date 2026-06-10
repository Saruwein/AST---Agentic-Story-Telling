# worldbuilding policy.md

This file tells the agent how to create, track, revise, and evaluate worldbuilding. Worldbuilding is the structured record of what is true inside the story world. Keep it lean — enough to preserve continuity, not so much that the story is buried under reference material.

## Track by locale, with time as a dimension

Track worldbuilding primarily by locale. A locale may be a country, city, district, road, building, room, ship, institution, battlefield, or other place-like environment. Record time inside the locale file as a dimension of change.

Ask: Where is this true? When is it true there? Who is affected there? What changes over time?

The timeline is an index of event order, not the main storage location for worldbuilding.

## Persistence scale

- **Section-level** — mentioned once. Do not log.
- **Chapter-level** — persistent across multiple sections in one chapter. Log and inform the human author.
- **Super-chapter-level** — persistent beyond one chapter or affects future continuity. Ask before introducing or changing it when it contradicts established defaults.

## Place files

Create or update a place file in `places/` when a locale becomes persistent or likely to recur. Recommended structure:

```markdown
# [place name].md

## Identity
Name: | Type: | Parent locale: | Sub-locations: | First appearance: | Related sections:

## Default state
What is usually true here?

## Temporal states
[Temporal state: chapter/section/event] — State: | What changed: | Characters/objects affected: | Continuity consequences:

## Events
Event: | Section: | Characters: | Worldbuilding impact:

## Associated characters and objects
Character/object: | Relationship: | Relevant sections:

## Local customs or rules
Custom: | Scope: | Who knows it: | Consequence:

## Open questions
Question: | Why it matters: | Who must answer:
```

## Timeline

The timeline in `timeline/` is a semi-ordinal index. It tracks event order even when exact dates are unknown.

Recommended entry:

```markdown
### Event: [name]
Event ID: | Summary: | Sequence position: | Known date: | Date status: fixed/approximate/relative/unknown/contested
Relative order: Before: | After: | During: | Near:
Duration: | Characters: | Places: | Objects: | Worldbuilding impact: | Continuity risk:
```

A fixed date remains fixed until the human author authorizes a change.

## Casual author language is not canon

Do not automatically convert informal author language into canonical worldbuilding. Example:

```text
"Jenny is being a dumb bitch here."
```

should not become `Canon: Jenny is dumb.` If the meaning affects persistent worldbuilding, ask.

## Ask before persistent changes

Before changing or introducing super-chapter-level worldbuilding that contradicts established defaults or affects future continuity, use juxtaposition: current worldbuilding → proposed change → persistence level → reason → risk → authorization needed.
