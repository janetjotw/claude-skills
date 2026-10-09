# Claude code - Agent skills

This project walks through building an agent skill from scratch: a PR description skill that works across my repo [project](https://github.com/janetjotw/my-website). Learn how to structure the SKILL.md file, test it, and understand how Claude Code discovers and matches skills to the requests.

## What's in this repo

```
claude-skills/
├── AGENTS.md                  ← project-level context for AI agents
├── CLAUDE.md                  ← imports AGENTS.md for Claude Code
├── README.md                  ← this file
├── agent-skill-building.md    ← the tutorial: building and using the PR description skill
└── .claude/
    └── skills/
        └── pr-description/
            └── SKILL.md       ← the skill the tutorial builds
```

Start with [agent-skill-building.md](agent-skill-building.md).


## Why use a skill instead of AGENTS.md?

`AGENTS.md` and a `SKILL.md` can hold similar instructions, but they load at different times.

| | `AGENTS.md` | `SKILL.md` |
|---|---|---|
| Loads | Always | When your request matches the skill's `description` |
| Holds | Facts and rules about the whole project | One repeatable task, with steps and an output format |
| Scope | One repository | One repository, or all your projects if stored in `~/.claude/skills/` |

Use `AGENTS.md` for what is always true, such as "Do not commit or push unless the user asks." Use a skill for a task you do on request, such as writing a PR description.

Putting every task in `AGENTS.md` works for a small project, but the agent then carries all of those instructions on every request. A skill keeps a task's instructions out of the way until you need them, and you can reuse it across projects instead of copying it into each repo.
