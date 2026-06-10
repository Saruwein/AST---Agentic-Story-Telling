# AST — Agentic Storytelling

AST is an experimental framework for writing and editing stories with agentic AI support.

The repository separates the manuscript from the meta-information an agent needs to work responsibly: style, characters, worldbuilding, continuity, and project rules.

This repo is a **template**. To start a new story, create a new repository from this template — you get the full agent workflow, skills, and structure, then fill in your own story content.

---

## Getting started

### Quickstart

1. Create a new repo from this template (GitHub: green "Use this template" button)
2. Clone your new repo
3. Open in opencode and type `/connect` to set up a provider
4. Start writing — ask the **writer** agent to draft your first chapter

### Open Code setup

Connect:
- type `/connect`
- find a provider or search 'other' to enter a custom provider
- enter API key when prompted
- opencode loads config from `.opencode/opencode.jsonc`

---

## Workflows

### Writing a chapter

1. Ask the **writer** agent to draft a chapter. It creates `mainmatter/Chap{N}.md` and the corresponding `meta-mainmatter/chapters/Chap{N}-meta.md`.
2. The writer consults `plot.md` for beats, style files for narrative guidance, and character/worldbuilding files for continuity.
3. Review the draft and ask for revisions.

### Reviewing a chapter

Once a chapter exists, two agents can review it in **parallel**:

| Agent | What it produces | Perspective |
|---|---|---|
| **reader** | `Chap{N}-reader-rev.md` | Natural-language impressions, no metadata access |
| **lectorate** | `Chap{N}-lectorate-consistency.md` | Style assessment, worldbuilding/character continuity, governance |

### Editing a chapter

After receiving reviews, ask the **writer** to edit the chapter. The `writer-edit` skill guides the revision:

- Incorporates reader and lectorate feedback
- References style policy and worldbuilding policy for continuity
- Preserves deliberate style choices while fixing accidental deviations
- Updates the meta file's revision number

### Using branches

    git checkout -b storyline/book-001
    git checkout -b experiment/nonlinear-structure
    git checkout -b translation/de

Write on branches, merge to `main` when stable. See [Git usage](#git-usage) below.

---

## Reference

### Agents

Six specialised agents help with different aspects of the project:

| Agent | Scope |
|---|---|
| **writer** | Drafts prose into `mainmatter/`, maintains `plot.md` (beat outline), manages the TOC, edits based on reviews, and creates writer appendices. Cannot restructure the worktree. |
| **reader** | Reads the story with no metadata access — summarises plot, depicts characters, assesses scenes, describes vibe. Natural language only. Sees `mainmatter/` and `appendix/public/`. |
| **lectorate** | Full metadata access for editorial review. Assesses style (7 categories), worldbuilding continuity, character continuity, plot structure, governance compliance, and reader load. Also maintains `frontmatter/` book metadata. |
| **publishing** | Manages book-level metadata in `frontmatter/` only — author, title, version, completion status, publication dates. |
| **worktree engineer** | Manages directory layout, file moves, and opencode configuration. Has zero authority over story content or meta-mainmatter files. |
| **general** | Default agent for open-ended tasks and research. |

Each agent carries its own permission rules. Ask an agent by name (`"act as writer"` or use the `/agent` command).

### Skills

| Skill | Use |
|---|---|
| `writer-plot` | Beat-level plot outlining with `plot.md` |
| `writer-prose` | Drafting chapter prose |
| `writer-edit` | Revising prose based on reader/lectorate feedback |
| `reader-analysis` | Natural-language summarisation, depiction, assessment, vibe |
| `lectorate-style` | Style assessment across seven categories |

Skills are loaded automatically when the task matches their description.

### Glossaries

- `glossary.md` — framework terms (all agents except reader reference this)
- `meta-mainmatter/glossary.md` — story-specific terms per branch (writer maintains, lectorate reads)
- `appendix/public/` may contain reader-facing glossaries for the finished book

### Project structure

See `project structure.md` for a full layout reference and `dev docs.md` for the architecture overview.

- Manuscript → `mainmatter/` (chapters named `Chap001.md`, `Chap002.md`, ...)
- Chapter exchange → `meta-mainmatter/chapters/` (meta, reader review, lectorate consistency)
- Style → `meta-mainmatter/style/`
- Characters → `meta-mainmatter/characters/`
- Worldbuilding → `meta-mainmatter/worldbuilding/`
- Plot outline → `plot.md`
- Agent and skill definitions → `.opencode/agents/` and `.opencode/skills/`

### Git usage

Use `main` as the stable production branch.

Create separate branches for storylines, experiments, translations, or major revisions:

    git checkout -b storyline/book-001
    git checkout -b experiment/nonlinear-structure
    git checkout -b translation/de

Commit changes often and write clear commit messages:

    git add .
    git commit -m "Draft chapter 001"
    git commit -m "Update global style notes"
    git commit -m "Track monastery kitchen worldbuilding"

Merge changes back into `main` only when they are stable and intended to become part of the project baseline.

To pull upstream template changes into your story repo:

    git remote add upstream https://github.com/Saruwein/AST---Agentic-Story-Telling
    git fetch upstream
    git cherry-pick <commit-hash>

### Legal note

AST is an experimental writing and workflow framework. It is provided as-is, without warranty.

Users are responsible for reviewing all AI-assisted outputs before publication or distribution. This includes checking for factual errors, copyright issues, privacy concerns, unwanted similarities to existing works, and compliance with applicable laws, contracts, platform rules, and publishing requirements.

The framework does not replace legal, editorial, or publishing advice.