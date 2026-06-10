# chapter exchange workflow

Policy for the writer-reader-lectorate review cycle using a shared chapter exchange space at `meta-mainmatter/chapters/`.

## Naming convention

Every chapter produces up to four files:

| File | Created by | Purpose |
|---|---|---|
| `mainmatter/Chap{N}.md` | writer | The prose |
| `meta-mainmatter/chapters/Chap{N}-meta.md` | writer | Chapter metadata |
| `meta-mainmatter/chapters/Chap{N}-reader-rev.md` | reader | Reader-perspective review |
| `meta-mainmatter/chapters/Chap{N}-lectorate-consistency.md` | lectorate | Consistency check |

`{N}` is a zero-padded three-digit chapter number: `001`, `002`, ..., `999`.

## Chapter cycle

1. **Writer** drafts `mainmatter/Chap{N}.md` and `meta-mainmatter/chapters/Chap{N}-meta.md` together. The meta file records: POV character, timeline placement, locations, characters who appear, word count, and any style notes.
2. **Reader** reads `mainmatter/Chap{N}.md` and writes `meta-mainmatter/chapters/Chap{N}-reader-rev.md` — natural-language impressions only, no metadata references.
3. **Lectorate** reads `mainmatter/Chap{N}.md` and writes `meta-mainmatter/chapters/Chap{N}-lectorate-consistency.md` — style assessment against the seven categories, worldbuilding/character continuity check, and governance compliance.

Steps 2 and 3 can run in parallel. The writer may revise the chapter after receiving feedback — load the `writer-edit` skill, increment the meta file's revision field, and note what changed.

## Meta file template (`Chap{N}-meta.md`)

```markdown
# Chap{N} — {Chapter Title}

- **POV:** {character name}
- **Timeline:** {relative or absolute date}
- **Locations:** {list}
- **Characters:** {list}
- **Word count:** {number}
- **Revision:** {number}
- **Style notes:** {optional — anything the writer wants to flag}
```

## Review file conventions

Reader and lectorate review files follow freeform markdown. The reader uses natural language (no paths, no section numbers). The lectorate references specific file paths and section numbers.

Both should begin with a summary line:

```markdown
# Chap{N} — Reader review

**Overall:** one-sentence verdict
```

```markdown
# Chap{N} — Lectorate consistency check

**Overall:** one-sentence verdict
```
