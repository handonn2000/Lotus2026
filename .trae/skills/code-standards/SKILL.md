# Code Standards Skill

This skill defines the coding standards and best practices for the Lotus2026 project, ensuring consistency and maintainability across the codebase.

## Key Standards
- **TypeScript First**: All new code should be written in TypeScript with strict type checking enabled.
- **Clean Code Principles**: Adhere to SOLID, DRY (Don't Repeat Yourself), and KISS (Keep It Simple, Stupid).
- **Functional Programming**: Prefer immutable data structures and pure functions where appropriate.
- **Naming Conventions**:
  - `camelCase` for variables and functions.
  - `PascalCase` for classes, interfaces, and React components.
  - `kebab-case` for file names and CSS classes.

## Linting & Formatting
- Use ESLint with the project's shared configuration.
- Use Prettier for consistent code formatting.
- Run `npm run lint` and `npm run format` before every commit.

## Documentation
- Document all public APIs using JSDoc/TSDoc.
- Maintain a clear and up-to-date `README.md` for each major module.
