# PRIVACY POLICY — PilotAI Desktop Application

**Effective Date:** July 20, 2026
**Policy URL:** https://github.com/pilotaisupport/Pilot-AI-Privacy-Policy/blob/main/README.md

---

## §1. DEFINITIONS

**"App"** means PilotAI desktop software for Windows.
**"Device"** means the user's personal computer.
**"Personal Data"** means any information relating to an identified or identifiable natural person.
**"Processing"** means any operation performed on Personal Data.
**"Controller"** means [Developer Name/Entity], [Address].
**"DPO"** means Data Protection Officer, reachable at privacy@pilotai.app.
**"Third Party"** means any natural or legal person, public authority, agency, or body other than the data subject, controller, or processor.
**"Special Category Data"** means biometric data processed for unique identification (Art. 9 GDPR).
**"Always-On Listening"** means continuous microphone capture for wake word detection occurring entirely on Device.

---

## §2. CONTROLLER IDENTITY & CONTACT

| Role | Contact |
|------|---------|
| **Controller** | [Developer Name], [Address], [Country] |
| **DPO** | [DPO Name/Email] |
| **Data Subject Requests** | privacy@pilotai.app |
| **Response Obligation** | 30 days (GDPR Art. 12(3)), 45 days (CCPA §1798.130(a)(2)) |

---

## §3. PERSONAL DATA COLLECTED

### 3.1 Data Provided by the Data Subject

- **Identity Data:** name, alias
- **Authentication Data:** API keys (encrypted at rest with AES-256-GCM), Gmail OAuth tokens
- **Contact Data:** email recipients, WhatsApp contact names
- **Communication Data:** email content accessed via Gmail API

### 3.2 Data Collected Automatically

- **Audio Data:** continuous microphone capture for wake word detection (Device-local, 64ms frames, not retained); speech segments for transcription (Device-local Whisper, discarded after transcription)
- **Voice Biometrics (Special Category):** numerical voiceprint embedding stored at `%APPDATA%\PilotAI\speaker_enrollment\voiceprint.json`; never leaves Device. Collected only upon explicit opt-in consent.
- **Conversation Data:** full chat history (SQLite + JSON, Device-local); transmitted to Third-Party AI provider as prompt context
- **Screen Captures:** OCR of browser tab bar region; UI automation click-target matching; WhatsApp QR. Processed in memory, not retained.
- **Usage Data:** command success counts (Device-local `assistant_stats.json`)
- **Automation Data:** click coordinates (Device-local `click_memory.json`)

### 3.3 Data Transmitted to Third Parties

Per feature invocation only, minimized to necessity:

| Third Party | Data | Purpose | Legal Basis for Transfer |
|-------------|------|---------|--------------------------|
| Groq Inc. (USA) | Transcribed text, conversation history, identity data | AI response generation | Standard Contractual Clauses (SCCs) + necessity for contract performance |
| Google LLC (USA) | Email content, OAuth token, sender/recipient metadata | Email reading/sending via Gmail API | OAuth consent + SCCs |
| DuckDuckGo (USA) | Search query string | Web search result retrieval | Anonymized; no Personal Data retained |
| wttr.in | City name | Weather data | Anonymized; no Personal Data retained |
| ipinfo.io / geocoder | Public IP address (transient, not stored) | Approximate geolocation for weather | Transient, not retained |
| OpenStreetMap | Place name string | Geocoding | Anonymized |

### 3.4 Data NOT Collected

The App does not collect: precise geolocation, browsing history (beyond active tab for browser detection), contact list contents (beyond names for WhatsApp addressing), financial information, health data, political opinions, religious beliefs, or trade union membership.

---

## §4. LEGAL BASES FOR PROCESSING

### 4.1 GDPR Art. 6 — Lawfulness of Processing

| Processing Activity | Legal Basis (Art. 6) | Rationale |
|--------------------|---------------------|-----------|
| Wake word detection | 6(1)(f) Legitimate interests | Core functionality; Device-local only; no data leaves Device |
| Speech transcription | 6(1)(b) Contractual necessity | Essential to provide the voice assistant service |
| AI response generation | 6(1)(b) Contractual necessity | Essential to provide the AI assistant service |
| Conversation memory | 6(1)(f) Legitimate interests | User experience continuity |
| Gmail integration | 6(1)(a) Consent | Optional feature; revocable |
| Web search / weather | 6(1)(b) Contractual necessity | Performed at user's explicit request |
| Usage statistics | 6(1)(f) Legitimate interests | Service improvement; Device-local |

