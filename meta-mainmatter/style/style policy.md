# style policy.md

This file tells the agent how to handle style.

Style means the preferred behavior of the narrative. It includes prose, pacing, clarity, tension shape, reader orientation, description density, dialogue behavior, temporal complexity, local complexity, surprise logic, repetition, intensity, and worldbuilding density.

## File roles

```text
default style.md
= starting stylistic defaults

global style.md
= active project-specific style

style policy.md
= how the agent may handle style
```

The agent must not confuse these files.

`default style.md` is advisory.  
`global style.md` is project-specific.  
`style policy.md` is procedural.

## Style anchors are not rules

Style anchors are default pressures, not commandments.

The agent may use them to draft, evaluate, revise, translate, or explain stylistic behavior, but it must not turn them into a checklist for the human author.

A strong story may deliberately violate any default style anchor.

## Human author instruction wins

The current instruction from the human author overrides stored style files unless it violates a hard rule in `rules.md`.

## Do not edit style governance silently

The agent must ask before editing:

```text
style policy.md
default style.md
global style.md
rules.md
project structure.md
chapter structure
naming conventions
style inheritance logic
```

The agent may propose such changes, but must not make them silently.

## Ask before major stylistic shifts

The agent must ask before making major stylistic shifts.

Major stylistic shifts include changing:

```text
the project’s prose baseline
the dominant tense
the dominant point of view
the dominant chronology
the density of worldbuilding
the default level of reader orientation
the default level of violence, sex, cruelty, or shock
the default level of dialect, jargon, archaism, or invented language
```

## Use juxtaposition for major style proposals

When proposing a major stylistic change, use this format:

```text
Current style:
What the story is doing now.

Proposed style:
What would change.

Reason:
Why the change may help.

Risk:
What may become harder, heavier, less coherent, or less readable.

Authorization needed:
What the human author must approve.
```

## Track meaningful deviations

The agent should track meaningful deviations from `global style.md`.

A deviation is meaningful when it affects:

```text
drafting
editing
revision
translation
reader comprehension
continuity
character voice
worldbuilding
pacing
tone
local readability
```

The agent should not record every small variation.

## Consider reader load during evaluation

When evaluating readability or editorial quality, the agent should consider how stylistic deviations affect reader load.

A consistent global deviation is usually easier for the reader to adapt to than many abrupt local deviations. Heavy local deviations may still be excellent, but they usually need clearer artistic purpose or stronger contextual support.

This is advisory, unweighted, and untested. The agent must not treat it as a hard score.

## Style inheritance

Practical order:

```text
default style.md
→ global style.md
→ chapter style
→ character style for character-owned language
→ current human author instruction
```

This order is domain-aware.

Chapter style applies to the chapter’s general narration, pacing, density, and tone.

Character style applies mainly to dialogue, direct thought, letters, testimony, diary entries, quoted speech, or narration assigned to that character.

The human author can override all of it.