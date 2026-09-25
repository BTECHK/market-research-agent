# Platform Limits: Google read-aloud, iOS long-form TTS, on-device feasibility

*Research date: 2026-09-25. Method: WebSearch only (WebFetch to support.google.com and workspaceupdates.googleblog.com was blocked by the egress proxy, so Google help-page wording is taken from search excerpts). Adversarial pass. Items marked **[UNVERIFIED]** could not be confirmed from a primary source.*

**Bottom line:**
- **Founder's "~10 minute cap": no evidence of it in Google Docs' own "Listen to this tab".** Three things could explain what the founder saw:
  - (a) Google's **Gemini-TTS API documents a hard ~655 s (~10.9 min) output cap per request**, with audio truncated after that. Any tool that makes one naive call hits it.
  - (b) Third-party Chrome/Docs extensions have **daily free-tier caps of 5–20 min**.
  - (c) The "listen" feature is **not available at all** on a free personal Gmail account, and the legacy "Speak selection" only works with a screen reader running.
- **The founder's guess that an iPhone "can't produce two hours of audio" is wrong.** No OS or hardware limit exists. The real limits are:
  - bugs in Apple's built-in reading tools (Speak Screen and similar);
  - the ban on **GPU work in the background on iPhone**, which does limit streaming neural TTS once the screen locks.

---

## 1. Google Docs and Google read-aloud tools

### 1a. "Listen to this tab" (Gemini audio, launched Aug 2025)
| Item | Finding | Source |
|---|---|---|
| Launch | Rapid Release from 2025-08-18; Scheduled Release from 2025-08-25 | https://workspaceupdates.googleblog.com/2025/08/listen-to-documents-using-gemini-google-docs.html |
| Entry points | Tools > Audio > Listen to this tab, or a toolbar button. Authors can use Insert > Audio buttons. The player shows the duration and offers speed and voice choices (Narrator, Educator, Coach and others). | same; https://9to5google.com/2025/08/18/google-docs-audio-gemini/ |
| Eligible plans | Business Standard/Plus, Enterprise Standard/Plus, Gemini Education add-ons, nonprofits, **Google AI Pro and Ultra (individual)** | https://workspaceupdates.googleblog.com/2025/08/listen-to-documents-using-gemini-google-docs.html ; https://support.google.com/docs/answer/16386234 |
| **Free personal Gmail** | **Not available.** The menu item does not appear. | same; https://www.itechguides.com/google-docs-can-read-your-documents-aloud-with-natural-sounding-ai-voices/ |
| Platform | **Desktop web only** ("only available in English and on desktop at this time") | 2025-08 Workspace Updates post; help page excerpt |
| Language | English only at launch. The July 2026 expansion of Gemini in Docs to 11 more languages does **not** name audio, so **[UNVERIFIED]** whether audio gained languages. | https://workspaceupdates.googleblog.com/2026/07/expanded-language-support-for-gemini-in-Google-Docs.html |
| Mobile Docs apps | No evidence that Listen reached the iOS/Android Docs apps. What Google shipped on mobile (2026-09-03) is **Docs Live**, a conversational Gemini voice feature for paid Workspace users, not a linear reader. | https://www.androidheadlines.com/2026/09/google-workspace-live-voice-conversations-gemini-gmail-docs-keep.html ; https://gcn.com/google-rolls-out-gemini-live-voice/21469/ |
| Length cap | **None documented** in any excerpt. **[UNVERIFIED]** either way. The help page could not be fetched. | — |
| Complaints | Few first-hand complaints were found. Third-party troubleshooting pages mention "usage limits" and connectivity as causes of playback stopping, which is vague. Reviewers note it has no word highlighting or reading aids. | https://castreader.com/google-docs-read-aloud-not-working ; https://www.mote.com/learn/landing/text-to-speech-google-docs |

