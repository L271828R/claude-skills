---
name: skills-router
description: Personal skills router. When user invokes /grill-me, says "grill me", or triggers any personal skill by name, read its definition from disk and execute it. Skills: grill-me (stress-test a plan or design), add-skill (add a new skill to this repo), write-a-prd (create a product requirements document).
---

Personal skill index — read the file when the skill is triggered, then follow its instructions:

| Skill | Triggers | Definition |
|-------|----------|------------|
| grill-me | /grill-me, "grill me" | /Users/rueda/projects/skills/skill-definitions/grill-me.md |
| add-skill | /add-skill, "add a skill", "new skill" | /Users/rueda/projects/skills/skill-definitions/add-skill.md |
| write-a-prd | /write-a-prd, "write a prd", "create a prd", "plan a feature" | /Users/rueda/projects/skills/skill-definitions/write-a-prd.md |

When triggered: Read the file at the listed path and execute the skill defined there.
