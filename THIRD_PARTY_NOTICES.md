# Third-party notices

NextHelp is built with Apple frameworks and can work with the following third-party software. NextHelp does not bundle any of it: you download it separately, and each item stays under its own license.

| Component | How NextHelp uses it | License |
|---|---|---|
| Ollama (https://github.com/ollama/ollama) | Optional local runtime for AI models. The setup assistant can download the official release and verify its signature. | MIT |
| AI models you download through Ollama (for example the Qwen3 family and an embedding model such as nomic-embed-text) | Generate answers and embeddings on your Mac. | Each model has its own license, shown on its model card. Check it before using a model commercially. |
| Cloud AI providers you configure (OpenAI, Anthropic, Groq, OpenRouter, Google, others) | Optional. Receive the text you send, using your API key. | Their own terms and privacy policies. |
| Apple frameworks (SwiftUI, AppKit, ScreenCaptureKit, Speech, Translation, NaturalLanguage) | User interface, audio capture, on-device speech recognition and translation. | Apple's SDK and macOS license terms. |

Product and company names mentioned are trademarks of their respective owners. NextHelp is an independent project and is not affiliated with or endorsed by any of them.

Before each release, check that this list still matches what the app uses and that each license text you need to reproduce is included.
