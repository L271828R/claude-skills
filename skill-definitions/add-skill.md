---
name: add-skill
description: Add a new skill to the personal skills repo using the router pattern. Use when the user wants to add, create, or register a new personal skill.
---

# Add a Skill

The personal skills repo lives at `/Users/rueda/projects/skills/` and uses a pull-based router pattern:
- `skills/router/SKILL.md` — the router (always loaded, tiny index table)
- `skill-definitions/<name>.md` — full skill content (read on demand, never auto-loaded)

## Steps

1. **Ask** for the skill name, trigger phrases, and what the skill should do (if not already provided).

2. **Create** the skill definition file at `/Users/rueda/projects/skills/skill-definitions/<name>.md` with this format:
   ```
   ---
   name: <name>
   description: <one-line description of when to use it>
   ---

   <full skill instructions>
   ```

3. **Add a row** to the router table in `/Users/rueda/projects/skills/skills/router/SKILL.md`:
   - Add to the `| Skill | Triggers | Definition |` table
   - Update the frontmatter `description:` field to mention the new skill name and its trigger

4. **Confirm** by reading back both files to the user.

## Rules
- Skill name: lowercase, hyphenated (e.g. `grill-me`, `add-skill`)
- Triggers: list the slash command and any natural language phrases that should activate it
- Definition path: always `/Users/rueda/projects/skills/skill-definitions/<name>.md`
- Keep the router table row concise — one line per skill