### 4.2 GDPR Art. 9 — Special Category Data

Voice biometric processing requires **explicit consent** (Art. 9(2)(a)):
- Collected only after affirmative opt-in via consent dialog
- Never leaves Device
- Revocable at any time via Settings → Voice → Speaker Verification OFF
- Deletion available via Settings → Privacy → Delete Voiceprint

### 4.3 CCPA §1798.100 — Notice at Collection

Categories of Personal Information collected in the preceding 12 months:
1. Identifiers (name, IP address)
2. Biometric information (voiceprint, if enrolled)
3. Internet/electronic activity (conversation history, search queries)
4. Geolocation data (approximate, from IP)
5. Audio/electronic data (voice recordings for wake samples)
6. Inferences (preferences, routines)

**No sale or sharing** for cross-context behavioral advertising (CCPA §1798.120).

### 4.4 BIPA (740 ILCS 14) — Biometric Information

- **Retention schedule:** voiceprint retained until earlier of: (a) user-initiated deletion, (b) app uninstall, or (c) 3 years from last use
- **Consent:** written release obtained prior to collection
- **Prohibition on sale:** biometric data is not sold, licensed, or otherwise traded
- **No third-party disclosure:** biometric data never leaves Device

---

## §5. PURPOSES OF PROCESSING

Personal Data is processed solely for:

1. **Provision of the voice assistant service** — wake detection, transcription, AI response, feature execution
2. **Personalization** — name, preferences, conversation continuity
3. **Feature functionality** — email (Gmail), messaging (WhatsApp), search, weather, automation
4. **Service improvement** — anonymous local usage statistics

**Prohibited processing:** The App does not sell Personal Data, does not process for behavioral advertising, does not train third-party AI models, and does not engage in automated decision-making producing legal effects concerning the data subject (GDPR Art. 22).

---

## §6. DATA RETENTION

| Data Category | Retention Period | Deletion Mechanism |
|---------------|-----------------|-------------------|
| Wake detection audio | Not retained (processed in 64ms chunks) | Automatic |
| Transcription audio | Discarded after transcription | Automatic |
| Conversation history | Until data subject initiates deletion | Settings → Privacy → Delete Conversations |
| User memories | Until data subject initiates deletion | Settings → Privacy → Delete Memories |
| Voiceprint (biometric) | Until data subject initiates deletion or 3 years from last use | Settings → Privacy → Delete Voiceprint |
| Wake audio samples | Until data subject initiates deletion | Delete `wake_samples/` |
| Gmail OAuth tokens | Until revocation or app uninstall | Settings → Gmail → Disconnect |
| API keys | Until modification or app uninstall | Settings → API Key |
| Send history | Until data subject initiates deletion | Settings → Privacy → Clear History |
| Automation data | Until data subject initiates deletion | Settings → Privacy → Clear Click Memory |
| Usage statistics | Until data subject initiates deletion | Settings → Privacy → Reset Statistics |

