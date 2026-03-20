# Feature Specification: Skill Navigator

## 1. Overview
The **Skill Navigator** is a meta-skill designed to help AI agents (and users) discover, evaluate, and select the most appropriate skills from the extensive `.trae/skills` library (currently 170+ skills). It acts as a specialized search and recommendation engine.

## 2. User Stories
- As an agent, I want to find the best skill for a specific task (e.g., "how to implement Agora") without manually browsing hundreds of folders.
- As a user, I want to know what capabilities are available in the project's skill library.
- As an agent, I want to ensure I'm using the most relevant and up-to-date skill for my current objective.

## 3. Functional Requirements
### 3.1. Skill Discovery
- Search `.trae/skills` using keywords and semantic context.
- Analyze skill descriptions and frontmatter metadata (name, description, category).

### 3.2. Evaluation & Selection
- Rank skills based on relevance to the current task.
- Provide a clear rationale for why a specific skill is recommended.
- Identify "Skill Chains" (e.g., use `brainstorming` before `senior-fullstack`).

### 3.3. Usage Guidance
- Provide the exact `@invoke` syntax for the recommended skill.
- Briefly explain the core "how-to" of the recommended skill.

## 4. Technical Design
### 4.1. Implementation Detail
- The skill will be defined in `.trae/skills/skill-navigator/SKILL.md`.
- It will leverage terminal tools (`grep`, `ls`) and IDE search capabilities (`SearchCodebase`) to explore the skills directory.

### 4.2. Metadata Schema
Skills in the library follow the standard frontmatter format:
```markdown
---
name: skill-name
description: "Brief summary"
category: "Development | Design | Planning | etc."
---
```

## 5. Acceptance Criteria
- [ ] Successfully finds relevant skills for a given query (e.g., "auth", "testing", "agora").
- [ ] Recommends at least one primary skill and explains why.
- [ ] Provides the correct invocation command.
- [ ] Handles cases where no relevant skill is found gracefully.
