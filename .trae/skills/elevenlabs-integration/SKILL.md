---
name: elevenlabs-integration
description: Integrate ElevenLabs AI voice API (TTS/STT) via REST or official SDKs.
risk: safe
source: community
---

# ElevenLabs Integration (TTS/STT)

## Overview

ElevenLabs provides AI voice infrastructure for text-to-speech (TTS), speech-to-text (STT), voice cloning, conversational agents, and generative audio via a REST API plus official Python/TypeScript SDKs. Voices are referenced by a unique `voice_id` (for example `JBFqnCBsd6RMkjVDRZzb`) that you pass in API requests, and models control quality/latency/language coverage (for example `eleven_v3` for expressive 70+ languages, `eleven_flash_v2_5` for low-latency real-time). TTS usage is billed per character (1 credit per character of input text); other operations are billed by audio duration.

Base URL: `https://api.elevenlabs.io`

## When to Use This Skill

- Use when you need to add ElevenLabs TTS into an app (narration, IVR, voice UI).
- Use when you need STT transcription (batch file transcription or realtime streaming).
- Use when you need to pick/clone/design voices and manage `voice_id` lifecycles.
- Use when optimizing latency, audio formats (mp3/pcm/ulaw), or privacy/retention settings.

## How It Works

### Step 1: Authentication and key handling

- Use the `xi-api-key` header for server-to-server calls.
- Store the key in an environment variable (for example `ELEVENLABS_API_KEY`) and never log it.
- If you need client-side access, prefer a backend proxy or use short-lived tokens when supported by the capability.

### Step 2: Discover voices and select `voice_id`

- Call `GET /v1/voices` to list voices accessible to your account and select the `voice_id` you want to use.
- Keep `voice_id` as configuration (env/config/db), not hard-coded in multiple places.

### Step 3: Pick a model for the use case

- Real-time voice UI: `eleven_flash_v2_5` (optimized for low latency).
- Expressive multi-language output: `eleven_v3`.
- Default TTS model parameter is `eleven_multilingual_v2` on the TTS convert endpoint, but you can override `model_id`.

### Step 4: Convert text to speech (TTS)

- Use `POST /v1/text-to-speech/{voice_id}` to convert text into audio.
- Use `output_format` for the return encoding (mp3/pcm/ulaw). For telephony, `ulaw` is commonly used.
- For long text, split into chunks and pass `previous_text` / `next_text` or `previous_request_ids` / `next_request_ids` to maintain continuity.

### Step 5: Transcribe audio (STT)

- Use `POST /v1/speech-to-text/convert` to transcribe an audio/video file (multipart form upload or `cloud_storage_url`).
- For realtime transcription, use the WebSocket endpoint `wss://api.elevenlabs.io/v1/speech-to-text/realtime`.

## Examples

### List voices (REST)

```bash
curl https://api.elevenlabs.io/v1/voices \
  -H "Accept: application/json" \
  -H "xi-api-key: $ELEVENLABS_API_KEY"
```

### Create speech (TTS) and save to mp3 (REST)

```bash
curl -X POST "https://api.elevenlabs.io/v1/text-to-speech/6NGuyxq9eXrZtTqO2JHa?output_format=mp3_44100_128" \
  -H "xi-api-key: $ELEVENLABS_API_KEY" \
  -H "Content-Type: application/json" \
  --data '{
    "text": "Hello from ElevenLabs.",
    "model_id": "eleven_flash_v2_5",
    "voice_settings": {
      "stability": 0.5,
      "similarity_boost": 0.75
    }
  }' \
  --output speech.mp3
```

### Create speech (TTS) with TypeScript (Node fetch)

```typescript
import { writeFile } from 'node:fs/promises';

const apiKey = process.env.ELEVENLABS_API_KEY;
if (!apiKey) {
  throw new Error('Missing ELEVENLABS_API_KEY');
}

const voiceId = '6NGuyxq9eXrZtTqO2JHa';
const url = `https://api.elevenlabs.io/v1/text-to-speech/${voiceId}?output_format=mp3_44100_128`;

const res = await fetch(url, {
  method: 'POST',
  headers: {
    'xi-api-key': apiKey,
    'Content-Type': 'application/json',
  },
  body: JSON.stringify({
    text: 'Hello from ElevenLabs.',
    model_id: 'eleven_flash_v2_5',
    voice_settings: {
      stability: 0.5,
      similarity_boost: 0.75,
    },
  }),
});

if (!res.ok) {
  const errText = await res.text();
  throw new Error(`ElevenLabs TTS failed: ${res.status} ${errText}`);
}

const audio = new Uint8Array(await res.arrayBuffer());
await writeFile('speech.mp3', audio);
```

### Create transcript (STT) with a file upload (REST)

```bash
curl -X POST "https://api.elevenlabs.io/v1/speech-to-text/convert" \
  -H "xi-api-key: $ELEVENLABS_API_KEY" \
  -F "model_id=scribe_v2" \
  -F "file=@./audio.wav"
```

## Best Practices

- Prefer streaming responses for TTS when the client supports it, especially in voice-first UI.
- Use `seed` for more consistent outputs across retries, but expect some nondeterminism.
- Use `enable_logging=false` only when you explicitly need reduced retention and your plan supports it.
- Choose `output_format` to match downstream systems (mp3 for most apps, `ulaw` for telephony, pcm for low-level audio pipelines).

## Security & Safety Notes

- Treat audio and transcripts as sensitive user data; avoid sending unnecessary personal data.
- Never persist or log `xi-api-key`; rotate immediately if exposed.
- If you proxy calls through your backend, validate and rate-limit user input to prevent abuse and unexpected cost spikes.

## Related Skills

- `@voice-agents` - Designing low-latency voice agent pipelines end-to-end
- `@audio-transcriber` - Turning recordings into structured notes and summaries
