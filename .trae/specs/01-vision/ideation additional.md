# Lotus2026: Voice-First Cartoon Tutor

## 1. Project Vision
A friendly, interactive cartoon avatar that serves as a personalized voice tutor for students, guided by teacher-provided insights and adaptive learning behavior.

Lotus2026 aims to bridge AI tutoring and real classroom teaching by allowing teachers to shape how the AI teaches each individual student.

---

## 2. Core Components

### A. Voice-First Interaction
- **Avatar**: Lightweight web/mobile interface with a friendly cartoon character  
  - States: listening, thinking, speaking  
- **Voice Stack**: 
  - **Agora**: Real-time voice delivery (teacher calls, group sessions)
  - **ElevenLabs**: Primary high-quality tutor voice (female, kid-friendly)
  - **OpenAI**: Conversational reasoning + optional STT/TTS fallback
- **Voice Modes**:
  - Warm (default)
  - Playful (young learners)
  - Calm (low-confidence students)
  - Encouraging (feedback mode)
- **Flow Control (State Machine)**:
  - Intro → Lesson → Guided Practice → Quiz → Feedback → Wrap-up
- **Micro-interactions**:
  - Instant feedback (“Great job!”, “Try again!”)
  - Silence detection (“Are you still there?”)
  - Turn-taking management

---

### B. Teacher-Informed Personalization
- **Teacher Dashboard Input**:
  - Ratings:
    - confidence, participation, focus
    - speaking, listening, vocabulary, pronunciation
  - Tags:
    - `needs_hints`
    - `visual_learner`
    - `playful_persona`
    - `shy`
    - `needs_encouragement`
  - Focus areas:
    - phonics, sentence building, vocabulary, etc.

- **Student Profile Engine**:
  - Converts teacher input → structured profile
  - Generates:
    - summary traits
    - support level (low / medium / high)
    - recommended tutor style

- **Personalization Engine**:
  - Injects profile into AI prompt
  - Controls:
    - difficulty
    - tone
    - hint timing
    - explanation style

- **Dynamic Adaptation Rules**:
  - `needs_hints = true` → early scaffolding
  - `visual_learner = true` → imagery-based explanation
  - `confidence = low` → simpler questions + encouragement
  - `speaking = strong` → open-ended questions
  - `focus = low` → shorter interactions

---

### C. Learning Experience Engine
- **Lesson Engine**:
  - AI-generated or predefined lessons
  - Topic-based (colors, animals, phonics, etc.)

- **Adaptive Difficulty System**:
  - Increase difficulty when correct
  - Decrease or scaffold when struggling

- **Interactive Quiz System**:
  - 2–3 quick questions per session
  - Immediate feedback + retry

- **Mistake Memory**:
  - Track repeated mistakes
  - Reinforce weak areas in next sessions

- **Gamification Layer (v2)**:
  - Stars / rewards
  - Streak tracking
  - Achievements

---

### D. Review & Reporting Loop
- **Session Summaries**:
  - Generated from transcript + profile
  - Includes:
    - Wins
    - Focus Areas
    - Suggested Next Steps

- **Parent Comment Generator**:
  - Short, warm, positive
  - Parent-friendly language

- **Teacher Report**:
  - Structured:
    - strengths
    - areas to monitor
    - next steps

- **Persona Persistence**:
  - Student profile evolves over time
  - Tutor adapts across sessions

- **Progress Tracking**:
  - Track improvement across sessions
  - Detect trends (e.g. speaking ↑, focus ↓)

---

### E. Session & State System
- **Session Model**:
  - sessionId
  - studentId
  - current state
  - transcript
  - timestamps

- **State Machine**:
  - Intro → Lesson → Practice → Quiz → Wrap-up

- **Transcript Storage**:
  - Used for:
    - summaries
    - personalization
    - progress tracking

- **Event Hooks**:
  - onAnswer → evaluate response
  - onMistake → trigger hint
  - onEnd → generate reports

---

## 3. Tech Stack & Constraints

- **AI / Logic**:
  - OpenAI (tutor reasoning, summaries, reports)
  - OpenRouter / AWS Kiro (optional routing)

- **Voice**:
  - ElevenLabs (primary TTS)
  - OpenAI (fallback STT/TTS)

- **Real-time**:
  - Agora (voice streaming, teacher interaction)

- 


## 5. Future Expansion Ideas 🚀

### AI & Learning
- AI-generated lesson plans (based on student profile)
- pronunciation scoring (speech analysis)


### Interaction & Experience
- emotion detection (engagement / frustration)
- multi-language tutor support
- voice emotion modulation (tone changes dynamically)
- custom avatar per student (character personalization)




---