Complete data removal: delete `%APPDATA%\PilotAI\` directory.

---

## §7. INTERNATIONAL DATA TRANSFERS (GDPR Art. 44–49)

Data transferred to the United States for AI processing (Groq) and email (Google) is governed by:

1. **Standard Contractual Clauses (SCCs)** — European Commission Decision 2021/914, Module 2 (Controller-to-Processor). Available on request.
2. **EU-US Data Privacy Framework** — for participating entities
3. **No transfer** occurs for Device-local processing (wake detection, transcription, biometric verification, storage)

For transfers where no adequacy decision or appropriate safeguard exists, processing is limited to purposes for which the data subject has given explicit consent (Art. 49(1)(a)) or where processing is necessary for contract performance (Art. 49(1)(b)).

---

## §8. DATA SUBJECT RIGHTS

### 8.1 Right of Access (GDPR Art. 15 / CCPA §1798.100)
Data subject may request confirmation of whether Personal Data is processed and access such data.

### 8.2 Right to Rectification (GDPR Art. 16)
Inaccurate Personal Data shall be corrected without undue delay via Settings.

### 8.3 Right to Erasure (GDPR Art. 17 / CCPA §1798.105)
Data subject may request deletion of Personal Data. The Controller shall comply without undue delay where:
- Data is no longer necessary for the purpose for which it was collected
- Consent is withdrawn and no other legal basis exists
- Data subject objects and no overriding legitimate grounds exist
- Data has been unlawfully processed
- Erasure is required by Union or Member State law

Deletion methods: (a) in-App Settings controls, (b) manual deletion of `%APPDATA%\PilotAI\`, (c) email request to privacy@pilotai.app

### 8.4 Right to Restrict Processing (GDPR Art. 18)
Data subject may obtain restriction where accuracy is contested, processing is unlawful, or data subject has objected.

### 8.5 Right to Data Portability (GDPR Art. 20)
Data subject may request receipt of Personal Data in structured, commonly used, machine-readable format (JSON). Response within 30 days.

### 8.6 Right to Object (GDPR Art. 21)
Data subject may object to processing based on legitimate interests (Art. 6(1)(f)). The Controller shall cease processing unless demonstrating compelling legitimate grounds.

### 8.7 Right to Withdraw Consent (GDPR Art. 7(3))
Where processing is based on consent, data subject may withdraw at any time. Withdrawal does not affect lawfulness of processing before withdrawal.

### 8.8 Right to Opt Out of Sale/Sharing (CCPA §1798.120)
No sale or sharing occurs. No affirmative opt-out required.

### 8.9 Right to Non-Discrimination (CCPA §1798.125)
The Controller shall not discriminate against a data subject for exercising any right.

### 8.10 Right to Lodge Complaint (GDPR Art. 77)
Data subject has the right to lodge a complaint with a supervisory authority, particularly in the Member State of habitual residence.

---

## §9. DATA SECURITY (GDPR Art. 32)

The Controller implements appropriate technical and organizational measures:

| Measure | Implementation |
|---------|---------------|
| Encryption at rest | AES-256-GCM for API keys |
| Access controls | File system permissions restrict OAuth token access |
| Device-local processing | Wake detection, transcription, biometrics processed on Device |
| No cloud storage | All user data stored on Device |
| Input validation | No unvalidated data accepted from external sources |

**Risk acknowledgment:** No security measure provides absolute protection. Data subject uses the App at their own risk. Suspected breaches shall be reported to privacy@pilotai.app immediately.

---

## §10. DATA BREACH NOTIFICATION (GDPR Art. 33–34)

In the event of a Personal Data breach likely to result in a risk to rights and freedoms:
- **Supervisory authority:** notified within 72 hours (Art. 33(1))
- **Data subject:** notified without undue delay (Art. 34(1))
- **Content:** nature of breach, categories of data involved, likely consequences, measures taken or proposed

---

## §11. CHILDREN'S PRIVACY (COPPA — 15 U.S.C. §§6501–6506)

The App is not directed at children under 13. The Controller does not knowingly collect Personal Data from children under 13. An age gate requiring confirmation of age ≥ 13 is presented during onboarding. Upon discovery of collection from a child under 13, the Controller shall delete such data immediately. Reports: privacy@pilotai.app.

---

## §12. CHANGES TO THIS POLICY

Material changes shall be notified via in-app notification or email (if provided). Continued use after the Effective Date constitutes acceptance. Previous versions available upon request.

---

## §13. GOVERNING LAW

This Privacy Policy is governed by the laws of [Jurisdiction], without regard to conflict of laws principles. Disputes arising from this Policy shall be subject to the exclusive jurisdiction of the courts of [Jurisdiction].

---

## §14. COMPLAINT AUTHORITIES BY JURISDICTION

| Jurisdiction | Authority | Contact |
|--------------|-----------|---------|
| EU/EEA | Local Data Protection Authority | Per Member State |
| UK | Information Commissioner's Office (ICO) | https://ico.org.uk |
| California (USA) | California Attorney General | https://oag.ca.gov/privacy |
| Illinois (USA) — BIPA | Illinois Attorney General | https://illinoisattorneygeneral.gov |
| Canada | Office of the Privacy Commissioner (OPC) | https://priv.gc.ca |
| Brazil | ANPD | https://www.gov.br/anpd |
| Australia | OAIC | https://oaic.gov.au |

---

*Document history: v1.0 — July 20, 2026*