### 1b. Audio summaries (Feb 2026)
- **Rollout:** began 2026-02-12, with up to 15 days or more to reach all accounts. Entry point is Tools > Audio > Listen to document summary. Summaries are "typically under a few minutes" (about 3 min), with speed from 0.5x to 2x and voice personas.
- **Plans:** AI Pro and Ultra, AI Pro for Education, AI Ultra for Business, Business and Enterprise Standard/Plus. **Free users are excluded.**
- **Platform:** web.
- **Implication:** this is a *summary*, not a full read, so it does not compete with a 2-hour full listen.
- **Sources:** https://workspaceupdates.googleblog.com/2026/02/listen-to-audio-summaries-in-google-docs.html ; https://9to5google.com/2026/02/12/google-docs-audio-summaries/ ; https://www.androidpolice.com/google-docs-gets-a-big-gemini-boost-focused-on-accessibility/

### 1c. Older and other Google options
- **Docs "Speak selection":** turn on Tools > Accessibility > screen reader support, then Accessibility > Speak > Speak selection. This **sends the text to a running screen reader** (ChromeVox, NVDA or JAWS). Without one, "nothing happens", and users report it failing. **This is the most likely cause of the founder's "read-aloud was not working."**
  - https://support.google.com/docs/answer/6282736 ; https://www.edugeek.net/forums/topic/204945-google-docs-text-to-speech-not-working/
- **Chrome Reading mode "Read aloud":** on stable Chrome, Reading mode **does not detect text in Google Docs**. Docs integration has sat behind flags since 2024. It also fails on PDFs or stops after the first page.
  - https://www.androidpolice.com/google-chrome-reading-mode-improvements-docs-integration/ ; https://chromestory.com/2024/05/make-chrome-read-articles-aloud/ ; https://moondeskmedia.com/blog/chrome-read-pages-aloud
- **Chrome Web Speech API bug:** Google network voices **stop after about 15 seconds** per utterance. This is a long-standing Chromium bug and affects extensions or sites that do not chunk text.
  - https://bugs.chromium.org/p/chromium/issues/detail?id=679437 ; https://issues.chromium.org/issues/41346274 ; https://github.com/HadrienGardeur/read-aloud-best-practices/issues/3
- **ChromeOS Select-to-speak:** Chromebook only, and reads selected text. It gives no documented length cap. Some reviewers report long selections stopping, which is weak evidence.
  - https://support.google.com/chromebook/answer/9032490 ; https://readaloudreader.com/blog/google-docs-read-aloud/
- **Google Docs iOS app:** has **no built-in read aloud**. Users rely on iOS Speak Selection, Speak Screen or VoiceOver.
  - https://spellapp.com/resources/how-to-make-google-docs-read-to-you-on-iphone ; https://murf.ai/blog/text-to-speech-google-docs

### 1d. Evidence for a "~10 minute" cap
- **Gemini-TTS (Cloud):** the text field is limited to 4,000 bytes, and "**output audio can at most be around 655 seconds… audio will be truncated**." That is about 10.9 min.
  - https://docs.cloud.google.com/text-to-speech/docs/gemini-tts
- **Gemini API TTS:** a 32k-token context per session, shared between instructions and script. It streams only on 3.1-flash-tts-preview.
  - https://ai.google.dev/gemini-api/docs/speech-generation
- **Extension free tiers:**
  - NaturalReader: premium voices 20 min/day, "plus" voices 5 min/day.
  - Read Aloud: 20 min/day free.
  - Speechify: daily limits.
  - https://chromewebstore.google.com/detail/naturalreader-ai-text-to/kohfgcgbkjodfcfkcackpagifgbcmimk ; https://readaloud.net/en/blog/text-to-speech-chrome-extension
- **Verdict:**
  - The ~10-min figure matches the Gemini-TTS per-request cap and extension quotas.
  - **Nothing shows Docs' Listen itself stops at 10 min.** Google presumably chunks the text internally, so treat the founder's cap as **[UNVERIFIED anecdote]**.
  - For our own build: **if we use Gemini-TTS, we must chunk at ≤4 KB of text / ≤10 min per call.**

---

## 2. iOS built-in reading tools and developer limits

