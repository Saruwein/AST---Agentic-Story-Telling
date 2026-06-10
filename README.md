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

## How to work with agents

The human author owns the story.

Agents may help plan, draft, critique, edit, revise, translate, and track continuity. They should not silently make major creative, structural, stylistic, character, or worldbuilding changes.

Ask agents to work in clear modes:

    Plan this chapter.
    Draft this section.
    Critique this scene.
    Revise this passage.
    Check continuity.
    Update the relevant meta files.

When a change is large, the agent should propose it first by showing:

    Current version:
    Proposed change:
    Reason:
    Risk:
    Authorization needed:

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