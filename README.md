# AST — Agentic Storytelling

AST is an experimental framework for writing and editing stories with agentic AI support.

The repository separates the manuscript from the meta-information an agent needs to work responsibly: style, characters, worldbuilding, continuity, and project rules.

## How to use this Git repo

Use `main` as the stable production branch.

Create separate branches for storylines, experiments, translations, or major revisions.

    git checkout -b storyline/book-001
    git checkout -b experiment/nonlinear-structure
    git checkout -b translation/de

Commit changes often and write clear commit messages.

    git add .
    git commit -m "Draft chapter 001"
    git commit -m "Update global style notes"
    git commit -m "Track monastery kitchen worldbuilding"

Merge changes back into `main` only when they are stable and intended to become part of the project baseline.


## Open Code 

Connect:
* type '/connect'
* find a provider or
  search 'other' to enter a custom provider
* enter API key when prompted
* privide opencode.json


## Agents

Six specialised agents help with different aspects of the project:

| Agent | Scope |
|---|---|
| **writer** | Drafts prose into `mainmatter/`, maintains `plot.md` (beat outline), manages the TOC, and creates writer appendices. Cannot restructure the worktree. |
| **reader** | Reads the story with no metadata access — summarises plot, depicts characters, assesses scenes, describes vibe. Natural language only. Sees `mainmatter/` and `appendix/public/`. |
| **lectorate** | Full metadata access for editorial review. Assesses style (7 categories), worldbuilding continuity, character continuity, plot structure, governance compliance, and reader load. Also maintains `frontmatter/` book metadata. |
| **publishing** | Manages book-level metadata in `frontmatter/` only — author, title, version, completion status, publication dates. |
| **worktree engineer** | Manages directory layout, file moves, and opencode configuration. Has zero authority over story content or meta-mainmatter files. |
| **general** | Default agent for open-ended tasks and research. |

Each agent carries its own permission rules. Ask an agent by name (`"act as writer"` or use the `/agent` command).

## Skills

- `writer-plot` — beat-level plot outlining with `plot.md`
- `writer-prose` — drafting and revising chapter prose
- `reader-analysis` — natural-language summarisation, depiction, assessment, vibe
- `lectorate-style` — style assessment across seven categories

Skills are loaded automatically when the task matches their description.

## How this applies here

AST uses the repo as a structured writing environment.

The manuscript lives in `mainmatter`.

Agent-facing notes live in `meta-mainmatter`.

Style is tracked under `meta-mainmatter/style`.

Characters are tracked under `meta-mainmatter/characters`.

Worldbuilding is tracked under `meta-mainmatter/worldbuilding`.

The goal is to make AI-assisted storytelling more controllable, traceable, and useful: the agent can help generate and revise text, but the project structure keeps the human author in control.

## Legal note

AST is an experimental writing and workflow framework. It is provided as-is, without warranty.

Users are responsible for reviewing all AI-assisted outputs before publication or distribution. This includes checking for factual errors, copyright issues, privacy concerns, unwanted similarities to existing works, and compliance with applicable laws, contracts, platform rules, and publishing requirements.

The framework does not replace legal, editorial, or publishing advice.