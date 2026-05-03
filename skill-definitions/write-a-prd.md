---
name: write-a-prd
description: Create a PRD (Product Requirements Document) through user interview, codebase exploration, and module design. Use when the user wants to write a PRD, create a product requirements document, or plan a new feature.
---

# Write a PRD

## What is a PRD (and how it differs from a BRD)

A **BRD (Business Requirements Document)** captures the *problem*:
- Why are we doing this?
- What business pain or opportunity exists?
- What does success look like in business terms?
- Technology-agnostic. Stable. Written for stakeholders.

A **PRD (Product Requirements Document)** captures a *solution to that problem*:
- What exactly are we building?
- What are the features, user stories, and acceptance criteria?
- What is in scope and out of scope?
- Technology-adjacent. Volatile — gets revised as you learn more.

**A BRD can spawn multiple PRDs.** One problem may have several solution approaches, phases, or A/B variants. Always link the PRD back to its parent BRD if one exists.

---

## Steps

You may skip steps if you don't consider them necessary.

1. **Ask** the user for a long, detailed description of the problem they want to solve and any potential ideas for solutions. Ask if a BRD already exists for this problem — if so, read it before proceeding.

2. **Explore the repo** to verify their assertions and understand the current state of the codebase.

3. **Interview the user relentlessly** about every aspect of this plan until you reach a shared understanding. Walk down each branch of the design tree, resolving dependencies between decisions one-by-one.

4. **Sketch out the major modules** you will need to build or modify to complete the implementation. Actively look for opportunities to extract deep modules that can be tested in isolation.

   A **deep module** (as opposed to a shallow module) is one which encapsulates a lot of functionality in a simple, testable interface which rarely changes.

   Check with the user that these modules match their expectations. Check with the user which modules they want tests written for.

5. **Write the PRD** using the template below. The PRD should be self-contained — a developer with no prior context should be able to read it and know exactly what to build.

6. **Submit** as a GitHub issue or save to a `prd/` directory in the repo, as the user prefers.

---

## PRD Template

```markdown
# PRD: [Feature Name]

**Status:** Draft | In Review | Approved  
**Author:** [name]  
**Date:** [date]  
**BRD:** [link or "none"]

---

## Problem Statement
[What problem does this solve? Who has the problem? What is the impact?]

## Goals
- [Measurable goal 1]
- [Measurable goal 2]

## Non-Goals
- [Explicitly out of scope — prevents scope creep]

## User Stories
- As a [user], I want to [action] so that [outcome].

## Acceptance Criteria
- [ ] [Specific, testable condition]
- [ ] [Specific, testable condition]

## Module Design

### Modules to build
| Module | Responsibility | Interface | Tests needed |
|--------|---------------|-----------|--------------|
| [name] | [what it does] | [public API shape] | Yes / No |

### Modules to modify
| Module | Current behavior | Change required |
|--------|-----------------|-----------------|
| [name] | [what it does now] | [what changes] |

## Key Decisions
| Decision | Options considered | Choice | Reason |
|----------|--------------------|--------|--------|

## Open Questions
- [ ] [Question that needs resolution before or during implementation]

## Out of Scope
- [Thing that came up but is explicitly excluded]
```
