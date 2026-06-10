# worldbuilding policy.md

This file tells the agent how to create, track, revise, and evaluate worldbuilding.

Worldbuilding is the structured record of what is true inside the story world.

It should be lean: enough to preserve continuity, not so much that the story becomes buried under reference material.

## Track by locale, with time as a dimension

The agent should track worldbuilding primarily by locale.

A locale may be a country, city, district, road, building, room, ship, institution, battlefield, tavern, karaoke bar, forest, dream-space, or other place-like environment.

Time should usually be recorded inside the locale file as a dimension of change.

Ask:

```text
Where is this true?
When is it true there?
Who is affected there?
What changes there over time?
```

The timeline is separate, but it is an index of event order, not the main storage location for worldbuilding.

## Persistence scale

The agent cannot write without inventing details. Not every invented detail should be logged.

```text
Section-level:
Mentioned once in one section.
Do not log.

Chapter-level:
Persistent across multiple sections in one chapter.
Log and inform the human author.

Super-chapter-level:
Persistent beyond one chapter, or affects future continuity.
Ask before introducing or changing it when it contradicts established defaults.
```

## Place files

A place file should be created or updated when a locale becomes persistent, consequential, or likely to recur.

Place files belong in:

```text
meta-mainmatter/worldbuilding/places/
```

Recommended structure:

```markdown
# [place name].md

## Identity

Name:
Type:
Parent locale:
Sub-locations:
First appearance:
Related mainmatter sections:

## Default state

What is usually true here?

## Temporal states

### Temporal state: [chapter / section / date / event]

State:
What changed:
Characters affected:
Objects affected:
Continuity consequences:
Related timeline entries:

## Events that happened here

Event:
Section:
Characters involved:
Worldbuilding impact:
Continuity consequence:

## Associated characters

Character:
Relationship to place:
Relevant sections:

## Associated objects

Object:
Role in place:
Related object file:

## Local customs or rules

Custom or rule:
Scope:
Who knows it:
Consequence:

## Anachronism or plausibility notes

Item:
Expected baseline:
Actual manuscript usage:
Status:
Action:

## Open questions

Question:
Why it matters:
Who must answer:
```

## Timeline

The timeline is a semi-ordinal index.

It tracks event order even when exact dates are unknown. Some events may have fixed dates. Others may only be known as before, after, during, near, or relative to other events.

Timeline files belong in:

```text
meta-mainmatter/worldbuilding/timeline/
```

Recommended entry:

```markdown
### Event: [event name]

Event ID:
Summary:
Sequence position:
Known date:
Date status: fixed / approximate / relative / unknown / contested / author placeholder / changed by authorization

Relative order:
Before:
After:
During:
Near:
Unknown relation:

Duration:
Characters involved:
Places involved:
Objects involved:
Worldbuilding impact:
Style impact:
Source:
Continuity risk:
Open questions:
```

A fixed date remains fixed for continuity until the human author authorizes a change.

## Anachronisms

An anachronism is not automatically wrong.

It may be a mistake, a hook, an alternate-history marker, a translation convention, a comic device, a stylistic choice, or an unresolved issue.

If an anachronism is a hook, it must be expected to return, resolve, or change meaning later.

If it will not return or matter, the agent should suggest dropping it, correcting it, or marking it as a placeholder.

## Casual author language is not canon

The human author may use shorthand, jokes, frustration, insults, placeholders, or console-like commands.

The agent must not automatically convert this language into canonical worldbuilding.

Example:

```text
Jenny is being a dumb bitch here.
```

should not become:

```text
Canon: Jenny is dumb.
```

A better interpretation is:

```text
The human author wants Jenny’s behavior in this moment to read as foolish, abrasive, impulsive, defensive, cruel, comic, or socially destructive.
```

If this affects persistent characterization or worldbuilding, ask.

## Ask before persistent changes

The agent must ask before changing or introducing super-chapter-level worldbuilding that contradicts established defaults or affects future continuity.

Use this format:

```text
Current worldbuilding:
What is currently established.

Proposed change:
What would change.

Persistence level:
Section-level, chapter-level, or super-chapter-level.

Reason:
Why the change may help.

Risk:
What continuity, plot, translation, or reader-load burden it creates.

Authorization needed:
What the human author must approve.
```

## Keep worldbuilding lean

Track only what affects drafting, editing, revision, translation, continuity, character behavior, plot logic, reader comprehension, or future scenes.

Do not create a file for every detail.