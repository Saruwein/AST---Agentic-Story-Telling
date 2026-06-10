# style policy.md

This file tells the agent how to handle style. Style means the preferred behavior of the narrative — prose, pacing, tension, clarity, reader orientation, description, dialogue, and more.

## File roles

- `default style.md` — starting stylistic defaults (advisory)
- `global style.md` — active project-specific style
- `style policy.md` — how the agent may handle style (procedural)
- `chapter styles/` — per-chapter style notes
- `character styles/` — character voice and diction notes

`default style.md` is advisory. `global style.md` is project-specific. `style policy.md` is procedural. Do not confuse them.

## Style anchors are not rules

Style anchors are default pressures, not commandments. A strong story may deliberately violate any default. Do not turn anchors into a compliance checklist.

## Human author instruction wins

The current instruction from the human author overrides stored style files unless it violates a hard rule in `rules.md`.

## Style inheritance

Practical order: `default style.md` → `global style.md` → chapter style → character style (for character-owned language) → current human author instruction.

Chapter style applies to general narration, pacing, density, and tone. Character style applies mainly to dialogue, direct thought, letters, testimony, diary entries, quoted speech, or narration assigned to that character.

## Track meaningful deviations

Track deviations from `global style.md` when they affect drafting, editing, revision, translation, reader comprehension, continuity, character voice, worldbuilding, pacing, tone, or local readability. Do not record every small variation.

## Consider reader load

When evaluating readability, consider how stylistic deviations affect reader load. A consistent global deviation is easier to adapt to than many abrupt local deviations. This is advisory, not a hard score.

## Style layer

Style is tracked through these files:

```text
meta-mainmatter/style/style policy.md
meta-mainmatter/style/default style.md
meta-mainmatter/style/global style.md
meta-mainmatter/style/chapter styles/
meta-mainmatter/style/character styles/
```

The agent must not treat style anchors as hard rules (see Rule 1 in `rules.md`).
