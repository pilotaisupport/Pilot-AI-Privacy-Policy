# PilotAI — Privacy Policy

**PilotAI** only accesses device data when you enable a feature or grant a permission. Microphone, screen, and file access are optional. Conversations stay on your device or go to the AI gateway you choose. No data goes to a central PilotAI cloud.

**No ads or analytics.** No ad, analytics, or crash-reporting SDKs.

**Permission-based.** Microphone, screen capture, file system, and notification access are optional.

**Your AI provider.** The app sends transcribed text to the AI provider you configure (Groq, Ollama, or another compatible service).

**Optional features.** Gmail, WhatsApp, web search, weather, location, and voice biometrics are all optional. You control each feature.

**Effective date:** July 20, 2026 · **Applies to:** Windows desktop app

**Support email:** pilotaifeedback@gmail.com

---

## 1. Scope

This policy applies to the PilotAI desktop application for Windows. It does not cover the privacy practices of your AI provider (e.g., Groq, Ollama), Gmail, WhatsApp, DuckDuckGo, or any other third-party service you choose to connect to through PilotAI.

---

## 2. Information the app can access

The app can access the following categories of data, depending on which features you enable:

**Connection and setup data** — AI provider API key, gateway host/port, model selection, wake-word settings, feature toggles, and pairing state.

**Microphone audio** — if you enable wake-word detection or voice input. Wake-word detection runs locally (64ms frames, not retained). Voice input is transcribed locally via Whisper and the resulting text is sent to your configured AI provider.

**Voice biometrics** — if you enable speaker verification. A numerical voiceprint is stored locally and never leaves your device. Requires explicit opt-in.

**Screen content** — if you enable OCR-based browser tab detection or UI automation. Screenshots are processed in memory and not retained.

**Conversation history** — stored locally. Sent to your AI provider as context for response generation.

**Email data** — if you connect Gmail. The app can read email metadata, send emails, and modify messages (mark read, archive, delete). Controlled by Gmail OAuth scopes.

**WhatsApp contacts and messages** — if you enable WhatsApp integration. Processed through a local browser automation session.

**Search queries and location** — if you use web search or weather features. Sent to DuckDuckGo, wttr.in, or geocoding services only at your request.

**File system** — the app reads and writes configuration, conversation history, and voice samples to app-private storage. With your instruction, it can save files to your Desktop or other locations.

**Clipboard** — the app writes to the system clipboard only when you click "copy" on an AI message.

---

## 3. Where data goes

**Your AI provider.** Transcribed text and conversation context are sent to the AI provider you configure (Groq, Ollama, or another compatible service).

**Gmail.** If you connect Gmail, email data is sent to Google's Gmail API servers.

**WhatsApp.** WhatsApp messages are sent through WhatsApp Web via a local browser session.

**Web search and weather.** Search queries go to DuckDuckGo. Location queries go to geocoding services and wttr.in. All at your explicit request.

**What stays local.** Wake-word detection, speech transcription (Whisper), speaker verification, voice biometrics, conversation history storage, and all app settings.

We do not operate a central cloud. There is no PilotAI server that receives your data.

---

## 4. What we do not do

- We do not sell your personal data.
- We do not include ad SDKs.
- We do not include analytics or crash-reporting SDKs.
- We do not train third-party AI models on your data.
- We do not share data for cross-context behavioral advertising.
- We do not collect precise geolocation, browsing history beyond the active browser tab, contact lists beyond names for WhatsApp addressing, financial information, health data, or sensitive categories of personal data.

---

## 5. Local storage and security

The app stores connection secrets (API keys) locally using AES-256-GCM encryption. Gmail OAuth tokens are stored with restricted file-system permissions. Conversation history, memories, voiceprints, and settings are stored in app-private storage (`%APPDATA%\PilotAI\` and app data directories).

Temporary files (e.g., TTS audio output) are written to app cache and discarded after use.

---

## 6. Retention

| Data | Retained until |
|------|---------------|
| Wake-word audio | Not retained (64ms chunks, processed in real time) |
| Transcription audio | Discarded after transcription completes |
| Conversation history | You delete it (Settings → Privacy → Delete Conversations) |
| User memories | You delete them (Settings → Privacy → Delete Memories) |
| Voiceprint | You delete it or 3 years after last use (Settings → Privacy → Delete Voiceprint) |
| Wake audio samples | You delete them (delete `wake_samples/`) |
| Gmail OAuth tokens | You revoke them or uninstall the app |
| API key | You change it or uninstall the app |

Complete data removal: delete `%APPDATA%\PilotAI\`.

---

## 7. Your choices

- **Permissions.** You can grant or revoke microphone, file system, and other permissions at any time.
- **Features.** You can disable wake word, voice biometrics, Gmail, WhatsApp, screen capture, web search, and other features in Settings.
- **AI provider.** You can switch between Groq (cloud) and Ollama (local) at any time. Local mode sends no data off your device.
- **Data deletion.** You can delete conversations, memories, voiceprints, and history from Settings → Privacy.
- **Uninstall.** Removing the app deletes all locally stored data.

---

## 8. Changes and contact

We may update this policy as the app changes. The updated version will be posted here with a new effective date.

For privacy or security questions: **pilotaifeedback@gmail.com**.

**Instagram**
@pilotaifeedback

Data subject requests (access, deletion, portability): **pilotaifeedback@gmail.com** — we respond within 30 days.
