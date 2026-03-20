# Accessibility Checker Skill

This skill provides guidelines and best practices for ensuring the Lotus2026 Cartoon Tutor is accessible to all students, following WCAG standards.

## Key Guidelines
- **Semantic HTML**: Use proper HTML elements (e.g., `<button>`, `<nav>`, `<main>`) to ensure screen reader compatibility.
- **Color Contrast**: Maintain a contrast ratio of at least 4.5:1 for normal text and 3:1 for large text.
- **Keyboard Navigation**: Ensure all interactive elements are reachable and usable via keyboard alone.
- **ARIA Attributes**: Use ARIA labels and roles sparingly but correctly when standard HTML is insufficient.

## Testing for Accessibility
- Use automated tools like Axe-core and Lighthouse during development.
- Perform manual testing with screen readers (VoiceOver, NVDA).
- Ensure focus states are clearly visible for all interactive elements.

## Voice UI Considerations
- Provide visual alternatives for all important voice-conveyed information.
- Ensure real-time visual feedback for voice input (e.g., "Tutor is listening...").
