---
name: writer-edit
description: >-
  Writer skill. Revises chapter prose based on reader reviews, lectorate
  consistency checks, chapter metadata, and existing prose. References
  style policy, worldbuilding policy, and chapter/character style files.
  Use when incorporating feedback or polishing existing manuscript content.
---

## Editing workflow

When you receive a request to edit a chapter, collect all available inputs:

1. **The chapter itself** — `mainmatter/Chap{N}.md`
2. **Chapter metadata** — `meta-mainmatter/chapters/Chap{N}-meta.md` (POV, timeline, locations, characters, revision number, style notes)
3. **Reader review** — `meta-mainmatter/chapters/Chap{N}-reader-rev.md` if it exists (natural-language impressions)
4. **Lectorate consistency check** — `meta-mainmatter/chapters/Chap{N}-lectorate-consistency.md` if it exists (style, worldbuilding, character continuity)

Not all inputs need to exist. If only some are available, work with what you have.

## Review inputs before editing

### Reader review
Reader feedback is natural language with no file paths. Translate it into actionable edits:
- Plot summary issues → compare against `plot.md` beats
- Character depiction concerns → check character sheets and character style files
- Vibe/atmosphere notes → consider tone adjustments in the prose
- Scene assessment → locate the relevant section by context

### Lectorate consistency check
Lectorate feedback references specific file paths and section numbers. For each issue:
- Style assessments → consult `meta-mainmatter/style/style policy.md` and the relevant style files
- Worldbuilding continuity → consult `meta-mainmatter/worldbuilding/worldbuilding policy.md` and place files
- Character continuity → consult character sheets in `meta-mainmatter/characters/character sheets/`
- Plot structure → check against `plot.md`
- Governance compliance → follow `rules.md`

### Chapter metadata
The meta file records the chapter's design intent. Preserve or update:
- POV character
- Timeline placement
- Locations and characters
- Style notes (writer's own flags)
- Bump the revision number after editing

## Editing principles

### Consult the style inheritance chain
When deciding how to edit, follow this order:
1. `default style.md` — starting defaults (advisory)
2. `global style.md` — active project style
3. Chapter style file (if one exists in `meta-mainmatter/style/chapter styles/`)
4. Character style (for character-owned language)
5. Current human instruction

### Preserve authorial intent
Do not flatten the prose toward a neutral baseline. Style deviations that are deliberate should be preserved. The lectorate check identifies which deviations may be accidental — focus there.

### Track meaningful changes
After editing, update the meta file:
- Increment the revision number
- Note what changed and why

### Cuttable beauty
Be willing to cut elegant passages that don't serve the scene. See Prose Craft in `default style.md`.

## Worldbuilding during edits
When an edit touches worldbuilding details:
- Follow `meta-mainmatter/worldbuilding/worldbuilding policy.md`
- Respect persistence scale (section-level vs chapter-level vs super-chapter-level)
- Do not introduce super-chapter-level changes without asking

## When to ask the user
- If reader and lectorate feedback conflict
- If a suggested change would alter plot structure
- If super-chapter-level worldbuilding is affected
- If style inheritance is ambiguous
- If the edit would change POV or timeline
