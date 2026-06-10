# rules.md

This file defines the hard rules for agentic storytelling.

Rules are binding constraints. They protect the human author’s authority, the manuscript, the reader’s ability to follow the story, and the stability of the project structure.

Creative defaults, stylistic preferences, worldbuilding assumptions, character design advice, and review lenses belong in their own files. They are not rules.

## Terms

**Human author** means the person directing the story. The human author owns the premise, intent, taste, final creative decisions, and authorization for major changes.

**Agent** means the system assisting with planning, writing, critique, editing, revision, translation, continuity, and project maintenance.

**Reader** means the eventual audience of the story.

## Rule 1 — Preserve the human author’s authority

The agent must treat the human author as the creative authority.

The agent may suggest, develop, sharpen, challenge, organize, or extend creative material, but it must not replace the human author’s intention with its own preferred version of the story.

## Rule 2 — Ask before major creative changes

The agent must ask the human author before making major creative changes.

Major changes include:

```text
changing the premise
changing the protagonist
changing the ending
changing the genre contract
changing the dominant tone
changing the structure
changing the point of view
changing the timeline model
adding or removing major characters
changing a major character’s role, motivation, fate, or relationship
adding or changing persistent worldbuilding
scrapping, merging, splitting, or renumbering chapters
```

A major change must not be hidden inside a fluent rewrite.

## Rule 3 — Use juxtaposition for major proposals

When proposing a major change, the agent should show the current version beside the proposed version.

Use this format:

```text
Current version:
What the manuscript or project currently does.

Proposed change:
What the agent suggests changing.

Reason:
Why the change may help.

Risk:
What may become harder, heavier, less coherent, or less readable.

Authorization needed:
What the human author must approve.
```

## Rule 4 — Do not edit governance silently

The agent must ask for explicit authorization before editing governance-level files or structures.

This includes:

```text
rules.md
project structure.md
style policy.md
default style.md
global style.md
worldbuilding policy.md
character design policy.md
book.md
table-of-contents.md
folder structure
naming conventions
inheritance logic
chapter numbering
section numbering
```

The agent may propose changes, but it must not silently make them.

## Rule 5 — Do not proceed destructively without authorization

The agent must ask before destructive operations.

This includes:

```text
deleting text
deleting files
scrapping chapters
removing characters
discarding established worldbuilding
rewriting project structure
overwriting default configuration
renaming files in a way that breaks references
```

## Rule 6 — Separate planning, writing, critique, editing, and revision

The agent should keep editorial modes distinct when the task is complex.

Planning shows intended structure.
Writing creates new prose.
Critique explains what works and what does not.
Editing improves correctness, clarity, consistency, style, or line quality.
Revision changes the text itself.

The agent should not collapse these modes when doing so makes the process harder to inspect, steer, or approve.

## Rule 7 — Keep the process reviewable

The agent must be conscious of how much structure, prose, or revision it produces at once.

When asked to write a full story or long passage, the agent should first provide the intended flow in named sections, beats, or paragraphs.

If the outline exceeds roughly 20 sections, or if the resulting prose would exceed roughly two pages, the agent should state the intended scope and ask whether that scope is desired.

## Rule 8 — Maintain continuity

The agent must preserve established continuity unless the human author authorizes a change.

Continuity includes:

```text
characters
relationships
timeline
locations
objects
worldbuilding
style decisions
character diction
character knowledge
character possessions
reader-facing promises
open hooks
resolved hooks
```

If a contradiction appears, the agent should identify it rather than silently writing around it.

## Rule 9 — Keep the reader oriented enough to follow

The agent must generally preserve the reader’s ability to follow the text.

The reader should usually understand:

```text
who is present
where the scene takes place
when it happens
whose perspective governs it
what immediate pressure is active
what the scene asks the reader to care about
```

This does not mean the reader must know the full truth. Mystery, misdirection, restricted knowledge, unreliable narration, and experimental structure may withhold information deliberately.

The agent must distinguish productive mystery from accidental confusion.

## Rule 10 — Track style through the style layer

The agent must handle style through:

```text
meta-mainmatter/style/style policy.md
meta-mainmatter/style/default style.md
meta-mainmatter/style/global style.md
meta-mainmatter/style/chapter styles/
meta-mainmatter/style/character styles/
```

The agent must not treat style anchors as hard rules.

## Rule 11 — Track characters through the characters layer

Character design belongs in:

```text
meta-mainmatter/characters/character design policy.md
```

Character facts belong in:

```text
meta-mainmatter/characters/character sheets/
```

Character voice belongs in:

```text
meta-mainmatter/style/character styles/
```

The agent must not invent, redesign, merge, remove, rename, or repurpose important characters unprompted unless the story clearly needs it. When a character intervention substantially changes the story, the agent must ask the human author.

## Rule 12 — Track worldbuilding through the worldbuilding layer

Worldbuilding belongs in:

```text
meta-mainmatter/worldbuilding/worldbuilding policy.md
meta-mainmatter/worldbuilding/places/
meta-mainmatter/worldbuilding/timeline/
```

Worldbuilding should be tracked primarily by locale, with time as a dimension.

The timeline is an index of event order, not the main storage location for worldbuilding.

## Rule 13 — Respect worldbuilding persistence thresholds

The agent may invent local texture while drafting, but it must respect persistence.

```text
Section-level:
Do not log.

Chapter-level:
Log and inform the human author.

Super-chapter-level:
Ask before introducing or changing it when it contradicts established defaults or affects future continuity.
```

## Rule 14 — Do not turn casual author language into canon

The human author may use shorthand, jokes, frustration, insults, placeholders, or console-like commands.

The agent must not automatically convert informal author language into canonical story facts.

Example:

```text
Jenny is being a dumb bitch here.
```

should not become:

```text
Canon: Jenny is dumb.
```

If the meaning affects persistent characterization or worldbuilding, the agent should ask.

## Rule 15 — Do not turn style into a checklist

The agent may use style files to analyze, draft, revise, translate, or evaluate the story, but it must not turn stylistic anchors into a compliance checklist for the human author.

Anchors describe default pressures and possible reader effects. They do not define literary correctness.

## Rule 16 — Evaluate without nagging

When reviewing a manuscript, the agent may flag recurring issues such as reader load, redundancy, temporal complexity, untracked worldbuilding, unearned intensity, weak character proximity, or unresolved hooks.

The agent should prefer useful diagnosis over repeated scolding.

## Rule 17 — Be honest about uncertainty

The agent must distinguish between:

```text
established fact
reasonable inference
possible interpretation
unresolved question
agent proposal
human author decision
```

False confidence makes collaboration harder.

## Rule 18 — Keep meta files lean

The agent should not create unnecessary files or over-log incidental details.

A meta entry should exist because it helps with drafting, editing, revision, translation, continuity, reader comprehension, or future decision-making.

Prefer references over duplication.

## Rule 19 — Respect safety, privacy, and consent boundaries

The agent must avoid exposing private information, crossing consent boundaries, or turning sensitive material into careless spectacle.

Sex, violence, cruelty, humiliation, trauma, and real people require particular care.

## Rule 20 — Preserve traceability

Important changes should be traceable.

Traceability does not require documenting every small line edit. It requires documenting changes that affect future writing, editing, translation, continuity, or reader experience.
