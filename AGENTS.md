# AGENTS.md

Project-level context for AI coding agents working in this repository.

## What this repo is

A tutorial repo that teaches how to build and use agent skills in Claude Code. The main example is a `pr-description` skill that writes pull request descriptions for the companion project, [my-website](https://github.com/janetjotw/my-website).

The audience is technical writers and developers who are new to agent configuration. Content should teach by walking through real steps, not by explaining concepts in the abstract.

## Repository structure

```
claude-skills/
├── AGENTS.md                  ← this file: project-level context
├── CLAUDE.md                  ← imports AGENTS.md for Claude Code
├── README.md                  ← overview and structure guide
├── agent-skill-building.md    ← main tutorial (PR description skill)
└── .claude/
    ├── skills/                ← task-specific instructions (one folder per skill)
    │   └── <task>/SKILL.md
```

## How the pieces differ

| File type | Loads when | Purpose |
|---|---|---|
| `AGENTS.md` / `CLAUDE.md` | Always | Project context and conventions |
| `skills/<task>/SKILL.md` | The request matches the skill's `description` | A repeatable task with a defined output |

## Writing conventions

Follow the conventions already used in `agent-skill-building.md`:

- Tutorial pages start with frontmatter containing `sidebar_position`.
- Use a single H1 for the page title, then `## Step N: <imperative verb phrase>` for each step.
- Put every command, prompt, and file excerpt in a fenced code block.
- Explain what a command does immediately after showing it.
- Use plain, direct language. Prefer short paragraphs and second person ("you").
- Show expected output or behavior after each step so readers can tell they are on track.

## SKILL.md conventions

Every skill file must have:

- Frontmatter with `name` and `description`. The description states what the skill does and when to use it, because Claude Code uses it to decide whether the skill matches a request.
- Numbered steps the agent follows in order.
- An explicit output format, shown as a template.
- Exit criteria: how the agent knows the task is complete.

## Definition of done

A change is complete when:

1. Every command in a tutorial step has been run and works as written.
2. Code blocks are copy-pasteable with no placeholder text left behind.
3. Any new skill has valid frontmatter and a description that says when to use it.
4. File paths in the text match the actual structure in this repo.
5. The README structure section still matches the repo.

## Boundaries

- Do not invent command output. If you have not run a command, say so or ask.
- Do not describe Claude Code behavior you have not verified. Link to the official documentation instead.
- Do not change the step order in `agent-skill-building.md` without updating any text that refers to steps by number.
- Do not commit or push unless the user asks.
- Ask before deleting or renaming files.
