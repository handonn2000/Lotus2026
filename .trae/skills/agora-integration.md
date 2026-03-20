# Agora Integration Skill

This skill provides specialized knowledge and best practices for integrating Agora's real-time voice streaming into the Lotus2026 platform.

## Key Capabilities
- **RTC Engine Management**: Best practices for initializing, joining, and leaving channels.
- **Audio Profile Configuration**: Optimal settings for voice-first interactions (e.g., speech-to-text accuracy).
- **Token Management**: Secure implementation of Dynamic Key/Token authentication.
- **Troubleshooting**: Diagnosing common network and audio quality issues.

## Usage Guidelines
- Always use the latest stable Agora SDK version.
- Implement proper lifecycle management to prevent memory leaks and unexpected audio behavior.
- Use `audioProfile: SpeechStandard` and `audioScenario: Education` for optimal voice quality.
- Monitor `onNetworkQuality` and `onRtcStats` to provide user feedback on connection health.

## Reference Documentation
- [Agora Documentation](https://docs.agora.io/en/)
- [Agora Web SDK API Reference](https://docs.agora.io/en/Video/API%20Reference/web_ng/index.html)
