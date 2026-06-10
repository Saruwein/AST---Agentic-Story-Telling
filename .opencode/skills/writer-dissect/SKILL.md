---
name: writer-dissect
description: >-
  Analyze. Dissect. Import. Extract. Process user generated content into
  chapters, sections, characters, places, timeline.
---

## Import workflow

Use this when the user provides raw story text in `user generated content/source/`.

### Phase 1 — Ingest

Read all files from `user generated content/source/`. If there are notes in `user generated content/notes/`, read those too for authorial intent.

### Phase 2 — Propose structure

Analyse the text to identify narrative breaks:
- Existing chapter markers, Part dividers, `***`, `---`, or similar section breaks
- Scene shifts (change of location, time skip, POV switch, new character arrival)
- Natural resting points (cliffhanger, resolution, thematic shift)

For each candidate chapter:
- Assign a provisional title (use the existing heading if one exists)
- Identify its sections with tentative `## NNN.MMM — Title` headings
- Note which characters, locations, and timeline period appear
- Estimate relative length

Present the proposed structure to the user as a flat list:

```text
Chap001 — [Title] (sections: 001.001–001.003, chars: A, B, loc: Tavern)
Chap002 — [Title] (sections: 002.001–002.002, chars: C, D, loc: Forest)
…
```

**Do not write any files until the user approves.**

### Phase 3 — Apply sectioning

After the user approves (or adjusts) the structure:

1. Write each chapter into `mainmatter/Chap{N}.md` with stable section headings
2. Preserve pre-existing section markers — if the original had `## Chapter 1`, keep the break but re-head it `# Chapter 001 — Title` / `## 001.001 — Original Subtitle`
3. If the text had no sectioning, insert breaks at the approved boundaries

### Phase 4 — Extract initial metadata

For each chapter, create `meta-mainmatter/chapters/Chap{N}-meta.md`:

```markdown
# Chap{N} — {Title}

- **POV:** {character name or unknown}
- **Timeline:** {relative or absolute date, or unknown}
- **Locations:** {list}
- **Characters:** {list}
- **Word count:** {number}
- **Revision:** 1
- **Style notes:** {first impressions — tone, pacing, density}
```

### Phase 5 — Propose persistent records

Scan all chapters for recurring elements. Use persistence scale:

| Persistence | Action |
|---|---|
| **Section-level** (appears once) | Leave in manuscript only |
| **Chapter-level** (multiple sections, one chapter) | Log to the chapter meta file. Inform the user. |
| **Multi-chapter** (appears in 2+ chapters) | Propose a character sheet, place file, or timeline entry. Ask before creating. |

For each multi-chapter character, propose:

```text
Character: {name}
Appears in: {chapters}
Role: {protagonist / antagonist / ally / minor / unknown}
Traits evident from text: {short list}
→ Create character sheet? (y/n)
```

For each multi-chapter location, propose:

```text
Place: {name}
Appears in: {chapters}
Type: {city / building / region / etc.}
→ Create place file? (y/n)
```

For major timeline events, propose:

```text
Event: {summary}
Chapters: {list}
→ Add to timeline? (y/n)
```

Apply only what the user confirms. For confirmed items, use the templates from `meta-mainmatter/worldbuilding/worldbuilding policy.md` (places) and `meta-mainmatter/characters/character design policy.md` (character sheets).
