# dev docs.md

Reference map of the project — for humans and agents. Points to where things live and what each file does.

---

## Entry points

| File | Purpose |
|---|---|
| `README.md` | Project overview, quickstart, template workflow |
| `project structure.md` | Full directory layout with descriptions of every folder |
| `rules.md` | Governance rules for agents |
| `glossary.md` | Framework term definitions (roles, agents, skills, policies) |

## Where agents live

`.opencode/agents/` — one Markdown file per agent, each with embedded frontmatter for permissions.

| File | Agent |
|---|---|
| `writer.md` | Drafts prose, maintains plot outline, manages glossary |
| `reader.md` | Natural-language story feedback, no metadata access |
| `lectorate.md` | Editorial review, style assessment, continuity check |
| `publishing.md` | Book-level metadata in `frontmatter/` |
| `worktree engineer.md` | Directory layout, file moves, opencode config |

All agents are `mode: subagent` and carry their own `permission:` rules.

## Where skills live

`.opencode/skills/<name>/SKILL.md` — one folder per skill.

| Skill | Triggers on |
|---|---|
| `writer-plot` | Plot outlining, beat structure, scene order |
| `writer-prose` | Drafting or revising chapter prose |
| `reader-analysis` | Reader-perspective feedback (summary, depiction, vibe) |
| `lectorate-style` | Style assessment against 7 categories |

Skills are loaded automatically when the task matches their `description`.

## Story content

| Path | What goes here | Managed by |
|---|---|---|
| `mainmatter/` | Chapter files, table of contents | writer |
| `plot.md` | Beat outline (named beats, no prose) | writer |
| `frontmatter/` | Book metadata (title, author, status) | publishing / lectorate |
| `appendix/public/` | Reader-facing appendices (maps, glossaries) | writer |
| `appendix/writer/` | Working notes, alternate drafts | writer |

## Meta (agent-facing) content

| Path | What goes here | Managed by |
|---|---|---|
| `meta-mainmatter/style/default style.md` | Starting stylistic defaults | lectorate |
| `meta-mainmatter/style/global style.md` | Active project style notes | lectorate |
| `meta-mainmatter/style/style policy.md` | How the agent may handle style | lectorate |
| `meta-mainmatter/style/chapter styles/` | Per-chapter style notes | lectorate |
| `meta-mainmatter/style/character styles/` | Per-character voice notes | lectorate |
| `meta-mainmatter/characters/character design policy.md` | How the agent may design/extend characters | lectorate |
| `meta-mainmatter/characters/character sheets/` | Facts, relationships, continuity per character | lectorate |
| `meta-mainmatter/worldbuilding/worldbuilding policy.md` | How the agent may manage worldbuilding | lectorate |
| `meta-mainmatter/worldbuilding/places/` | Locale-based worldbuilding | lectorate |
| `meta-mainmatter/worldbuilding/timeline/` | Event order, dates, anachronisms | lectorate |
| `meta-mainmatter/glossary.md` | Story-specific terms (places, names, objects) | writer |
| `meta-mainmatter/chapters/Chap{N}-meta.md` | Chapter metadata (POV, timeline, locations) | writer |
| `meta-mainmatter/chapters/Chap{N}-reader-rev.md` | Reader-perspective review | reader |
| `meta-mainmatter/chapters/Chap{N}-lectorate-consistency.md` | Consistency check (style, continuity) | lectorate |

## Configuration

| File | Purpose |
|---|---|
| `.opencode/opencode.jsonc` | Provider setup, model selection, agent overrides, permissions |
| `.opencode/skills/` | Skill definitions (auto-loaded) |
| `.opencode/agents/` | Agent persona files (auto-loaded) |
| `.gitattributes` | LF line endings for all text files |
| `.gitignore` | Standard ignores |

## Workflows

### Starting a new story
1. Create repo from this template
2. Clone and open in opencode
3. Set up a provider (`/connect`)
4. Ask the **writer** to draft a beat outline in `plot.md`
5. Ask the **writer** to draft chapter 001

### Branching for a storyline
```bash
git checkout -b storyline/my-story
```
Write on the branch. Merge to `main` when stable.

### Chapter exchange workflow
When a chapter is drafted:
1. **Writer** creates `mainmatter/Chap{N}.md` + `meta-mainmatter/chapters/Chap{N}-meta.md`
2. **Reader** reviews the chapter and writes `meta-mainmatter/chapters/Chap{N}-reader-rev.md`
3. **Lectorate** checks consistency and writes `meta-mainmatter/chapters/Chap{N}-lectorate-consistency.md`

### Reviewing style
Ask the **lectorate** agent to assess a chapter against the seven style categories.

### Restructuring the project
Ask the **worktree engineer** to move files, rename folders, or edit agent/skill definitions.

## Permission model

Each agent has its own `permission:` block in frontmatter:
- `read: * allow` — all agents can read the whole project
- `edit:` — scoped to what the agent is responsible for
- `bash:` — scoped to needed commands (git, mv, mkdir)
- `task:`, `question:`, etc. — generally allowed

See each agent file under `.opencode/agents/` for the exact rules.