**User-facing tools (Speak Screen, Spoken Content, Safari Listen to Page, Accessibility Reader).** No documented length or character cap exists. The failures are reported bugs:
- Speak Screen stops after one page or will not turn pages (iOS 26): https://discussions.apple.com/thread/256209564 ; https://discussions.apple.com/thread/256137942
- "Insanely unreliable", stops mid-text: https://discussions.apple.com/thread/256044481
- Safari Listen to Page skips paragraphs and stops (iOS 17.3): https://discussions.apple.com/thread/255489297 ; https://discussions.apple.com/thread/255894417
- **Listen to Page stops as soon as the phone goes inactive when "Require Face ID to Unlock Private Browsing" is on.** A suggested workaround is deleting neural voices.
- Apple itself (WWDC26 session 219) tells developers to adopt UITextInput and page-turn APIs so Speak Screen and Accessibility Reader can move through long content. This implicitly confirms that apps with non-standard text views break it.
  - https://developer.apple.com/videos/play/wwdc2026/219/

**Can iOS produce 2 hours of audio?** Yes. No OS or hardware limit exists. Audiobook and podcast apps routinely play files of 10 hours or more with the background `audio` mode.
- **Storage math:**
  - 2 h at 64 kbps AAC = 64,000 × 7,200 / 8 = **57.6 MB** (correct).
  - Uncompressed Kokoro output (24 kHz, 16-bit mono) is **about 346 MB for 2 h**, so encode to AAC.

