# Product Requirement Document: Lotus2026

## 1. Goal
To build a voice-first, interactive cartoon tutor that personalizes its teaching style based on teacher-provided insights.

## 2. User Roles & Agents
### User Roles
- **Student**: Interacts with the cartoon avatar via voice for learning sessions.
- **Teacher**: Inputs student metadata (tags/scores) and receives session reports.

### Assigned Agents
- [Product Owner](file:///Users/handonn/Workplace/Lotus2026/.trae/agents/product-owner.md): Vision & Backlog.
- [UI/UX Designer](file:///Users/handonn/Workplace/Lotus2026/.trae/agents/ui-ux-designer.md): Avatar & Dashboard Design.
- [Front-end Developer](file:///Users/handonn/Workplace/Lotus2026/.trae/agents/front-end-developer.md): Client Implementation.
- [Back-end Developer](file:///Users/handonn/Workplace/Lotus2026/.trae/agents/back-end-developer.md): AI & State Orchestration.
- [Quality Engineer](file:///Users/handonn/Workplace/Lotus2026/.trae/agents/quality-engineer.md): Testing & Validation.

## 3. Key Requirements
### R1: Voice Interface
- **R1.1**: Real-time voice streaming with low latency (<500ms).
- **R1.2**: Visual feedback from the avatar when it's "listening" or "speaking."
- **R1.3**: Automatic transcription of student replies.

### R2: Teacher Dashboard (v1)
- **R2.1**: A simple UI to select a student and set/update tags.
- **R2.2**: Pre-defined tag set: `needs_hints`, `visual_learner`, `playful_persona`, `focus_areas`.

### R3: Personalization Engine
- **R3.1**: The tutor's system prompt must dynamically include current teacher tags.
- **R3.2**: Adaptive feedback: If `needs_hints` is high, the AI should offer more scaffolding.

### R4: Reporting
- **R4.1**: Post-session summary generation within 30 seconds of session end.
- **R4.2**: Bullet-point "Wins" and "Focus Areas" for teachers.

## 4. Success Metrics (Hackathon Focus)
- Successful 2-way voice conversation.
- Demonstrated change in AI tone based on a teacher tag toggle.
- Generated summary report at the end of a 3-minute demo.
