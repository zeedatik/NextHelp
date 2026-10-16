# NextHelp — Privacy Policy

Version 1.1 · Last updated: October 12, 2026

Responsible party: the NextHelp team ("we"). Contact: https://github.com/zeedatik/NextHelp/issues

## 1. The short version

NextHelp does not collect your data. It has no accounts, no analytics, no advertising, no crash reporting and no telemetry. We run no server that receives anything from the app. Everything the app creates stays on your Mac, unless you choose to connect a cloud AI provider (section 5).

## 2. What the app does with your audio

- **Microphone ("You").** With your permission, the app listens to your microphone and converts speech to text on your Mac using Apple's on-device speech recognition (SpeechAnalyzer, or SFSpeechRecognizer in on-device mode on older macOS versions). Audio is not recorded to a file and is not sent to us.
- **System audio ("Them").** With your Screen & System Audio Recording permission, the app captures the audio that plays on your Mac (for example, the other people in a video call) and transcribes it the same way. Only audio is used; the app does not store screen images.
- Apple may download speech and translation language packs to your Mac through macOS. Those downloads are performed by macOS under Apple's terms.

## 3. What is stored on your Mac

| What | Where | Notes |
|---|---|---|
| Transcripts (.txt) | ~/Documents/MeetingAssistant/Transcripciones/ | Saved automatically during a meeting. They can contain what other people said. Delete them whenever you want. |
| Teleprompter scripts | ~/Documents/MeetingAssistant/Guiones/ | Files you create or import. |
| Profile documents and their search index | ~/Library/Application Support/NextHelp/ | Copies of the documents you add to a profile and a local index used to find relevant passages. |
| Settings | macOS preferences (UserDefaults) | Window, language, model and display choices. |
| API keys | macOS Keychain | Only if you add a cloud provider. Never written to plain files. |
| Diagnostic log | ~/Documents/MeetingAssistant/MeetingAssistant-debug.log | Off in the released app by default. If you turn it on for troubleshooting, it can include fragments of transcribed text. Delete it when you finish. |

We cannot see or access any of these files.

## 4. When data leaves your Mac

The app only connects to the network for things you start or choose:

- **Ollama and models.** If you do not already have Ollama, the setup assistant downloads it from the official Ollama project release page on GitHub and checks its signature before running it. Models are downloaded by Ollama from its model library. Ollama then runs on your Mac.
- **A local or remote AI server you configure** (for example LM Studio, or another computer on your network). Text goes to the address you typed.
- **A cloud AI provider you configure** (section 5).
- **macOS.** Apple's own services, such as language-pack downloads, are handled by macOS.

The app contains no code that sends usage data to us.

## 5. Cloud AI providers

If you add a provider such as OpenAI, Anthropic, Groq or OpenRouter, the app sends the text needed for that request (for example, the part of the transcript you ask about, your question, and relevant excerpts of your profile documents) to that provider using your API key. That provider receives and processes it under its own privacy policy, and we do not control what it does with it. The app labels providers that send data off your computer. If you want everything to stay on your Mac, use a local model through Ollama.

## 6. Other people's data

Transcripts can contain personal information and voices of other people. You are responsible for informing them and obtaining consent where the law requires it (see the Terms of Use), and for storing and deleting transcripts responsibly.

## 7. Your rights

Because we do not hold your personal data, there is nothing for us to access, correct or delete on your behalf: you control all the data directly by deleting the files listed above or by removing the app. If you believe we hold personal data about you in some other way, contact us at the address above and we will respond in line with applicable law, including Mexico's data-protection law.

## 8. Children

The app is not directed to children under 13 and we do not knowingly collect information from them (we collect no information from anyone).

## 9. Changes

If this policy changes in a significant way, the app will ask you to review and accept the new version. The current version is always included with the app and in the project repository.