**AVSpeechSynthesizer (Apple's developer speech engine).**
- **Background speech works** with the `audio` UIBackgroundMode, an active playback session, and a synthesizer held as a property. A local variable gets deallocated and speech stops.
  - https://developer.apple.com/forums/thread/27097 ; https://developer.apple.com/forums/thread/23160 ; https://developer.apple.com/forums/thread/75826
- **Long-text bugs:**
  - An iOS 17 enhanced voice ("Daniel Enhanced") fires didFinish prematurely at the same spot every time. The workaround is to **split text into separate utterances** or **write to a file and play that**.
    - https://developer.apple.com/forums/thread/737685 ; https://developer.apple.com/forums/thread/738048
  - "Why has AVSpeechSynthesizer quit speaking?": https://developer.apple.com/forums/thread/746735
- **`write(_:toBufferCallback:)`:** receives PCM buffers that you append to an AVAudioFile. It had bugs: error -66686 on iOS 16, and choppy output on iOS 17.
  - https://developer.apple.com/forums/thread/122690 ; https://developer.apple.com/forums/thread/716424 ; https://developer.apple.com/documentation/avfaudio/avspeechsynthesizer/buffercallback
- **Voice limits:**
  - **Siri voices are not available to third-party apps.**
  - Premium and Enhanced voices must be **downloaded by the user in Settings**.
  - iOS 26 has a regression that ignores user-selected voices.
  - https://speechcentral.net/2026/08/08/why-cant-third-party-apps-use-siri-voices-on-iphone-ipad-and-mac/ ; https://developer.apple.com/documentation/avfaudio/avspeechsynthesisvoicequality/premium ; https://developer.apple.com/forums/thread/804648
- **Standard workarounds:** chunk by sentence or paragraph; queue utterances; persist the character offset so playback can resume; or pre-render to a file.

---

## 3. A fully on-device ("data never leaves the phone") architecture

**Text extraction**
- **PDFKit:** extracts text with no structure.
- **Vision `RecognizeDocumentsRequest` (iOS 26):** returns paragraphs, tables and lists in 26 languages. Developers report paragraph over-splitting and vertical-text quirks.
  - https://developer.apple.com/videos/play/wwdc2025/272/ ; https://github.com/vlumi/yomidori/pull/91
- **DOCX, EPUB and HTML:** these are zip/XML formats that are parseable locally. Local TTS and Speech Central already import DOCX, EPUB and PDF offline.

**Neural TTS on the phone (Kokoro-82M)**
- **Speed by device:**
  - iPhone 13 Pro with MLX Swift: **~3.3× real time** after warm-up. https://github.com/mlalma/kokoro-ios
  - Core ML on the Neural Engine (ANE): **~17× on iPhone 16 Pro, ~4–4.5× on A17 Pro (iPhone 15 Pro)**. The iPhone ANE compiler rejects the full-ANE plan. https://github.com/Jon-Schneider/kokoro-coreml-ane
- **Model size:**
  - about 80 MB (INT8 Core ML);
  - ONNX int8 88 MB, fp32 310 MB;
  - Sandbook bundles about 312 MB.
  - https://huggingface.co/FluidInference/kokoro-82m-coreml ; https://github.com/thewh1teagle/kokoro-onnx/releases ; https://sandbook.app/kokoro-tts
- **Battery:** only a single claim was found, that the ANE port drains about 4× less than GPU. **[UNVERIFIED]**, and there are no mAh-per-hour figures.
- **iPhone 12 (A14):** no benchmark found **[UNVERIFIED]**. The A14 ANE rejects the full-ANE plan, so expect slower speeds.
- **Licensing trap:** Kokoro is Apache-2.0, but **espeak-ng and phonemizer are GPLv3**. Use the **Misaki** grapheme-to-phoneme converter (G2P) for English. GPL on the App Store is a legal risk.
  - https://github.com/hexgrad/kokoro/issues/247 ; https://news.ycombinator.com/item?id=46642602
- **CRITICAL constraint: the GPU is unavailable in the background on iPhone.**
  - Metal work submitted from the background gets "Insufficient Permission" and may kill the process.
  - `BGContinuedProcessingTask` GPU access reports as unsupported on iPhone 15 Pro and 16 Pro (iPad only).
  - https://developer.apple.com/forums/thread/816774 ; https://developer.apple.com/documentation/metal/preparing-your-metal-app-to-run-in-the-background
- **Field confirmation:** Sandbook, which uses MLX, says "**real-time reading pauses when the screen locks**; prepare the chapter first to listen with the screen off."
  - https://apps.apple.com/gb/app/sandbook-natural-voice-reader/id6745732885
- **Counter-example:** Local TTS advertises background and lock-screen playback. The mechanism is unknown, perhaps CPU/ANE or pre-rendering.
  - https://apps.apple.com/us/app/local-tts-ai-voice-reader/id6779664222
- Whether Neural Engine inference is permitted in the background audio mode is **[UNVERIFIED]**. It must be prototyped.

**Apple Foundation Models (on-device language model)**
- The context window is **4,096 tokens** (input plus output), unchanged in iOS 27. iOS 26.4 added `contextSize` and `tokenCount`.
  - https://developer.apple.com/forums/thread/806542 ; https://zats.io/blog/making-the-most-of-apple-foundation-models-context-window/ ; https://chatforest.com/builders-log/apple-foundation-models-ios-27-on-device-llm-api-builder-guide/
- It is fine for cleaning up text chunk by chunk (about 2–3 pages per call), but not for summarizing a whole document.
- WWDC26 added a free **Private Cloud Compute** model (32K context) for developers under 2M downloads. It is off-device, so it breaks a strict "never leaves the phone" claim.
  - https://developer.apple.com/videos/play/wwdc2026/319/ ; https://dev.to/arshtechpro/wwdc-2026-apple-just-opened-the-foundation-models-framework-to-any-llm-provider-5ejn

**Competitors already claiming on-device or offline privacy**

| App | Claim | Source |
|---|---|---|
| Voice Dream | "All voices are offline to protect your privacy"; library stays on device or in iCloud | https://www.voicedream.com/reader/reader-feature-list/ |
| Speech Central | Offline voices by default; no external servers; no data collection | https://speechcentral.net/2023/08/06/navigating-privacy-in-text-to-speech-apps-on-ios-and-android/ |
| Speechify | Launched "On-Device iOS Voices", 100% local inference (about Dec 2025). Standard processing is cloud. | https://speechify.com/news/speechify-launches-on-device-ios-ai-voices-for-offline-reading/ |
| Local TTS, Sandbook, Voice Forge, Koro Voices, Simple Voice Reader | Kokoro 100% offline, no account | https://apps.apple.com/us/app/local-tts-ai-voice-reader/id6779664222 ; https://apps.apple.com/us/app/-/id6743238823 ; https://apps.apple.com/us/app/simple-voice-reader/id6787165967 |

**→ "Private and on-device with Kokoro" is already crowded, not a unique claim.**

**Google Docs without a server**
- **Share Sheet route:**
  - The Docs iOS app offers Share & export > **Send a copy** as PDF or .docx, which opens the iOS Share Sheet. This is zero OAuth and fully local.
  - https://www.techrepublic.com/article/how-to-export-a-google-doc-from-your-iphone/ ; https://www.idownloadblog.com/2022/07/29/how-to-save-google-docs-as-pdf/
- **Direct API route:**
  - GoogleSignIn plus the Drive REST API, calling `files.export` from the device. Use the `drive.file` scope.
  - The **Google Picker is a JavaScript/web API**, so native iOS needs a web view or a custom picker (with `drive.file`, a custom picker only sees files the app created or was granted).
  - https://developers.google.com/workspace/drive/api/guides/api-specific-auth ; https://developers.google.com/picker
- **Files app route:** Google Docs appear in the Files app only as **.gdoc shortcut stubs**, not content.
  - https://file-extensions.com/docs/gdoc

**Privacy and legal benefits**
- **App Store privacy label:** Apple says "data processed only on device is not 'collected'". An app that processes documents only on the device can claim **Data Not Collected**, provided analytics, crash reporting and account data also stay off.
  - https://developer.apple.com/app-store/app-privacy-details/
- **GDPR:** under the EDPB's controller/processor test, a developer that never receives the content is plausibly neither controller nor processor *for document content*. **This is a legal interpretation; get counsel.**
  - https://www.edpb.europa.eu/our-work-tools/our-documents/guidelines/guidelines-072020-concepts-controller-and-processor-gdpr_en
- **Attorneys:** ABA Formal Opinion 512 (2024-07-29) requires understanding how generative-AI tools handle client data, and informed consent for self-learning tools. On-device processing sidesteps most of this. Apple Guideline 5.1.2(i) third-party AI disclosure would not apply if nothing is sent.
  - https://www.americanbar.org/groups/business_law/resources/business-law-today/2024-october/aba-ethics-opinion-generative-ai-offers-useful-framework/

---

## 4. Rendering-time math

**Time to fully render 2 h (120 min) of audio**

| Device and path | Speed (× real time) | Full render of 2 h |
|---|---|---|
| iPhone 13 Pro, MLX | 3.3× | **~36 min** (the founder's "~40 min" is correct) |
| iPhone 15 Pro, Core ML | 4–4.5× | ~27–30 min |
| iPhone 16 Pro, Core ML on the Neural Engine | 17× | **~7 min** |

**Can streaming start in seconds?** Yes in principle. Kokoro is non-autoregressive, so it synthesizes one sentence in a single pass. At 3.3×, a 5-second sentence renders in about 1.5 s, plus model load and warm-up. **No published iPhone time-to-first-audio figure was found [UNVERIFIED]**. Desktop sentence-streaming reaches about 0.5 s.
- https://github.com/mjg1911/TTS/issues/18 ; https://www.forasoft.com/learn/ai-for-video-engineering/articles-ai/streaming-tts-kokoro-elevenlabs-turbo-openai-tts

**Caveat:** streaming only works **while the app is in the foreground** if it uses the GPU (MLX). For locked-screen listening, one of these is needed:
- (a) pre-render ahead of playback while in the foreground;
- (b) run on CPU or the Neural Engine via Core ML in the background (**unverified that this is allowed**);
- (c) fall back to AVSpeechSynthesizer when locked.

**Note:** A foreground render means the app must keep the screen on (idleTimerDisabled). A 36-minute render with the screen on costs battery and heat.
