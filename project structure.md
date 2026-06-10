# project structure.md

This file describes the project layout for agentic storytelling.

The project separates reader-facing manuscript files from agent-facing meta files. The goal is to help the agent preserve continuity, style, worldbuilding, and character design without overloading the story text.

## Root structure

```text
project/
|- .opencode/
|  |- agents/
|  |- skills/
|  |- opencode.jsonc
|- appendix/
|  |- appendix policy.md
|  |- public/
|  |- writer/
|- frontmatter/
|- mainmatter/
|- meta-mainmatter/
|  |- glossary.md
|  |- chapters/
|  |  |- Chap001-meta.md
|  |  |- Chap001-reader-rev.md
|  |  |- Chap001-lectorate-consistency.md
|  |- characters/
|  |  |- character sheets/
|  |  |- character design policy.md
|  |- style/
|  |  |- chapter styles/
|  |  |- character styles/
|  |  |- default style.md
|  |  |- global style.md
|  |  |- style policy.md
|  |- worldbuilding/
|  |  |- places/
|  |  |- timeline/
|  |  |- worldbuilding policy.md
|- plot.md
|- glossary.md
|- .gitignore
|- project structure.md
|- rules.md
|- README.md
```

## frontmatter

`frontmatter` contains book-level identity and publication metadata.

Useful files may include:

```text
book.md
title-page.md
preface.md
dedication.md
```

A `book.md` file may define:

```text
Title:
Human author:
Language:
Genre:
Version:
Publishing status:
Publishing date:
Mainmatter order:
Referenced global style file:
```

## mainmatter

`mainmatter` contains the actual story text.

Chapters follow the naming convention `Chap{N}.md` where `{N}` is a zero-padded three-digit number:

```text
mainmatter/
  table-of-contents.md
  Chap001.md
  Chap002.md
```

Each chapter uses stable section headings:

```markdown
# Chapter 001 — Arrival

## 001.001 — The Station

## 001.002 — The Wrong Name

## 001.003 — The Locked Room
```

Stable section headings let the agent discuss style, worldbuilding, timeline, and character continuity without changing the manuscript structure.

See `appendix/writer/chapter exchange workflow.md` for the full review cycle policy.

## glossaries

Two glossary files serve different scopes:

`glossary.md` at the project root defines framework terms — roles, agents, style categories, skills, policies. Maintained by the worktree engineer. Stable across branches.

`meta-mainmatter/glossary.md` tracks story-specific terms — character names, places, objects, concepts, events — with references to where they appear. Maintained by the writer. Changes per branch.

## appendix

`appendix` contains supplementary material split into two sections.

`appendix/public/` — reader-facing reference: glossaries, chronologies, character lists, worldbuilding summaries, maps, translator notes. Visible to the reader agent. Anything referenced in the TOC gets appended to the finished book.

`appendix/writer/` — working appendices for the writer: extended notes, alternate drafts, research. Not visible to the reader agent.

See `appendix/appendix policy.md` for access rules.

## meta-mainmatter

`meta-mainmatter` contains agent-facing files.

These files help the agent track style, worldbuilding, character design, continuity, and revision decisions.

### chapters

`meta-mainmatter/chapters/` is the shared exchange space for the writer-reader-lectorate review cycle.

Each chapter produces up to three files here alongside `mainmatter/Chap{N}.md`:

| File | Created by | Purpose |
|---|---|---|
| `Chap{N}-meta.md` | writer | POV, timeline, locations, characters, word count, revision number |
| `Chap{N}-reader-rev.md` | reader | Natural-language reader review |
| `Chap{N}-lectorate-consistency.md` | lectorate | Style, worldbuilding, character continuity check |

See `appendix/writer/chapter exchange workflow.md` for the full policy.

Meta files should remain lean. They should exist because they help with writing, editing, revision, translation, continuity, reader comprehension, or future decisions.

## style

`style` contains the project’s style system.

```text
style policy.md
= how the agent may handle style

default style.md
= starting stylistic defaults

global style.md
= active project-specific style

chapter styles/
= chapter-specific style notes

character styles/
= character voice and diction notes
```

Style means narrative behavior, not only prose surface.

## characters

`characters` contains character design and character facts.

```text
character design policy.md
= how the agent may design, extend, or alter characters

character sheets/
= character facts, relationships, knowledge, possessions, proximity, function, and continuity
```

Character voice belongs in:

```text
meta-mainmatter/style/character styles/
```

Character facts belong in:

```text
meta-mainmatter/characters/character sheets/
```

## worldbuilding

`worldbuilding` contains facts about the story world.

```text
worldbuilding policy.md
= how the agent may create, track, and revise worldbuilding

places/
= locale-based worldbuilding

timeline/
= semi-ordinal event order, fixed dates, and anachronism notes
```

Worldbuilding is tracked primarily by locale, with time as a dimension.

The timeline is an index of event order. It is not the main storage location for worldbuilding.

## Lean-file principle

Do not create a file for every detail.

Create or update meta files when the information affects:

```text
drafting
editing
revision
translation
continuity
reader comprehension
future scenes
character behavior
plot logic
```

If a detail appears once and does not matter later, leave it in the manuscript.
