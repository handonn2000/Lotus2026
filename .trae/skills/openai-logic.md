# OpenAI Logic Skill

This skill provides expertise in leveraging OpenAI models for generating pedagogical logic, lesson summaries, and interactive dialogue for the Cartoon Tutor.

## Key Capabilities
- **Prompt Engineering**: Designing effective system and user prompts for educational context.
- **Structured Outputs**: Using JSON mode or function calling to get predictable responses for session summaries.
- **Streaming Responses**: Implementing real-time text streaming for low-latency feedback.
- **Cost & Token Management**: Optimizing prompt length and choosing the right model (e.g., GPT-4o vs GPT-4o-mini).

## Usage Guidelines
- Use clear and concise system prompts to define the tutor's persona and pedagogical approach.
- Always validate the structure of JSON outputs from the LLM before processing.
- Implement retry logic with exponential backoff for API rate limits and transient errors.
- Use the `gpt-4o` model for complex reasoning and `gpt-4o-mini` for simpler, high-throughput tasks.

## Reference Documentation
- [OpenAI API Documentation](https://platform.openai.com/docs/)
- [OpenAI Cookbook](https://github.com/openai/openai-cookbook)
