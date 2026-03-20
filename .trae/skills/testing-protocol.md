# Testing Protocol Skill

This skill outlines the testing strategy and procedures for the Lotus2026 project, ensuring high reliability and zero regressions.

## Testing Strategy
- **Unit Tests**: Target individual functions and components (Jest, React Testing Library).
- **Integration Tests**: Verify the interaction between different modules and APIs (Supertest).
- **E2E Tests**: Simulate real user journeys using Playwright or Cypress.
- **Visual Regression**: Ensure UI consistency using tools like Storybook and Chromatic.

## Best Practices
- Aim for >80% code coverage on all new business logic.
- Mock external dependencies (like OpenAI and Agora) in unit and integration tests.
- Write descriptive test case names that clearly state the expected behavior.
- Ensure tests are independent and can be run in any order.

## CI/CD Integration
- Tests are automatically executed on every pull request via GitHub Actions.
- Deployments are blocked if the test suite fails.
