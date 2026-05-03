# Personal Skills

A personal skill library for Claude Code using a pull-based router pattern.

## How it works

Instead of loading all skill content into context on every session (push), only a small router index is always loaded. Full skill definitions are read from disk on demand when a skill is actually triggered (pull).

```
skills/
  router/
    SKILL.md              ← tiny index, always in Claude's context
skill-definitions/
  grill-me.md             ← full content, read only when triggered
  add-skill.md
```

## Adding a skill

Say "add a skill" or `/add-skill` to Claude. It will walk you through creating the definition file and wiring it into the router.

Manually:
1. Create `skill-definitions/<name>.md` with the full skill instructions
2. Add a row to `skills/router/SKILL.md`

## Skills

| Skill | Triggers | Description |
|-------|----------|-------------|
| grill-me | `/grill-me`, "grill me" | Relentlessly interviews you about a plan until reaching shared understanding |
| add-skill | `/add-skill`, "add a skill", "new skill" | Adds a new skill to this repo using the router pattern |
| write-a-prd | `/write-a-prd`, "write a prd", "plan a feature" | Creates a PRD via interview + codebase exploration (see skill for PRD vs BRD distinction) |

## Claude Code integration

The repo is symlinked into Claude's plugin directory so skills are picked up automatically:

```
~/.claude/plugins/marketplaces/personal-skills/plugins/personal → this repo
```

Changes to this repo are live immediately — no restart or sync needed.
