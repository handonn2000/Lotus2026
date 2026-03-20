---
name: skill-navigator
description: "Universal skill finder and discovery engine. Use when you need to find the best skill for a task from the extensive .trae/skills library."
category: "Planning | Discovery"
---

# Skill Navigator

## Overview
The **Skill Navigator** is a specialized meta-skill designed to help agents and users navigate the project's extensive skill library. It provides semantic search, categorization, and recommendation capabilities to ensure the right tools are used for every task.

## When to Use
- Use when you are unsure which skill applies to a specific task.
- Use when you want to explore the project's capabilities.
- Use when you're starting a new feature, debugging a complex issue, or planning a development sprint.

## Instructions

### 1. Identify the Task Goal
- Clearly state the objective of the current task (e.g., "implement authentication", "fix a memory leak", "design a voice UI").

### 2. Search the Skill Library
- Perform a search in the `.trae/skills` directory using keywords related to the task.
- Look for `SKILL.md` files and analyze their `name` and `description` in the frontmatter.

### 3. Evaluate and Recommend
- Select the most relevant skill(s).
- Provide a brief rationale for the recommendation.
- Check for "Skill Chains": Some tasks require a sequence of skills (e.g., `brainstorming` -> `plan-writing` -> `senior-fullstack`).

### 4. Provide Invocation Details
- For each recommended skill, provide the exact `@invoke` syntax.
- Briefly describe the first step to take with that skill.

## Example Recommendations

### Task: "Implement a new API endpoint for student reports"
- **Primary Skill**: `@api-patterns` (to design the endpoint correctly)
- **Secondary Skill**: `@senior-fullstack` (for the actual implementation)
- **Rationale**: Designing the API structure first ensures consistency and scalability before writing code.

### Task: "Fix a bug where the voice avatar stops responding"
- **Primary Skill**: `@systematic-debugging` (to identify the root cause)
- **Secondary Skill**: `@agora-integration` (if the issue is in the voice stream)
- **Rationale**: A systematic approach to debugging prevents guesswork and ensures a reliable fix.

## Quick Search Command (for agents)
```bash
grep -r "description:" .trae/skills/ | grep -i "YOUR_KEYWORD"
```
