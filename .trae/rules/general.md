# General Project Rules

These rules apply to all aspects of the Lotus2026 project to maintain high standards and consistent delivery.

## Project Vision
- **Voice-First**: Every feature should be designed with voice interaction as the primary interface.
- **Student-Centric**: Prioritize the learning experience and safety of students.
- **Privacy by Design**: Protect student data and follow all educational data privacy regulations.

## Workflow Rules
- **Skill Discovery**: For any new task or feature, first use `@skill-navigator` to identify the most relevant skills from the `.trae/skills` library.
- **Spec-Driven Development**: All development MUST follow the process defined in [spec-driven-development.md](file:///Users/handonn/Workplace/Lotus2026/.trae/rules/spec-driven-development.md). Implementation is only allowed after Step 4 has been approved by the user.
- **Plan Before Implementation**: Always create a plan first and ask for user confirmation before implementing any code changes.
- **Atomic Commits**: Each commit should represent a single, logical change.
- **Pull Request Reviews**: All code changes must be reviewed by at least one other team member.
- **No Direct Push to Main**: All changes must go through a feature branch and pull request.
- **Automated Testing**: No pull request will be merged if automated tests fail.

## Documentation Rules
- **Update Documentation**: Any change in functionality must be accompanied by an update to relevant documentation.
- **Self-Documenting Code**: Prefer clear variable and function names over excessive comments.
- **Keep it Simple**: Avoid over-engineering; aim for the simplest solution that meets the requirements.
