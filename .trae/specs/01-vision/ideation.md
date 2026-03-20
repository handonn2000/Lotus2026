# Lotus2026: Voice-First Cartoon Tutor

## 1. Project Vision
A friendly, interactive cartoon avatar that serves as a personalized tutor for students, bridgeable by teacher-driven insights.

## 2. Core Components
### A. Voice-First Interaction
- **Avatar**: Lightweight web/mobile interface with a friendly cartoon character.
- **Voice Stack**: 
  - **Agora**: Real-time voice streaming (10,000 free minutes).
  - **ElevenLab**: voice generation 
  - **OpenAI**: Conversational logic and STT/TTS integration.
- **Flow Control**: State machine to manage lesson progress (Intro -> Lesson -> Quiz -> Wrap-up).

### B. Teacher-Informed Personalization
- **Dashboard**: Teachers input student performance data (tags/scores).
- **Personalization Engine**: Uses **OpenRouter** or **AWS Kiro** to blend teacher data with lesson content.
- **Dynamic Adaptation**: Adjusts vocabulary, tone, and feedback styles based on "needs hints," "visual learner," etc.

### C. Review & Reporting Loop
- **Session Summaries**: OpenAI processes transcripts and teacher tags into bullet-point insights for the teacher.
- **Persona Persistence**: Future sessions respect teacher-adjusted persona settings (e.g., Playful vs. Serious).

## 3. Tech Stack & Constraints
- **Logic/AI**: OpenAI (API Credits), OpenRouter/AWS Kiro.
- **Real-time**: Agora.
- **Deadlines**: Credits/Tiers expire March 20-21, 2026.
