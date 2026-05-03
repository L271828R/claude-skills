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

5. **Write the PRD** covering:
   - Problem statement (link to BRD if one exists)
   - Goals and non-goals
   - User stories / acceptance criteria
   - Scope: what is in / out
   - Module design and key decisions
   - Open questions

6. **Submit** as a GitHub issue or save to a `prd/` directory in the repo, as the user prefers.
