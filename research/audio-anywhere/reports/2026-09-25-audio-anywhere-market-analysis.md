# Audio Anywhere: Is There a Viable Market for an AI Long-Document Reader on iOS?

**Research Date:** 2026-09-25
**Prepared for:** Founder, Audio Anywhere (working name)
**Status:** Complete. This is a desk study and has not been field-validated. See Research Limitations.
**Stance:** Adversarial, as the founder asked ("I'm not looking for you to agree").

---

## Executive Summary

### Verdict: Do not build MVP1 as specified. Spend 2–4 weeks and under $1.5K testing one narrow wedge, then decide.

The product as briefed is "Google Docs + PDF + progress saving + audiobook-grade voices, iOS consumer subscription, later read-anything-anywhere." That version enters a market with a profitable leader, a quality leader with an $11B parent, a crowded mid-tier, and two platform owners giving away good-enough versions. Every headline feature of MVP1 is already on a competitor's homepage. [Audeus](https://www.audeus.com/) markets "Read Aloud PDFs, Gdocs & more" and says it "automatically saves your place." MVP2 ("read anything from anywhere on your phone") cannot be built on iOS, because the sandbox blocks it ([Apple Platform Security](https://support.apple.com/guide/security/security-of-runtime-process-sec15bfe098e/web)). Apple has also already shipped a free system-wide version, the [iOS 26 Accessibility Reader](https://support.apple.com/guide/iphone/read-listen-text-apps-accessibility-reader-iph406a46ab8/ios).

One wedge survives the evidence, and it is narrow. It is a **"briefing-grade" reader for professionals who must hear long, structured, often confidential documents verbatim.** It would compete on three things:
- **document-structure fidelity:** strip headers, footers and page numbers, handle footnotes, get reading order right, narrate tables;
- **guaranteed long-session reliability** with exact resume;
- **on-device voices**, so client documents never leave the phone.

This wedge is a gap in incumbents' execution, not a moat. It also has **zero first-person evidence** from the professional segment it targets. Even if it works, the realistic outcome is a good indie business (about **$0.35–0.7M ARR by year 3**), not a venture-scale "Wispr Flow for listening."

### The founder's five questions, answered

| # | Question | Short answer | Confidence |
|---|---|---|---|
| 1 | **Do other people care about this problem, or only me?** | **Others care, but not the people you think.** Long-document failure in built-in TTS is one of the most persistent complaints on Apple's forums: 15+ threads from iOS 8 to iOS 26, such as ["iOS 18: 'Speak Screen' is largely broken"](https://discussions.apple.com/thread/256013629) and ["No speakable content could be found on the screen"](https://discussions.apple.com/thread/254777900). Paying users of [Speechify](https://justuseapp.com/en/app/1209815023/speechify-audio-text-reader/problems) and [ElevenReader](https://justuseapp.com/en/app/6479373050/elevenlabs-reader-ai-audio/reviews) report the same "loses its place" failure. But the complainers are mostly **accessibility users of free built-ins**. They are the least likely to pay a new subscription. We found **no first-person quote** from a lawyer, consultant or analyst. Google only partly fixed your own Google Docs complaint. [Gemini "Listen to this tab"](https://workspaceupdates.googleblog.com/2025/08/listen-to-documents-using-gemini-google-docs.html) (Aug 2025) works **only for paid Workspace and Google AI Pro/Ultra users, on desktop web, in English**. Free Gmail accounts and the Docs iOS app get no full read-aloud (see §10.6). | Pain: High. Paying professional pain: Unknown |
| 2 | **What exists today? What is the App Store competition?** | **Saturated.** [Speechify](https://speechify.com/) claims 50–60M users and is profitable, earning about $2M/month on US iOS alone ([Sensor Tower](https://app.sensortower.com/overview/1209815023?country=US)). [ElevenReader](https://elevenreader.io/blog/best-pricing-more-value) has the best voices, 10 free hours a month and $99/yr, backed by an [$11B parent](https://techcrunch.com/2026/02/04/elevenlabs-raises-500m-from-sequioia-at-a-11-billion-valuation/). Audeus, Peech, NaturalReader/Voice Dream, Listening.com and Speech Central ($9.99 one-time) fill the middle. [Dozens of template apps](https://apps.apple.com/us/app/ai-reader-read-aloud-pdf-book/id6754524209) bid on the keywords. Resume-position is **table stakes**. See the comparison table in section 4. | High |
| 3 | **How big is the market, and what is the realistic revenue?** | Ignore the $4–5B "TTS market" reports ([GM Insights](https://www.gminsights.com/industry-analysis/text-to-speech-market) and similar); they bundle IVR, automotive and enterprise APIs. Bottom-up **US consumer read-aloud spend is about $45–70M/yr**, roughly two-thirds to three-quarters of it Speechify. The **briefing-reader SAM is about $5–16M/yr**. A solo or small team realistically reaches **$53–106K in bookings net of Apple's 15% in year 1** and **$0.35–0.7M ARR in year 3**, and only if annual renewal beats the productivity median. | Low–Medium (assumption-heavy) |
| 4 | **Pricing, unit economics and what the founder earns ("compensation")** | Price at **$8.99/mo or $69/yr**, under ElevenReader ($99) and Speechify ($139). **Never sell "unlimited premium cloud voice":** at $9.99/mo, a 20 h/mo user on ElevenLabs v3 voices runs a **−1,113% gross margin**. On-device voices (Kokoro-82M) give about 100% gross margin. The binding constraint is not COGS. It is **LTV ≈ $32 per payer** (North America median, [RevenueCat](https://www.revenuecat.com/state-of-subscription-apps)) and **~23% annual renewal for productivity apps**. Year 1 will not replace a salary. By year 3 the business could pay one to three people. | Medium |
| 5 | **Is it viable, and where is a focused niche?** | **Viable only as a narrow wedge, and only after validation.** The niche is *structured, long, confidential work documents heard verbatim*: legal filings, policy briefs, investment memos, academic papers. Lead with messy PDFs, not Google Docs. Stay on-device by default. Drop MVP2 on iOS. The kill test is a concierge "cleaned audio via private podcast feed" pilot that must reach ≥40% "very disappointed" and ≥25% paid conversion. | Medium on the direction, Low on the wedge's size |

### Hypothesis verdicts

| Hypothesis | Verdict | One-line rationale |
|---|---|---|
| **H1:** Built-in and existing TTS readers handle long documents badly, and people complain | **Partial** | Strongly true for iOS built-ins and true for Speechify and ElevenReader. But Google fixed Docs for paid plans on desktop web (Aug 2025; free and mobile users still lack it, §10.6), Apple shipped Accessibility Reader (iOS 26), and complainers are mostly accessibility users, not professionals. |
| **H2:** No strong AI audiobook-style document reader dominates the App Store | **Rejected** | Speechify dominates distribution and ElevenReader dominates quality. Both are funded, and both offer resume, sync and cloud import. |
| **H3:** A niche of long docs + progress saving + Google Docs/PDF import can be owned | **Rejected as stated** (a narrowed version is unproven) | All three features are claimed by at least three competitors, and resume is table stakes. What remains open is *structure fidelity + reliability + on-device privacy for professional documents*. That niche is untested. |
| **H4:** People will pay a subscription for this | **Partial** | The category clearly monetizes (Speechify, NaturalReader, Readwise at $80–160/yr). But an entrant faces ~2.6% install-to-paid, ~23% renewal, $32 LTV, an ElevenReader free tier covering about eight 20-page documents a month, and an accessibility segment hostile to subscriptions. |

### Top three recommendations

1. **Freeze the build. Run seven validation experiments (section 9) over 2–4 weeks for under $1.5K.** The gating ones are JTBD interviews with 15–20 professionals, and a concierge MVP that delivers cleaned audio as a private podcast feed and asks for real payment.
2. **If the experiments pass, reposition from "text-to-speech app" to "private briefing reader."** The MVP is PDF and Share Sheet import, structure cleanup, pre-rendered on-device audio, and exact resume. Google Docs comes in via `drive.file` + Picker as a secondary input. Drop "read anything," text-message reading, OCR-first flows and voice cloning.
3. **Decide the ambition now.** If you need venture scale, the consumer app is not it. Only a firm or enterprise channel (on-device confidentiality for law and consulting) or an education/disability-services channel could get there, and neither has any evidence yet.

### Critical considerations

- **The biggest risk is an "elephant" nobody has tested:** professionals may want **summaries, not verbatim audio**. [NotebookLM Audio Overviews](https://www.macrumors.com/2025/05/20/google-releases-notebooklm-app-for-ios-and-android/) and [Google Docs audio summaries](https://workspaceupdates.googleblog.com/2026/02/listen-to-audio-summaries-in-google-docs.html) are free or bundled and growing.
- **The platform window is about 6–12 months.** iOS 27 brings a Gemini-derived model and Siri "read a document" ([MacRumors](https://www.macrumors.com/roundup/ios-27/)). Google Docs voice is moving to mobile ([Android Headlines](https://www.androidheadlines.com/2026/09/google-workspace-live-voice-conversations-gemini-gmail-docs-keep.html)).
- **The Wispr Flow analogy breaks on frequency.** Dictation is used dozens of times a day. Long-document listening is episodic, perhaps 1–3 times a week. That means weaker habit and higher churn.
- **"Why you" is unanswered.** A personal pain point is not distribution. Speechify's founder had the same pain and a nine-year head start ([20VC interview](https://speechify.com/blog/cliff-weitzman-speechify-20vc-lessons/)).

---

## 1. Research Methodology

### Approach
Six desk-research streams ran in parallel: Competitor Profiler, Voice Miner, Community Mapper, Pricing Intel, Trend Detector and Local/Platform Context. A PM strategy pass followed, applying JTBD, Four Forces, Dunford positioning, Porter's Five Forces, 7 Powers, a pre-mortem, PMF signals and a bottom-up TAM/SAM/SOM. This report cross-references those streams, resolves or flags conflicts, and adds the evidence synthesis. Every hypothesis was tested adversarially: we looked for disconfirming evidence first.

### Sources analyzed

| Source type | Volume | Examples |
|---|---|---|
| User complaints and forums | 58 quote/signal items from 12 source types (~14 verbatim, ~32 paraphrased, ~12 thread titles) | Apple Community, AppleVis, Zotero, Adobe Community, Trustpilot, BBB, mjtsai.com, mosen.org |
| Competitor pages, reviews and trackers | 11 direct competitors, 4 read-later apps, 9 platform substitutes, ~10 template apps | Vendor pricing pages, justuseapp, speedreadinglounge, castreader, texttolab |
| Pricing and cost data | 14 consumer price points, 17 TTS API price points | Vendor pricing pages, RevenueCat 2026 |
| Market and trend data | Funding, M&A, audiobook and prevalence statistics | TechCrunch, Edison Research, APA, CDC |
| Platform and regulatory | iOS APIs, App Store guidelines, Google OAuth, accessibility procurement | Apple developer docs, Google developer docs, Federal Register |

### Research limitations (read before relying on any number)

1. **Reddit, App Store pages, Google Trends and many vendor pages were blocked in this environment.** Egress blocked direct fetches of reddit.com, news.ycombinator.com, apps.apple.com, discussions.apple.com, applevis.com, trustpilot.com, trends.google.com, elevenreader.io, elevenlabs.io, speechify.com, revenuecat.com and others. **Most evidence comes from search-result snippets, not full pages.** Quotes marked [P] in the raw file are paraphrases of snippets and must be rechecked at the URL before they are used externally.
2. **Reddit was not mined at all** (r/dyslexia, r/ADHD, r/speechify, r/lawschool, r/LawFirm). This is the largest gap in voice-of-customer evidence.
3. **App Store ratings and review counts are mostly unverified.** Where given, they come from third-party aggregators such as appbrain.
4. **Google Trends was not accessed**, so every search-interest direction in this report is inferred and marked unverified.
5. **The shared 200-search budget ran out** before several items were covered: Wondercraft, Podcastle, Matter/Instapaper TTS depth, Microsoft Word/Edge on iOS, Speechify's and NaturalReader's App Store rating counts, and a wide App Store keyword sweep. These are open gaps, not evidence that nothing exists.
6. **There is no first-person evidence from the professional segment**, which is the segment this report ends up recommending. Every conclusion about professionals is a hypothesis.
7. **Revenue figures for private companies are third-party estimates that disagree** (see the data conflicts below).

### Data conflicts flagged

| Data point | Conflict | How this report treats it |
|---|---|---|
| Speechify revenue | $17.6M ARR per [Latka](https://getlatka.com/companies/speechify.com), vs ~$2M in one month on US iOS per a [Sensor Tower](https://app.sensortower.com/overview/1209815023?country=US) snippet (~$24M/yr annualized, US iOS only) | Speechify is plausibly a $30–100M+ business. The Trend Detector recommends treating it as "unknown." The TAM uses Sensor Tower and is therefore Low–Medium confidence. |
| Speechify plans | "Annual only, no monthly plan" ([fahimai](https://www.fahimai.com/speechify)) vs "$139/yr or $29/mo" ([costbench](https://costbench.com/software/ai-voice-tools/speechify/)) | We cite $139/yr as the anchor. Several 2026 pricing trackers (costbench, texttolab, fluxnote) list $29/mo, so a monthly plan most likely exists. |
| ElevenReader Ultra | "Unlimited" at $99/yr ([ElevenReader blog](https://elevenreader.io/blog/best-pricing-more-value)) vs "$11/mo or $99/yr for 20 hours" after the May 2026 audiobook launch ([Publishers Weekly](https://www.publishersweekly.com/pw/by-topic/industry-news/publisher-news/article/100500-elevenlabs-adds-200k-audiobooks-to-stream-offers-premium-tier.html)) | The 20-hour figure may apply to audiobook listening. Either way, $99/yr is the price anchor. |
| ElevenReader desktop | "No desktop app" is the "loudest… complaint" ([speedreadinglounge](https://www.speedreadinglounge.com/elevenreader-review)) vs an existing [Chrome extension](https://elevenreader.io/text-to-speech-chrome-extension) and web app | Treated as: web and extension yes, native desktop no. |
| Listening.com price | ~$59/yr ([listening.com/pricing](https://www.listening.com/pricing), per Competitor Profiler) vs ~$99/yr (per Pricing Intel, same URL) | Shown as $59–99. |
| Audioread price | "Pro from $4.99/mo" vs "$9.99/mo or $69.99/yr" ([audioread.com/pricing](https://audioread.com/pricing)) | Shown as $4.99–9.99/mo. |
| Voice Dream price | $59.99/yr vs reports of $79.99/yr on iOS ([Perkins](https://www.perkins.org/resource/voice-dream-reader-subscription-controversy/)) | Shown as $60–80. |
| Speechify review counts | Trustpilot ~6,600 vs ~5,600 reviews; "500K+" vs "1.1 million" five-star ratings claimed | Directionally consistent; exact counts not relied on. |
| US web-checkout fee | 0% after the Apr 2025 *Epic* injunction vs a Ninth Circuit ruling (Dec 2025) that allows a "reasonable" commission ([MacRumors](https://www.macrumors.com/2025/12/11/apple-app-store-fees-external-payment-links/)) | Treated as upside, not base case. |
| Build timing | The Trend Detector recommends "build only as a narrow, fast wedge within 6–12 months." The PM analysis recommends "don't build as specified, validate first." | Reconciled: validate in 2–4 weeks, *then* build fast. Both agree on the narrow wedge. |

### Confidence levels

| Area | Confidence | Why |
|---|---|---|
| Built-in iOS TTS fails on long content | **High** | 15+ independent threads over 10+ years |
| Competitive saturation / H2 | **High** | Multiple independent vendor, press and review sources |
| API cost curve and gross-margin math | **Medium–High** | Vendor list prices; some from trackers |
| Subscription benchmarks | **Medium–High** | RevenueCat 2026 covers 115K+ apps |
| TAM/SAM/SOM | **Low–Medium** | Built on estimates and analyst assumptions marked [A] |
| Professional-segment demand | **Low** | No first-person evidence |

---

## 2. Market Landscape

### Market overview: size the market by revealed spend, not report mills

Third-party "TTS market" reports put 2025 at **$3.5–4.9B**, with CAGRs ranging from **3.7% to 23.3%** for the same year ([GM Insights](https://www.gminsights.com/industry-analysis/text-to-speech-market), [Mordor](https://www.mordorintelligence.com/industry-reports/text-to-speech-market), [Technavio](https://www.technavio.com/report/text-to-speech-market-industry-analysis), [Credence](https://www.credenceresearch.com/report/text-to-speech-market)). A sixfold spread in growth estimates shows these numbers are not measured, and they mix IVR, automotive and enterprise APIs. **They are excluded from this analysis.**

Credible anchors are:

| Anchor | Figure | Source | Relevance |
|---|---|---|---|
| ElevenLabs | ~$500M ARR (Apr 2026), $11B valuation, $500M Series D (Feb 2026) | [TechCrunch](https://techcrunch.com/2026/02/04/elevenlabs-raises-500m-from-sequioia-at-a-11-billion-valuation/), [ElevenLabs](https://elevenlabs.io/blog/500m-arr-and-new-investors) | Mostly API and enterprise. The consumer reader is a showcase. |
| Speechify | 50–60M users claimed; profitable 4.5 years; ~$2M/month on US iOS (estimate) | [BigGo/Weitzman](https://finance.biggo.com/news/82a0b4613f50dfa4), [Sensor Tower](https://app.sensortower.com/overview/1209815023?country=US) | The only large consumer read-aloud revenue pool |
| US audiobooks | $2.43B in 2025, +9% | [Publishers Weekly / APA](https://www.publishersweekly.com/pw/by-topic/industry-news/audio-books/article/100588-u-s-audiobook-sales-up-9-in-2025-reaches-2-43-billion.html) | Shows the listening habit is growing |
| Audiobook reach | 37% of Americans 12+ listened in the past year | [Edison Infinite Dial 2026](https://www.edisonresearch.com/the-infinite-dial-2026/) | Upper bound on habituated listeners |
| Voice-AI investor appetite | Wispr $2B valuation (Aug 2026); Fish Audio ~$50M seed on $21M ARR | [TechCrunch (Wispr)](https://techcrunch.com/2026/08/17/wispr-raises-280m-at-2b-valuation-as-it-looks-beyond-dictation/), [TechCrunch (Fish)](https://techcrunch.com/2026/07/28/fish-audio-raises-50m-seed-to-build-ai-voice-models-for-creators-and-enterprises/) | Capital is available for voice, but in *input* and *models*, not reader apps |

### Key segments

| Segment | Size signal | Evidence of pain | WTP profile | Served by |
|---|---|---|---|---|
| Blind / low vision | 7.15M Americans with best-corrected vision loss ([CDC VEHSS](https://www.cdc.gov/vision-health-data/prevalence-estimates/vision-loss-prevalence.html)) | **Strong** (AppleVis, Apple Community) | Loyal but **subscription-hostile** | Voice Dream, Speech Central (free for VoiceOver users), built-ins |
| ADHD | 15.5M US adults diagnosed (6.0%) ([CDC MMWR](https://www.cdc.gov/mmwr/volumes/73/wr/mm7340a1.htm)) | Medium (secondary sources; Reddit not mined) | Pays for Speechify; "transformative" | Speechify |
| Dyslexia | "Perhaps as many as 15–20%" show *some symptoms* ([IDA](https://dyslexiaida.org/dyslexia-basics/)); an upper bound, not a TAM | Medium | Core Speechify market | Speechify |
| Academics / researchers | Part of the ~3.5M [A] in the SAM | Medium ([Zotero](https://forums.zotero.org/discussion/124826/ios-ipados-spoken-content-not-continuing-to-next-page-instead-goes-in-circles), [Adobe](https://community.adobe.com/t5/acrobat-reader-mobile-discussions/text-to-speech-function-for-acrobat-reader-dc-with-option-to-omit-reading-footnotes/td-p/11165366)) | Pays ~$59–99 for [Listening.com](https://www.listening.com/pricing) | Listening.com, Readwise |
| Lawyers / consultants / analysts | ~2.7M [A] | **None first-person.** Only vendor content ("a 40-page brief at 1.25x ≈ 90 min") | Unknown; plausibly high if confidentiality is addressed | Nobody specifically |
| Commuters / Pocket refugees | Pocket shut down [July 8, 2025](https://techcrunch.com/2025/05/22/mozilla-is-shutting-down-read-it-later-app-pocket) | Medium | Low. [Instapaper](https://blog.instapaper.com/post/802011928668094464/ai-voices-text-to-speech-redesign-and-android) and Matter now absorb them | Instapaper, Matter, Readwise, ElevenReader |
| Students | Large | Weak direct voice | Near zero: ElevenReader is [free for a year](https://elevenreader.io/students), Speechify 50% off | ElevenReader, Speechify |

### Macro trends

| Trend | Direction for the founder | Evidence |
|---|---|---|
| Neural TTS cost collapse; on-device voice is viable | **Bullish on cost, bearish on defensibility** | [Kokoro-82M](https://huggingface.co/hexgrad/Kokoro-82M) (Apache-2.0) runs ~3.3x real-time on iPhone 13 Pro ([kokoro-ios](https://github.com/mlalma/kokoro-ios)); gpt-4o-mini-tts and Gemini Flash TTS cost ~$0.015/min ([OpenAI](https://developers.openai.com/api/docs/models/gpt-4o-mini-tts), [Google](https://ai.google.dev/gemini-api/docs/pricing)) |
| AI voice passes blind tests | Bullish | 61% thought an AI narrator was human; purchase intent 54% vs 56% ([Inside Radio / Edison](https://www.insideradio.com/free/edison-study-ai-audiobook-narration-clears-consumer-hurdle/article_1f33b1c0-c1c4-47c1-9431-9a959b898cf3.html)) |
| Platforms absorbing read-aloud | **Bearish** | [Google Docs Listen](https://9to5google.com/2025/08/18/google-docs-audio-gemini/) (Aug 2025), [iOS 26 Accessibility Reader](https://support.apple.com/guide/iphone/read-listen-text-apps-accessibility-reader-iph406a46ab8/ios), iOS 27 Siri "read a document" ([BGR](https://www.bgr.com/2177707/cool-new-ios-27-accessibility-features-look-forward-to-fall/)) |
| "Gist" replacing "whole thing" | **Bearish** for verbatim listening | NotebookLM Audio Overviews on mobile since May 2025 ([Google](https://blog.google/innovation-and-ai/products/notebooklm-app/)); Docs audio summaries (Feb 2026) |
| Read-later consolidation | Mixed | Pocket shut down; ElevenLabs [acqui-hired Omnivore](https://www.creativerly.com/the-exit-us-of-omnivore-from-open-source-to-ai-vc-money/) and courts [Pocket refugees](https://elevenreader.io/blog/best-pocket-alternatives-for-read-aloud) |
| ElevenReader moving into audiobook retail | Mixed: it may leave work documents less contested | 200K human-narrated titles, May 2026 ([ElevenLabs](https://elevenlabs.io/blog/elevenreader-launches-premium-audiobooks)) |
| AI-podcast novelty fading | Mildly bullish for verbatim | Microsoft retired consumer Copilot Podcasts on Aug 18, 2026 ([Microsoft](https://support.microsoft.com/en-gb/topic/podcasts-in-microsoft-copilot-11c7e451-e810-4a82-b619-f96d9badc0a8)) |

Search-interest direction is **unverified** because Google Trends was blocked. The one medium-confidence signal is ElevenReader momentum: #2–3 in Books & Reference on Google Play and 5M+ installs ([AppBrain](https://www.appbrain.com/app/elevenlabs-reader-ai-audio/io.elevenlabs.readerapp), [Similarweb](https://www.similarweb.com/app/google/io.elevenlabs.readerapp/)).

### Platform and infrastructure constraints (iOS)

| Capability | Feasible on iOS? | Implication |
|---|---|---|
| Read other apps' content / iMessage | **No** ([Apple](https://support.apple.com/guide/security/security-of-runtime-process-sec15bfe098e/web), [AppleInsider](https://appleinsider.com/articles/16/06/14/inside-ios-10-third-party-compatibility-opens-up-messages-to-apples-app-universe)) | **MVP2 is dead on iOS.** System-wide reading is an Android feature ([AccessibilityService](https://developer.android.com/reference/android/accessibilityservice/AccessibilityService)). |
| Share Sheet, Safari extension, OCR, Shortcuts | Yes | Parity only. Speechify and ElevenReader already ship them ([Speechify](https://speechify.com/blog/listen-to-websites-with-the-safari-extension-on-ios/), [ElevenLabs](https://help.elevenlabs.io/hc/en-us/articles/26197616307985-How-do-I-add-content-to-ElevenReader)). |
| Background audio + lock screen | Yes, but `AVSpeechSynthesizer` has quirks ([dev forum](https://developer.apple.com/forums/thread/732576)) | **Pre-render audio files.** This is how reliability becomes an engineering guarantee. |
| Google Drive access | `drive.file` + Picker: no CASA. Restricted scopes need CASA at $500–4,500+/yr ([Google](https://developers.google.com/identity/protocols/oauth2/production-readiness/restricted-scope-verification), [DeepStrike](https://deepstrike.io/blog/google-casa-security-assessment-2025)) | Use `drive.file` for MVP. A "live whole-Drive sync" wedge would cost CASA. |
| Google Docs export | Markdown/HTML keep headings; 10 MB cap ([files.export](https://developers.google.com/workspace/drive/api/reference/rest/v3/files/export)) | Heading navigation is cheap to build |
| PDF structure | Vision `RecognizeDocumentsRequest` (iOS 26) runs on-device ([docs](https://developer.apple.com/documentation/vision/recognizedocumentsrequest)); [Mistral OCR 3](https://mistral.ai/news/mistral-ocr-3/) ~$1–2 per 1,000 pages | **Cleanup costs ~$0.002/page. Quality is the differentiator, not cost.** |
| CarPlay | Ambiguous: the guide excerpt bars "text-to-speech systems" ([CarPlay guide](https://developer.apple.com/download/files/CarPlay-Developer-Guide.pdf)), yet [Instapaper](https://blog.instapaper.com/post/716397810350784513) and [Speech Central](https://speechcentral.net/2024/05/08/nhance-your-carplay-experience-with-speech-centrals-text-to-speech-for-documents/) ship it | Pre-rendered audio strengthens the case |
| AI data disclosure | Guideline 5.1.2(i) requires consent before sending data to third-party AI ([TechCrunch](https://techcrunch.com/2025/11/13/apples-new-app-review-guidelines-clamp-down-on-apps-sharing-personal-data-with-third-party-ai)) | Cloud TTS gets an explicit consent screen, which **makes on-device a visible advantage** |

---

## 3. Customer Deep Dive

### Jobs to be done

| Job | Type | Evidence | Strength |
|---|---|---|---|
| Finish a long document by ear without babysitting the player | Functional | "on some pages it reads all the article, but on other pages it skips paragraphs, freezes or just stops reading in the middle" ([Apple Community](https://discussions.apple.com/thread/256044481)) | **High** (accessibility), unverified (professionals) |
| Hear only the main content | Functional | "haven't come across any app in the market that can omit the footnotes" ([Adobe Community](https://community.adobe.com/t5/acrobat-reader-mobile-discussions/text-to-speech-function-for-acrobat-reader-dc-with-option-to-omit-reading-footnotes/td-p/11165366)) | Medium |
| Resume exactly where I left off | Functional | "It would be useful if the text-to-speech function remembered where it had last been reading" ([Readwise changelog](https://docs.readwise.io/changelog)) | Low–Medium as a *named* pain; it is table stakes |
| Turn commute time into document time | Functional | Vendor content only | **Unverified** |
| Get the gist fast (competing job) | Functional | [NotebookLM](https://www.macrumors.com/2025/05/20/google-releases-notebooklm-app-for-ios-and-android/), [Docs audio summaries](https://workspaceupdates.googleblog.com/2026/02/listen-to-audio-summaries-in-google-docs.html) | Rising |
| Don't waste my listening investment | Emotional | "Don't want to sink a few hours into a text only to have ElevenReader freeze, without even having a way to restart from the right point" ([justuseapp](https://justuseapp.com/en/app/6479373050/elevenlabs-reader-ai-audio/reviews)) | Medium |
| Don't feel exploited by a tool I depend on | Emotional | "hoping you forget to cancel" ([Trustpilot](https://www.trustpilot.com/review/speechify.com)); "Subscription = deal breaker!" ([mjtsai](https://mjtsai.com/blog/2024/04/08/voice-dream-reader-switches-to-subscriptions/)) | High |

**So what:** The job with evidence behind it ("finish it without failures") is voiced by accessibility users about **free** tools. The job the founder wants to serve ("a professional absorbs a 20-page briefing on the go") has **no first-person evidence**, and it competes with a fast-growing substitute ("just give me the gist").

### Pain points, ranked by frequency × intensity

| Rank | Pain | Frequency | Intensity | Representative evidence |
|---|---|---|---|---|
| 1 | iOS built-in TTS stops, skips or loops on long content | High (15+ threads, iOS 8–26) | High (accessibility) | "Speak Screen… largely broken" ([thread](https://discussions.apple.com/thread/256013629)); 1.5x plays at ~2.5x; Zotero: Spoken Content "goes in circles endlessly" ([Zotero](https://forums.zotero.org/discussion/124826/ios-ipados-spoken-content-not-continuing-to-next-page-instead-goes-in-circles)); "iPhone will only read a few words or a few lines of a PDF" ([thread](https://discussions.apple.com/thread/255360754)) |
| 2 | Billing and trial dark patterns (Speechify) | High | High | "There is no way to sign up free plan straightaway. They force you to accept free trial and force you to provide credit card details" ([Trustpilot](https://www.trustpilot.com/review/speechify.com)); "charged $1.00 the same day and $188.00 after free trial expired" ([BBB](https://www.bbb.org/us/fl/miami/profile/education/speechify-inc-0633-92046942/complaints)) |
| 3 | Subscription backlash (accessibility) | High in 2024 | Very high | "not willing to pay for what, ultimately, is local-only software" ([mjtsai](https://mjtsai.com/blog/2024/04/08/voice-dream-reader-switches-to-subscriptions/)); "will not pay $60 a year" ([AppleVis](https://www.applevis.com/comment/146280)) |
| 4 | PDFs read badly: headers, footers, footnotes, columns, tables | Medium | High for academics and lawyers | "confusing… to have the headers and footers read in the middle of the sentence" ([W3C](https://lists.w3.org/Archives/Public/w3c-wai-gl/2015AprJun/0224.html)); ElevenReader drops different sections on each upload ([speedreadinglounge](https://www.speedreadinglounge.com/elevenreader-review)); Speechify "adds arbitrary pauses… at the end of each print line" ([App Store via snippet](https://apps.apple.com/us/app/speechify-text-to-speech-pdf/id1209815023?see-all=reviews)) |
| 5 | Paid incumbents lose place or freeze on long content | Medium | High | Speechify: "if you select the wrong thing, it loses the page and goes back to the beginning of the book" ([Medium](https://ashishdoneriya.medium.com/bugs-in-speechify-f25852241cca)); ElevenReader: "loses its place" ([justuseapp](https://justuseapp.com/en/app/6479373050/elevenlabs-reader-ai-audio/reviews)) |
| 6 | Flaky cloud import | Low–Medium | Medium | Speechify Google Drive links "maybe one try in 10" ([App Store via snippet](https://apps.apple.com/us/app/speechify-text-to-speech-pdf/id1209815023?see-all=reviews)) |

### Desired outcomes (in users' words)
- "read to the end of the document without stopping"
- "just the main content of each page without repeating the same footnotes" ([Adobe](https://community.adobe.com/t5/acrobat-reader-mobile-discussions/text-to-speech-function-for-acrobat-reader-dc-with-option-to-omit-reading-footnotes/td-p/11165366))
- "remembered where it had last been reading" ([Readwise](https://docs.readwise.io/changelog))
- "restart from the right point" ([justuseapp](https://justuseapp.com/en/app/6479373050/elevenlabs-reader-ai-audio/reviews))

### Decision-making and barriers

| Factor | Evidence | Implication |
|---|---|---|
| Voice quality anchors choice | Users stay with ElevenReader despite bugs "because of its high-quality voice" ([justuseapp](https://justuseapp.com/en/app/6479373050/elevenlabs-reader-ai-audio/reviews)) | A new entrant can't win on voice. It must *demonstrate* reliability before install. |
| Free is "good enough" for casual users | "if you only need the occasional article read aloud, you may not need to install anything" ([aidictation](https://aidictation.com/blog/text-to-speech-iphone)) | The occasional user is not a customer |
| Governments think built-ins suffice | The UK DfE proposes funding assistive software only where free OS tools fall short ([DfE consultation](https://consult.education.gov.uk/disabled-students-allowance-team/assistive-software-funded-through-disabled-student)) | Headwind for accessibility sales, and direct counter-evidence to H1 |
| Trust and billing anxiety | "predatory" ([Apple Community](https://discussions.apple.com/thread/256048372)) | No-card trial and reminder emails are a positioning asset |
| Confidentiality | ABA Rule 1.6 inferred; Apple 5.1.2(i) consent screens make cloud sharing explicit | On-device processing may matter for professionals. **Unvalidated.** |

**Counter-evidence to the pain:** Speechify holds 4.7/5 on Trustpilot, ~83% five-star ([Trustpilot](https://www.trustpilot.com/review/speechify.com)), and billing anger "has not visibly hurt its growth." Pain with incumbents is not the same as willingness to switch.

---

## 4. Competitive Analysis

### Competitive landscape
The market has four layers:
1. **Speechify** owns distribution. It tests ~1,300 AI-generated ads a day and spends $500K a month on creative testing ([Dealroom](https://app.dealroom.co/news/note/1-000-ai-ads-a-day-and-tokens-over-salaries-inside-speechify-s-playbook-for-owning-the-voice-ai-market)).
2. **ElevenReader** owns quality and runs its own model near marginal cost.
3. **A crowded mid-tier and long tail** of template apps.
4. **Free platform substitutes** from Apple, Google and Microsoft.

### App Store and substitute comparison

Ratings are from third-party aggregators where available. "n/v" means not verified: App Store pages were blocked.

| Product | Price (US) | iOS rating | Google Docs import | PDF cleanup | Resume / sync | Desktop | On-device / privacy |
|---|---|---|---|---|---|---|---|
| **[Speechify](https://speechify.com/)** | $139/yr or $29/mo ([costbench](https://costbench.com/software/ai-voice-tools/speechify/)) | 4.7 (count n/v) | Yes via Drive, **flaky** ("one try in 10") | *Claims* skip footnotes/headers; users report line-end pauses | Cross-device sync; users report "loses the page" | Mac, web, Chrome/Edge ext | Cloud voices; offline on Premium |
| **[ElevenReader](https://elevenreader.io/blog/best-pricing-more-value)** | Free 10 h/mo; $11/mo or $99/yr | 4.7–4.72 (~9.2K) ([appbrain](https://www.appbrain.com/appstore/elevenreader-read-books-aloud/ios-6479373050)) | **No native.** Copy-paste or file ([castreader](https://castreader.com/blog/elevenreader-review-2026)) | **Weak:** complex PDFs "incomplete, out of order"; 500-page cap | iOS/Android/web sync; "loses its place" | Web + Chrome ext; no native app | Cloud; offline on Ultra |
| **[NaturalReader](https://help.naturalreaders.com/en/articles/8854700-plans-pricing-personal-version)** | $79–159/yr | n/v; Trustpilot 1.6 ([Trustpilot](https://www.trustpilot.com/review/www.naturalreaders.com)) | Yes via Drive ("basic") | n/v | "Limited"; no progress sync from Drive | Win/Mac/web/Chrome | Cloud + basic voices |
| **[Voice Dream – Natural Reader](https://apps.apple.com/us/app/voice-dream-natural-reader/id496177674)** | ~$60–80/yr (legacy one-time kept) | n/v | Via Drive/Dropbox | n/v | Strong bookmarks/position | Native Mac | Offline, on-device voices |
| **[Speech Central](https://speechcentral.net/)** | **$9.99 one-time**; free for VoiceOver users | n/v | Via files | Marketed "heavy PDF cleanup" | n/v | Mac, Windows | System voices, on-device |
| **[Peech](https://apps.apple.com/us/app/peech-text-to-speech-reader/id1429704005)** | $70–99/yr (many tiers seen) | n/v | Files/PDF | n/v; called "most accurate and reliable" ([beingpaperless](https://beingpaperless.com/peech-text-to-speech-reader-for-ipad-full-review/)) | n/v | n/v | n/v |
| **[Audeus](https://www.audeus.com/pricing)** | $19/mo or $119/yr | n/v | **Yes (marketed "Gdocs")** | n/v | **Auto-resume marketed** | Web | Cloud |
| **[Listening.com](https://www.listening.com/features)** | $59–99/yr (conflict) | n/v | PDF | **Yes, for academic papers** (skips citations) | Sentence bookmarks | Web | Cloud |
| **[Audioread](https://audioread.com/pricing)** | $4.99–9.99/mo; $69.99/yr | n/v | Via forward or URL | n/v | Via your podcast app | Web, ext | Cloud |
| **[Readwise Reader](https://docs.readwise.io/reader/docs/faqs/text-to-speech)** | $119.88/yr ([pricing](https://readwise.io/pricing/reader)) | n/v | No (read-later) | PDFs in text view only | Starts from scroll position | Yes | Cloud |
| **[Voice Aloud Reader (MWM)](https://www.appbrain.com/appstore/voice-aloud-reader/ios-1446876360)** | n/v | 4.64 (~19K) | n/v | n/v | n/v | No | n/v |
| **[Google Docs Listen](https://workspaceupdates.googleblog.com/2025/08/listen-to-documents-using-gemini-google-docs.html)** | Bundled with Workspace / Google AI plans | N/A | **Native** | N/A (Docs only) | n/v | **Web only** at launch | Cloud (Gemini) |
| **[iOS Speak Screen / Accessibility Reader](https://support.apple.com/guide/iphone/read-listen-text-apps-accessibility-reader-iph406a46ab8/ios)** | Free | N/A | Via any app | None | **No**; "loses your place" | Mac equivalents | **On-device** |
| **[NotebookLM](https://blog.google/innovation-and-ai/products/notebooklm-app/)** | Free | n/v | Via Drive | N/A (summarizes) | N/A | Web | Cloud |
| **Audio Anywhere (proposed wedge)** | $69/yr target | — | `drive.file` Picker + Share Sheet | **Core differentiator** | Exact resume via pre-rendered audio | Chrome ext before Mac | **On-device default** |

**Reading the table:** Every column in the founder's MVP1 except *PDF cleanup quality* and *on-device privacy* has at least three "Yes" entries. Those two columns are where the wedge must live.

### Key competitor profiles (condensed)

| Competitor | Strength | Weakness | Threat level |
|---|---|---|---|
| **Speechify** | Distribution, brand, SEO/ASO, profitability, feature breadth; SIMBA 3.0 in the Artificial Analysis top 10 | Billing distrust (BBB F rating, 80+ billing complaints per [costbench](https://costbench.com/software/ai-voice-tools/speechify/)); long-content bugs; feature bloat ("no recently opened files") | **Very high.** Owns acquisition. |
| **ElevenReader** | Best voices; near-zero marginal cost; free 10 h/mo; students free; $500M in fresh capital | Resume and freeze bugs; weak PDF parsing; no native desktop; audio locked in app | **Very high.** Could fix our wedge in a sprint if it chose to. |
| **Audeus** | Already markets the exact MVP1 | Unknown scale and funding | Medium. Proves MVP1 is not novel. |
| **Listening.com** | A vertical niche (academic papers) that works | Academic-only | Low. **Proof that verticalization works.** |
| **Speech Central** | $9.99 one-time; owns "anti-subscription" among accessibility users | System voices | Medium in accessibility |
| **Google / Apple** | Free, default, improving | Google: web-only, Docs-only. Apple: older voices, 10+ years of long-content bugs. | **High and rising** |

### White space

| Unmet need | Evidence of gap | Who could close it fast | Our odds |
|---|---|---|---|
| Structure fidelity for professional PDFs (footers, footnotes, columns, tables) | Adobe, W3C and ElevenReader complaints; only Listening.com (academic) addresses it | ElevenLabs (capable, not prioritized) | **Best available** |
| Guaranteed long-session reliability + exact resume | Complaints across Apple, Speechify and ElevenReader | Apple (iOS 27.x), ElevenLabs | Medium; hard to *market* |
| On-device confidentiality | Cloud incumbents can't claim it without undermining their model | Apple (with weaker voices, no cleanup) | Medium; **unvalidated demand** |
| Honest billing | Speechify's #1 complaint theme | Already occupied by Speech Central ("Pay Once") | Low as a sole differentiator |
| Live Google Doc re-sync | Nobody found doing it (unverified) | Google itself | Low. Google is moving Docs voice to mobile. |

---

## 5. Strategic Interpretation (from the PM analysis)

This section merges the PM Expert's framework analysis ([raw/pm-analysis.md](../raw/pm-analysis.md)) with the evidence above. Where the PM view and the evidence diverge, the tension is flagged.

### 5.1 Verdict and wedge
The PM verdict is **"Don't build as specified."** It is consistent with the evidence synthesis. The wedge it identifies matches the white-space analysis:

> *For professionals who have to absorb long, structured work documents, Audio Anywhere is a private briefing reader that plays only the substance of your PDFs and Google Docs, start to finish, on-device, and never loses your place. Unlike Speechify or ElevenReader, which read everything including page furniture and send your files to the cloud, it is built for documents that matter and stay confidential.* (Test this statement; do not adopt it yet.)

**Category choice:** Not "text-to-speech app," which Speechify owns. Instead **"briefing reader" or "audio for work documents,"** a sub-category that [Listening.com](https://www.listening.com/) showed can work for academic papers.

### 5.2 Switching dynamics (Four Forces)

| Force | Strength | Evidence |
|---|---|---|
| Push away from current tools | **Strong for free built-ins; weak for paying ElevenReader and Speechify users** | Built-in failure threads; ElevenReader users stay for the voice |
| Pull toward a reliable, clean reader | Moderate; invisible before trial | "just the main content" |
| Anxiety | Moderate–Strong | Billing distrust; confidentiality; 5.1.2(i) consent screens |
| Habit | **Strong** | Reading on screen, skimming, asking an AI for a summary |

**Net:** Switching likelihood is low for general consumers, medium for built-in users who hit failures, and unknown for professionals. **Go-to-market implication:** show side-by-side demo audio of the *same messy PDF* read by Speechify, ElevenReader and us before install.

### 5.3 Porter's Five Forces

| Force | Intensity | Key evidence |
|---|---|---|
| Rivalry | **Very high** | Speechify ad machine; ElevenReader price cut 50%; "Pay Once, Not $139/yr" SEO pages |
| Threat of new entrants | **Very high** | Free Kokoro; $15–30/1M-char APIs; new template apps every quarter ([TTS Reader Pro](https://apps.apple.com/us/app/ttsreader-text-to-speech-ai/id6746346171) and similar) |
| Substitutes | **Very high** | Accessibility Reader, Google Docs Listen, NotebookLM, [Edge Read Aloud](https://www.microsoft.com/en-us/edge/features/read-aloud), podcast feeds, reading it yourself |
| Buyer power | **High** | Zero switching cost; AppleVis forced Applause to [reverse within days](https://www.applevis.com/forum/ios-ipados/applause-has-backed-down-purchased-voice-dream-features-will-stay); ~23% renewal |
| Supplier power | **Medium–High** | Apple takes 15–30% and gatekeeps; the leading voice supplier (ElevenLabs) is also the leading competitor; [PlayHT shut down](https://texttolab.com/blog/play-ht-shutdown-alternatives) on ~5 months' notice |

**Verdict:** The structure is unattractive. Profit pools go to **voice-model owners** and **paid-acquisition machines**. An entrant with neither can only profit in a pocket where rivalry is low *because the job is specialized*.

### 5.4 Why now / why you / why not the giants

| Question | Answer | Probability the threat materializes |
|---|---|---|
| Why now? | Mixed. Costs have collapsed and voice passes blind tests, but the "robotic to human" shift was captured in 2023–25 by ElevenLabs and Speechify. **Window: 6–12 months.** | — |
| Why you? | **Unanswered, and the weakest link.** No evidence of vertical distribution, parsing IP or an audience. | — |
| Why not Apple? | It has deprioritized long-content reliability for 10+ years, but iOS 27 brings a Gemini-derived model and Siri "read a document." | Kills the generic reliability wedge within 18 months: **Medium.** Kills the structure wedge: **Low–Medium.** |
| Why not Google? | Already shipped Docs Listen on the web; voice is heading to Docs mobile. | Neutralizes the Google Docs angle: **High** |
| Why not ElevenLabs? | Could fix resume and PDF parsing in a sprint, but is focused on API, enterprise and audiobooks. It **cannot credibly claim on-device privacy.** | Out-executes you if it chooses: **High.** Chooses to within 12 months: **Medium.** |

### 5.5 Defensibility (7 Powers)
- **Available:** *Counter-positioning*, partial. It rests on on-device confidentiality and honest billing, but Speech Central already owns "anti-subscription." *Process power*, partial. It rests on a tuned cleanup pipeline per document type (court filings, 10-Ks, papers, policy briefs), plus an evaluation set of messy PDFs.
- **Not available:** scale economies (incumbents have them), network effects, branding, cornered resource. Switching costs are weak.
- **Real defensibility** would come only from a B2B or firm channel (procurement, VPAT, firm-wide deployment), which is unvalidated.

### 5.6 Pre-mortem (assume it failed by September 2027)

| Type | Risk | Likelihood / impact |
|---|---|---|
| **Elephant** | Professionals want summaries, not verbatim audio, or don't listen weekly | **Medium–High / Fatal** |
| Elephant | The founder's pain is really an accessibility-user pain, and those users are served and price-hostile | High / High |
| Elephant | Retention decays to the productivity norm (~23% renewal), leaving LTV at ~$32 | High / High |
| Elephant | "Reliability" can't be marketed before weeks of use | High / Medium |
| Tiger | Apple ships neural voices plus resume in Accessibility Reader or Siri | Medium / High |
| Tiger | Google ships "Listen" in iOS Docs | High / Medium |
| Tiger | ElevenReader fixes resume and PDF parsing | Medium / High |
| Tiger | Unit economics break on "unlimited cloud" voices | High if offered / High |
| Tiger | CAC exceeds LTV; head ASO terms are locked | High / High |
| Paper tiger | The "$4–5B TTS market"; Google CASA cost (avoidable); on-device voice quality (testable) | — |

### 5.7 PMF indicators
- **The category has PMF, and incumbents captured it.** Speechify is "worth every penny" for daily users ([fahimai](https://www.fahimai.com/speechify)). ElevenReader users say "I was looking at paying hundreds a year… ElevenReader is a game changer" ([speedreadinglounge](https://www.speedreadinglounge.com/elevenreader-review)). Accessibility users fought publicly to keep Voice Dream.
- **This product as specified: weak signals.** Briefing-reader wedge: **insufficient data.**
- **Aha moment to instrument later:** "finished a first document of 20+ pages without intervention."

### 5.8 Where the PM analysis and the evidence synthesis diverge

| Topic | PM analysis | Evidence synthesis / other raw files | Resolution |
|---|---|---|---|
| Timing | Validate first, then decide | The Trend Detector says "build… within 6–12 months" | Compatible: validate in weeks, then build fast. |
| Google Docs as a wedge | Kill it as a headline; Google neutralizes it | The Competitor Profiler floated "live Google Docs sync" as a possible wedge | **Side with the PM view.** A live-sync build needs CASA-restricted scopes, and Google is moving Docs voice to mobile. Keep Docs as an input, not the pitch. |
| Speechify revenue in TAM | Uses the Sensor Tower ~$24M US iOS figure | The Trend Detector calls Speechify revenue "unknown" | The TAM is labeled Low–Medium confidence. The conclusion (a modest, concentrated market) holds within a ±50% error. |
| Accessibility users | Upside only; not in SAM | Pricing Intel suggests a lifetime tier for accessibility users | Compatible: offer a lifetime or VoiceOver-free tier as **goodwill and word of mouth**, not as the revenue plan. |

---

## 6. Market Size and Revenue Potential

### TAM: revealed US consumer read-aloud spend

| Component | Calculation | Estimate |
|---|---|---|
| Speechify, US iOS | ~$2M/month × 12 ([Sensor Tower](https://app.sensortower.com/overview/1209815023?country=US); assumes that month is representative) | ~$24M |
| Speechify, other US channels | +50–100% of iOS [A] | $12–24M |
| ElevenReader, US | 5M installs × 2.6% paid × ~$80 × ~40% US [A] | ~$4M |
| Mid-tier and long tail | 10–15 apps × $0.5–1.5M [A] | $5–20M |
| **TAM** | | **≈ $45–70M/yr, midpoint ~$55M** |

### SAM: the US iOS briefing-reader wedge

| Step | Assumption | Result |
|---|---|---|
| US professionals consuming 20+ page structured documents | [A] lawyers 1.3M + consultants 1M + financial analysts 0.4M + policy analysts 0.5M + researchers/faculty/grad students 3.5M | 6.7M |
| Weekly verbatim-listening need | [A] 10–20% (anchored loosely on [Edison's](https://www.edisonresearch.com/the-infinite-dial-2026/) 37% audiobook reach, discounted) | 0.67–1.34M |
| On iPhone | [A] ~57% | 0.38–0.76M |
| Would pay ≥$69 rather than use free alternatives | [A] 20–30% | 76K–230K |
| **SAM at $69/yr** | | **≈ $5–16M/yr** |

### SOM: realistic capture

| Horizon | Assumptions | Result |
|---|---|---|
| Year 1 | 30K installs from long-tail ASO and vertical communities (no paid engine) × 3–6% install-to-paid × $69 × 0.85 | **900–1,800 payers → $53–106K bookings (net of Apple's 15%)** |
| Year 3 | 5–10K active payers; requires annual renewal ≥40% (vs the 23% productivity median) | **$0.35–0.7M ARR** (~3–6% of SAM) |
| Venture case | Firm/enterprise licensing or edu/disability-services channel with a VPAT | **Unvalidated** |

**Sensitivity (synthesizer check):** The year-3 figure is most sensitive to renewal. At the 23% median, a steady 1,800 new payers a year sustains only about 2,300 active payers (1,800 / (1 − 0.23)), or **~$135K ARR**, not $0.35M. Reaching the PM's range needs *both* higher renewal *and* install volume growing to roughly 60–100K a year. **Treat $0.35–0.7M as the success case, not the base case.**

---

## 7. Pricing, Unit Economics and Founder Compensation

### Competitive price bands

| Band | Annual price | Players |
|---|---|---|
| Free / near free | $0–10 | iOS built-ins, Google Docs Listen (bundled), NotebookLM, ElevenReader free 10 h/mo, Speech Central $9.99 lifetime |
| Low | ~$60 | [Instapaper](https://9to5mac.com/2023/12/05/instapaper-price-increase-new-features/) $59.99, Voice Dream $60–80, Listening.com (low estimate) |
| **Mid (dense)** | **$70–120** | Audioread $69.99, NaturalReader Lite $79, [Matter](https://gleamr.io/blog/matter-app-pricing-2026) $79.99, ElevenReader $99, Audeus $119, Readwise $119.88 |
| Premium | $139–159 | Speechify $139, NaturalReader Pro $159 |
| Benchmarks | ~$100–180 | [Blinkist](https://nibble-app.com/blog/blinkist-cost) ~$100, [Audible](https://www.dealnews.com/features/audible/cost/) Premium Plus $14.95/mo |

### Cost of goods: TTS per 20-page document (~60K characters, ~70 min)

| Voice option | Cost/doc | Heavy user (20 h/mo) |
|---|---|---|
| On-device (Kokoro-82M, Apple premium voices) | $0 | $0 |
| OpenAI tts-1 / Google Neural2 ([Google](https://cloud.google.com/text-to-speech/pricing)) | ~$0.90–0.96 | ~$15–16 |
| gpt-4o-mini-tts / Gemini Flash TTS | ~$1.05 | ~$18 |
| Google Chirp 3 HD / tts-1-hd | $1.80 | ~$31 |
| ElevenLabs Flash ([ElevenLabs API](https://elevenlabs.io/pricing/api)) | $3.00 | ~$52 |
| ElevenLabs v2/v3, Polly Long-Form ([AWS](https://aws.amazon.com/polly/pricing/)) | $6.00 | ~$103 |

### Gross margin at $9.99/mo (15% Apple fee → $8.49 net)

| Voice cost | Light (2 h/mo) | Moderate (5 h/mo) | Heavy (20 h/mo) |
|---|---|---|---|
| On-device $0 | ~100% | ~100% | ~100% |
| $16/1M | 81% | 51% | **−94%** |
| $30/1M | 64% | 8% | **−264%** |
| $100/1M (ElevenLabs v3) | **−21%** | **−206%** | **−1,113%** |

**So what:** "Unlimited premium cloud voice" is not viable at $49–139/yr for anyone listening more than 4–5 h/month. ElevenReader and Speechify can do it only because they own their models. **Architecture:** unlimited on-device voice, plus 1–2 metered "studio" cloud hours a month at ≤$30/1M characters (~$1.50–3.10 COGS). *Correction (source verification): the raw pricing file proposed 5–8 hours at "~$1.60–2.50"; at ~51K characters per hour, 5–8 hours actually cost ~$7.70–12.30 at $30/1M. That exceeds the ~$7.64 net from an $8.99/mo plan. Larger allowances need a cheaper ($4–16/1M) voice or a higher-priced tier.* Cache per document so re-listens are free. Abstract across two or more vendors (the PlayHT lesson).

### The binding constraint is LTV and CAC, not COGS

| Benchmark ([RevenueCat 2026](https://www.revenuecat.com/blog/growth/subscription-app-trends-benchmarks-2026)) | Value |
|---|---|
| North America Day-35 download-to-paid (median) | 2.6% |
| Trial conversion: 17–32 day trials vs <4 day trials | 42.5% vs 25.5% |
| Productivity median annual renewal | **~23%** (lowest category) ([RevenueCat](https://www.revenuecat.com/blog/growth/average-subscription-renewal-rates-by-app-category)) |
| Median realized year-1 LTV per payer, North America | **$32** |
| New apps that never reach $1K total revenue | 57.7% |
| AI apps' long-term retention | Weaker than non-AI ([TechCrunch](https://techcrunch.com/2026/03/10/ai-powered-apps-struggle-with-long-term-retention-new-report-shows)) |

**Derived CAC ceiling (synthesizer calculation):** With LTV at $32–50 per payer and 3–6% install-to-paid, the maximum affordable cost per install is about **$1–3**. Speechify's ad machine sets the price of head keywords well above that. **Paid acquisition is not a viable primary channel.** Growth must come from organic vertical communities and long-tail ASO.

### Pricing recommendation
- **$8.99/mo or $69/yr.** Below ElevenReader ($99) and Speechify ($139), and above the $60 floor that cannot fund acquisition. Pricing Intel's sweet spot is $69–79.
- **Free tier:** on-device voice, limited documents. **Trial:** 14–30 days, **no card required**, with reminder emails. This counter-positions against Speechify.
- **Accessibility:** a lifetime tier, or free for VoiceOver users, as goodwill. Do not rely on it for revenue.
- **Team/firm plan:** $15–25 per seat per month, only if interviews surface *unprompted* confidentiality concerns.
- **Payments:** join Apple's [Small Business Program](https://developer.apple.com/app-store/small-business-program/) (15%) on day one. Treat US web checkout as upside only.

### Founder compensation: what the founder can realistically earn

| Scenario | Gross bookings / ARR | Approximate take-home capacity* |
|---|---|---|
| Year 1 (SOM) | $53–106K bookings (after Apple's 15%) | ~$40–95K before founder time. **Not a salary replacement** once taxes, tooling and any acquisition spend are counted. |
| Year 3, base (23% renewal) | ~$135K ARR | One part-time founder |
| Year 3, success (≥40% renewal) | $0.35–0.7M ARR | One to three people |
| Venture | Requires a B2B channel | Unvalidated |

*Synthesizer estimate. Assumes near-zero COGS (on-device) and fixed costs of a few thousand dollars a year (Apple developer program, parsing API, Google verification). Excludes paid acquisition.

---

## 8. Go-to-Market Considerations

### Channels

| Channel | Why | Evidence / source |
|---|---|---|
| Vertical communities: r/lawschool, r/LawFirm, Zotero forums, consulting and policy networks | Where the wedge's users are; organic | [Communities map](../raw/communities-found.md); Zotero iOS TTS complaints |
| Long-tail ASO: "read PDF aloud," "listen to documents," "briefing reader" | The head term "text to speech" is unwinnable | Speechify dominance ([speechify.com](https://speechify.com/)); no keyword volumes verified |
| Side-by-side demo content: the same messy PDF read by three apps | Reliability is invisible before install | PM Four Forces analysis |
| Chrome extension before a native Mac app | Reaches Google Docs in the browser plus Windows and Chromebooks | [ElevenReader Chrome](https://elevenreader.io/text-to-speech-chrome-extension); Speechify extension "alone is worth it" ([computertech](https://computertech.co/speechify-review/)) |
| AppleVis (feedback, goodwill) | Dense, vocal, reviews TTS apps in detail | [AppleVis ElevenReader page](https://www.applevis.com/apps/ios/utilities/elevenreader-read-text-aloud) |
| Edu / disability services (later) | Procurement needs a VPAT; ADA Title II deadline Apr 2027 | [Section508.gov](https://www.section508.gov/sell/acr-vpat-faq/); [Federal Register](https://www.federalregister.gov/documents/2026/04/20/2026-07663/extension-of-compliance-dates-for-nondiscrimination-on-the-basis-of-disability-accessibility-of-web) |

### Influencers
Jonathan Mosen ([mosen.org](https://mosen.org/voicedream/)), AppleVis editors, Michael Tsai and Jason Snell ([Six Colors](https://sixcolors.com/link/2024/04/another-app-switches-to-a-subscription-model/)) for the indie Apple audience. No professional-segment influencers were identified. That is a gap to close in interviews.

### Messaging (built from users' own language)
- **Lead with:** "Reads to the end. Never loses your place." "Only the substance: no headers, footers or page numbers." "Your documents never leave your phone."
- **Avoid:** "AI voices" (commoditized), "read anything" (Apple owns it), and "text to speech" as the category.

### Trust signals
No-card trial; reminder before charge; one-tap cancel; on-device processing with a plain-language 5.1.2(i) disclosure; a published cleanup benchmark on public PDFs; a lifetime option for accessibility users.

---

## 9. Strategic Recommendations

### Primary recommendation
**Do not write production code yet.** Run the seven experiments below, spending under $1.5K over 2–4 weeks. Build a narrow iOS MVP only if the gating experiments pass.

| # | Experiment | Cost / time | Proceed if | Kill if |
|---|---|---|---|---|
| 1 | **Incumbent bake-off**: 10 real long documents (footnote-heavy, multi-column, tables, 20–100 page Google Docs) through ElevenReader, Speechify, Audeus, Peech, Google Docs Listen and Accessibility Reader | ~$20, days 1–4 | Every incumbent fails ≥3 of 10 documents on completion or resume, **or** averages ≥3 structural errors per 10 pages | ≥2 incumbents complete ≥9 of 10 with ≤1 error per 10 pages and reliable resume |
| 2 | **JTBD switch interviews** with 15–20 professionals | $0–300, weeks 1–2 | ≥8 of 15 face ≥2 must-know long documents a week; ≥5 of 15 have tried or paid for TTS; recruiting takes ≤10 days | <5 of 15 have weekly frequency, **or** most say a summary suffices |
| 3 | **Concierge MVP:** clean documents (Mistral OCR + LLM) → audio (Kokoro/Chirp 3 HD) → private podcast feed; then a Sean Ellis survey plus a real Stripe payment ask | ~$50, weeks 2–4 | ≥60% submit a 2nd document in 7 days; **≥40% "very disappointed"**; **≥25% pay** | <15% pay, or <25% "very disappointed," or <30% submit a 2nd document |
| 4 | **Positioning smoke test:** "Private briefing reader" vs "Read anything aloud with AI" | $600–1,000, weeks 1–3 | CTR ≥1.0%; ≥15% join the waitlist; ≥5% pay a deposit; **≤$30 per paying customer** | >$60 per paying customer and weak organic channels |
| 5 | **Platform check** on iOS 27 and Google Docs iOS | $0, day 2 | The OS fails ≥30% of documents | The OS is within 20% of the best third-party app |
| 6 | **Cleanup + voice spike** on 30 PDFs; blind A/B test vs ElevenReader | ~$30, weeks 1–2 | ≥95% of pages with no leakage; preferred ≥65% on structured documents; Kokoro accepted for ≥30 min by ≥50% | Can't beat ElevenReader on structured documents |
| 7 | **"Why you" memo:** the vertical, the first 100 users by name or channel, the edge | $0, day 1 | A concrete channel to ≥100 target users | No vertical access and paid CAC fails |

**Overall kill rule:** Stop or pivot (Android-first "read anything," or a B2B firm tool) if Exp. 3 fails its pay or "very disappointed" threshold, **or** if two of Exp. 1, 5 and 6 hit their kill thresholds.
**Build rule:** Build only if Exp. 2 and 3 pass **and** at least two of Exp. 1, 4 and 6 pass.

### If the build rule passes: MVP scope

| In | Out |
|---|---|
| PDF + Share Sheet import; Google Docs via `drive.file` Picker | "Read anything anywhere," iMessage/texts (impossible on iOS) |
| Structure cleanup (headers, footers, footnotes, reading order, tables); heading navigation | Voice cloning, celebrity voices |
| Pre-rendered on-device audio; exact resume; lock-screen controls; offline | "Unlimited cloud premium voice" |
| 1–2 metered cloud studio hours (more only on a cheaper voice or a higher tier); two or more vendors | Restricted Drive scopes / CASA |
| Chrome extension as the second surface | Native Mac app (use Catalyst later) |

### Key success factors
1. Measurably better structure cleanup than ElevenReader on professional document types, proven in a blind test.
2. Weekly listening frequency in at least one profession.
3. An organic channel into that profession; CAC ≤ $30 per payer.
4. Annual renewal ≥40%.
5. Shipping before iOS 27.x/28 closes the generic reliability gap.

### Risks and mitigations

| Risk | Mitigation |
|---|---|
| Professionals prefer summaries | Exp. 2/3 gate. Possibly add "summary first, then full read" as a feature, not the pitch. |
| Apple closes the gap | Anchor on structure and confidentiality, not generic reliability. Rerun Exp. 5 at each iOS release. |
| ElevenReader copies the wedge | Go deep in one vertical: per-document-type cleanup and an evaluation set. |
| Margin collapse | On-device default; metered cloud; caching |
| Accessibility backlash | Lifetime / VoiceOver-free tier; honest billing |

### Open questions
1. How often do professionals *need* verbatim listening, as opposed to a gist?
2. Is confidentiality a real purchase driver, or an analyst's inference?
3. What are the actual App Store ratings and 1–3 star review themes for Speechify, ElevenReader and Speech Central on long PDFs? (Blocked here.)
4. What do Reddit communities say about WTP and switching? (Not mined.)
5. What is Google Trends seasonality around back-to-school? (Unverified.)
6. Does iOS 27's Siri "read a document" include position memory and neural voices?

### Next steps (the next 14 days)
1. **Day 1:** write the "why you" memo (Exp. 7); start interview recruiting (Exp. 2).
2. **Days 1–4:** run the bake-off (Exp. 1) and the iOS 27 check (Exp. 5).
3. **Week 1:** launch landing pages A/B (Exp. 4); start the cleanup spike (Exp. 6).
4. **Week 2:** start the concierge pilot (Exp. 3) with the first 10–15 interviewees.
5. **In parallel:** do a manual Reddit and App Store review pass to fill the evidence gaps above.

---

## 10. Addendum: Follow-up Questions (25 Sep 2026)

The founder asked eight follow-up questions after reading the report. Each answer below starts with the short answer. Evidence is in [raw/business-models.md](../raw/business-models.md) and [raw/platform-limits.md](../raw/platform-limits.md). Tags: [A] = analyst assumption, [U] = unverified.

### 10.1 Is the market saturated, or does it just have established leaders?

**Short answer: it has established leaders and a crowded long tail. It is saturated in features and in advertising, not in customer satisfaction.** "Saturated" was too blunt. Three different things are true at once:

| Layer | State | What it means for you |
|---|---|---|
| **Spend** | **Concentrated.** Speechify takes roughly two-thirds to three-quarters of US consumer spend, and ElevenReader is the fast #2 | The top two own the head search terms and the ad auctions |
| **Features** | **Saturated.** Google Docs import, resume, sync and natural voices each ship in 3+ apps | You can't win on a feature checklist |
| **Satisfaction** | **Not saturated.** Speechify has an F rating at the BBB over billing; users say ElevenReader "loses its place"; Apple's built-in readers have a decade of bug threads | People are unhappy, but unhappy people don't find you without distribution |

**Why the niche exists if the market is crowded.** Niches survive next to strong leaders for four reasons, and all four apply here:

1. **It's small.** Professionals who must hear 20–200-page structured documents word for word are about a $5–16M niche (§6). That's too small for Speechify's growth targets or ElevenLabs' $11B valuation to care about. Honestly, that's the main reason it's open, and it also caps what you can earn.
2. **The leaders' business models point elsewhere.** Speechify earns its money on mass-market students, dyslexic readers and books, using high-volume ads. ElevenReader exists to showcase ElevenLabs' cloud voices and now sells audiobooks. Neither is rewarded for the unglamorous work of reading footnotes and tables correctly.
3. **Getting document structure right is hard, boring engineering.** It doesn't make a good ad, so it gets underinvested.
4. **Privacy cuts against a cloud-voice business model.** An app whose pitch is "your document never leaves your phone" competes against its own premium cloud voices. *Correction: this gap is narrowing. Speechify launched on-device iOS voices in Dec 2025 ([Speechify](https://speechify.com/news/speechify-launches-on-device-ios-ai-voices-for-offline-reading/)), and small apps built on the free Kokoro voice model already exist (Local TTS, Sandbook, Voice Forge). On-device voices are becoming table stakes. Privacy by design (no account, no upload, no server) is still rare.*

### 10.2 Where do the costs actually come from? (ELI5)

**Short answer: the voice is cheap. Finding customers is expensive, and Apple takes a cut.** High prices are set by what buyers will pay and by the cost of advertising, not by the cost of generating speech.

**The lemonade-stand version.** Imagine selling a $139 cup of lemonade:
- **Apple takes $21–42** just for letting you sell on its App Store (15–30%).
- **The lemons (the voice)** cost about **$15 a year** for a typical listener. Speechify says its voices cost it "single-digit dollars per million characters" [U], and at 5 hours a month that's roughly $15.
- **The billboards (ads)** are the big cost. In the US, each app install bought through ads costs about **$4–6** ([AppTweak](https://www.apptweak.com/en/aso-blog/apple-ads-benchmarks)), and only about 2–10% of installs ever pay. So each *paying* customer costs about **$50–300 in ads**. Speechify spends about $500K a month just *making* ads, testing about 1,300 AI-made ads a day ([Speechify/20VC](https://speechify.com/news/speechify-ceo-cliff-weitzman-20vc-podcast/)).
- **Refunds and chargebacks** take about 2–5%.
- What's left pays staff, servers and profit.

**Why the price is so high:** most subscribers quit within a year (productivity apps renew at only about 23%). An app therefore has to take a big annual payment up front to earn back the $50–300 it spent to find that customer. The high price comes from the high advertising cost.

**Why the price *can* be so high:** buyers compare against expensive anchors. Read&Write costs about $170 a year and Kurzweil about $500. In the UK, government disability grants (DSA) have paid for 86K+ ClaroRead licences ([Everway](https://www.everway.com/en-gb/govt-grant-schemes/what-is-dsa/claroread/)), so many accessibility buyers aren't paying out of pocket. That anchor is weakening: the UK has proposed removing most software from DSA ([Wonkhe](https://wonkhe.com/blogs/dfe-proposes-to-strip-most-assistive-software-out-of-disabled-students-allowance/)).

**Why Speech Central can charge $9.99 once:**
- It uses the iPhone's built-in voices, so each listening hour costs $0.
- It runs no ads and has no paid acquisition.
- It's a tiny team.
- It grows through goodwill: free for VoiceOver users and schools ([speechcentral.net](https://speechcentral.net/)).

Remove ads and cloud voices, and $9.99 is sustainable, but only at small scale.

### 10.3 Would cheap infrastructure (DigitalOcean) plus tiers win market share?

**Short answer: cheap infrastructure brings voice cost close to zero, but voice cost was never the main cost. A low price helps you convert and keep customers. It does not solve discovery.**

**Cost per hour of generated audio:**

| Option | $ per audio hour | Notes |
|---|---|---|
| On-device (iPhone's built-in voices, or Kokoro on the phone) | **$0** | Uses the user's battery. See 10.5 for the screen-lock limit. |
| Self-hosted Kokoro on a GPU (DigitalOcean RTX 4000 Ada at $0.76/h; RunPod/Vast RTX 4090 at $0.29–0.69/h) | **~$0.01–0.04** | Kokoro runs 36–96× faster than real time on a GPU ([benchmark](https://gist.github.com/efemaer/23d9a3b949b751dde315192b4dcf0653)) |
| Self-hosted Kokoro on a CPU-only droplet | ~$0.07–0.19 | 0.9–5× real time depending on cores ([benchmark](https://github.com/obole-ia/tts-cpu-benchmark)) |
| Hosted Kokoro API (someone else runs the GPU) | ~$0.03–0.04 | $0.65–0.80 per 1M characters |
| Self-hosted Orpheus / Chatterbox (more expressive) | ~$0.05–0.35 | Orpheus weights use Meta's Llama licence |
| Mid-tier cloud API (OpenAI, Google Neural2, Chirp 3 HD) | $0.77–1.54 | $15–30 per 1M characters |
| ElevenLabs | $2.60–5.10 | The premium benchmark |

GPU prices are from third-party trackers such as [computeprices](https://computeprices.com/providers/digitalocean) [U]; check them against DigitalOcean's own pricing page.

**The trap: an idle server.** One always-on GPU droplet costs **$215–555 a month whether anyone listens or not**. At 100 users that's more per user than a cloud API. It only pays off at roughly **300–700 listening hours a day**. It also brings operations work: autoscaling, queues, and GPU cold starts measured in minutes.

**Recommended order:**
1. Voices on the phone by default ($0).
2. A hosted Kokoro API for optional cloud voices.
3. Your own DigitalOcean or Hetzner GPU only after usage passes several hundred hours a day.

**Licence traps to avoid:**
- **XTTS-v2** is non-commercial, and a licence can't be bought because Coqui shut down.
- **F5-TTS** weights are non-commercial (CC-BY-NC).
- **Piper** voices each carry their own licence.
- **Kokoro's espeak-ng** pronunciation step is GPLv3. Use Misaki instead.

**Does a cheap alternative gain share?** Partly:
- **Helps:**
  - Near-zero cost of goods lets you undercut the $99–139 tier profitably.
  - Price complaints about Speechify, Voice Dream and NaturalReader are common.
  - A low price converts better and draws fewer billing complaints.
  - There's an unclaimed gap: no family plan from Speechify or ElevenReader.
- **Doesn't help:**
  - "Pay once, not $139/yr" is already a common competitor pitch.
  - Speech Central already sells at $9.99 lifetime.
  - Cheap doesn't get you found. A low price also shrinks what you can spend to acquire a customer, which pushes you further toward organic, community-led growth.

### 10.4 Business models compared

Year-1 illustration using the same **30K installs** as §6. Conversion rates for the cheaper models are assumptions [A]; cheaper offers usually convert better.

| Model | Example | Convert [A] | Year-1 revenue (net of Apple's 15%) | Pros | Cons |
|---|---|---|---|---|---|
| **Premium subscription** ($69/yr) | Speechify, ElevenReader, Audeus | 3–6% | **$53–106K** | Recurring; funds some ads | Head-to-head with the leaders; productivity renewal about 23% |
| **Low-price subscription** ($2.99/mo or $29.99/yr) | None found among TTS readers | 6–10% | **~$46–76K** | Undercuts everyone; less churn pain | Can't fund paid ads (12–24 month payback) |
| **One-time purchase** ($14.99) | Speech Central ($9.99), Voice Dream legacy | 8–12% | **~$31–46K**, not recurring | Accessibility users love it; no billing anger | Revenue stops unless installs keep growing; cloud voices are unaffordable |
| **Free on-device + paid tiers** | ElevenReader, NaturalReader | 2–5% | Depends on tier prices | Wide top of funnel | Free-tier apps convert about 2.1% vs 10.7% for pay-first ([RevenueCat](https://www.revenuecat.com/blog/growth/subscription-app-trends-benchmarks-2026)) |
| **Credits / top-ups** for cloud voices | ReadBack, SpeechGen | n/a | Add-on | Heavy users pay their own voice cost | Users dislike meters |
| **Ads only** | Voice Aloud Reader (MWM), @Voice | n/a | **~$2–12K** (see 10.8) | No paywall | Tiny revenue; clashes with privacy and VoiceOver |
| **Family plan** ($39–49/yr for 5) | Not offered by the leaders | [A] | Add-on | Unclaimed gap | Needs Apple Family Sharing setup |
| **B2B / education licences** | Read&Write (~$2.60/student district-wide), Kurzweil (~$4K/site) | n/a | Lumpy, larger | Real budgets; no Apple fee on invoiced sales | Slow sales; needs an accessibility conformance report (VPAT); DSA headwind |

**Recommended structure, if the tests pass:**
- **Free:** unlimited reading with Apple's on-device voices, including document cleanup. No ads, no account.
- **Plus ($2.99/mo, $24.99/yr, or $39.99 lifetime):** on-device neural voices (Kokoro), exact resume across devices, heading navigation, and a family plan.
- **Cloud voice top-ups (optional):** metered studio voices at cost plus margin.

This is the "honest price, private by design" position. Its ceiling is lower than a $69 subscription's, but it matches what the evidence says people are angry about.

### 10.5 Keeping documents only on the phone (no server storage)

**Short answer: feasible, and a strong privacy story. There is one real engineering catch: the screen lock.**

**How it works end to end:**
1. **Import without our server.**
   - PDFs, Word, text, EPUB and HTML arrive through the Share Sheet or the Files app.
   - For Google Docs, the Docs iOS app's **"Send a copy" → PDF or Word** passes the file straight to the app with no Google sign-in ([TechRepublic](https://www.techrepublic.com/article/how-to-export-a-google-doc-from-your-iphone/)).
   - Optionally, Google sign-in plus a Drive export downloads the file straight to the phone.
2. **Extract and clean the text on the phone:** Apple's PDFKit, plus Vision's document reader in iOS 26 for scans and screenshots.
3. **Generate speech on the phone:** Apple's built-in voices, or Kokoro (about 80–312 MB; 3.3× real time on iPhone 13 Pro, 4–4.5× on 15 Pro, about 17× on 16 Pro via the Neural Engine; [kokoro-ios](https://github.com/mlalma/kokoro-ios), [kokoro-coreml-ane](https://github.com/Jon-Schneider/kokoro-coreml-ane)).
4. **Nothing is stored on a server.** The App Store privacy label can read **"Data Not Collected"** if analytics are also off ([Apple](https://developer.apple.com/app-store/app-privacy-details/)). You never hold client documents. That removes most of the storage cost and much of the legal exposure (ABA Opinion 512 concerns, GDPR processor duties; get a lawyer to confirm).

**The catch: iOS does not let apps use the GPU in the background** ([Apple Developer Forums](https://developer.apple.com/forums/thread/816774)). A Kokoro-style voice running on the GPU stops generating when the screen locks. Sandbook, an existing Kokoro app, says live reading "pauses when the screen locks." Workarounds:
- **Render ahead** while the app is open. A 2-hour document takes about 36 minutes to render on iPhone 13 Pro and about 7 minutes on 16 Pro, then plays locked like any audio file (about 58 MB as AAC).
- **Fall back to Apple's built-in voices when locked.** They keep speaking in the background.
- **Run the model on the Neural Engine.** It might be allowed in the background; this is unverified and needs a prototype.

**Other limits:**
- Apple's on-device language model has only a 4,096-token window, so it can clean a document about 2–3 pages at a time but can't summarize the whole thing.
- Older iPhones are slow, and I found no battery benchmarks.
- Third-party apps can't use Siri's voices. Users must download Apple's "Premium" voices themselves in Settings ([Speech Central](https://speechcentral.net/2026/08/08/why-cant-third-party-apps-use-siri-voices-on-iphone-ipad-and-mac/)).

### 10.6 Google Docs: why it didn't work for you, and the 10-minute limit

**Short answer: your experience is consistent with the evidence. Google's "fix" covers paying users on desktop web only. There is a real ~10-minute cap in Google's speech service, but it's a developer limit, not a documented Docs limit.**

- **"Listen to this tab"** (Aug 2025) is only for paid Workspace plans (Business Standard/Plus, Enterprise, Education add-ons) and Google AI Pro/Ultra subscribers. It is **desktop web only and English only**. On a free Gmail account the menu item doesn't appear ([Google Workspace Updates](https://workspaceupdates.googleblog.com/2025/08/listen-to-documents-using-gemini-google-docs.html), [9to5Google](https://9to5google.com/2025/08/18/google-docs-audio-gemini/)).
- **Audio summaries** (Feb 2026) give a spoken recap of about 3 minutes, not a full reading ([9to5Google](https://9to5google.com/2026/02/12/google-docs-audio-summaries/)).
- **The Google Docs iOS app has no read-aloud.** Its Sept 2026 voice feature is a Gemini *conversation*, not a reader.
- **Docs' older "Speak selection" does nothing unless a screen reader is turned on** ([Google Help](https://support.google.com/docs/answer/6282736)). This is the most likely reason read-aloud "was not working."
- **Where ~10-minute limits do exist:**
  - Google's Gemini speech service caps a single request at about **655 seconds (10.9 min)** and cuts off the rest ([Google Cloud docs](https://docs.cloud.google.com/text-to-speech/docs/gemini-tts)). Any tool built on it that doesn't split long text would stop at about 10 minutes.
  - Free tiers of popular Chrome read-aloud extensions allow only **5–20 minutes a day** (NaturalReader, Read Aloud).
  - Chrome's built-in Google voices cut off after about 15 seconds per chunk unless the text is split ([Chromium bug](https://bugs.chromium.org/p/chromium/issues/detail?id=679437)).
- **Implication:** H1 is somewhat *stronger* than the report first said, for free and mobile Google Docs users. That's a large group, and they are precisely the ones Google's fix leaves out.

### 10.7 Can an iPhone produce two hours of audio?

**Short answer: yes. There is no hardware or OS limit.** Two hours of speech is about 58 MB as AAC, which is trivial. Apple's built-in readers (Speak Screen, Listen to Page, Accessibility Reader) stop because of *bugs*, not a cap: they stop after one page, skip paragraphs, or stop on lock ([Apple Community](https://discussions.apple.com/thread/256209564), [2](https://discussions.apple.com/thread/255489297)).

A dedicated app can play for hours if it does three things:
- turns on the background-audio mode;
- splits text by sentence, which works around known early-stop bugs in Apple's iOS 17 speech engine ([Apple forums](https://developer.apple.com/forums/thread/737685));
- or renders to a file first.

That reliability is precisely the product.

### 10.8 Can ads offset costs? (ELI5)

**Short answer: ads can pay for a free voice, not an expensive one.** People listen with the screen locked, so they rarely see ads. Estimated ad revenue is about **$0.01–0.05 per listening hour**:
- banner ads earn about $0.50 per 1,000 views;
- full-screen ads about $12–14;
- rewarded videos $15–40;
- only about 25–27% of iOS users allow ad tracking ([Adjust](https://www.adjust.com/blog/att-opt-in-rates-2025/)).

Example [A]: 5,000 regular listeners × 4 hours a month × 12 months = 240K listening hours × $0.01–0.05 ≈ **$2–12K a year**.

| Voice | Cost per hour | Ad revenue per hour | Covered by ads? |
|---|---|---|---|
| On-device | $0 | $0.01–0.05 | Yes |
| Self-hosted Kokoro | $0.01–0.04 | $0.01–0.05 | Roughly |
| Cloud API ($15–30 per 1M) | $0.77–1.54 | $0.01–0.05 | **No, 25–100× short** |
| ElevenLabs | $2.60–5.10 | $0.01–0.05 | No |

**The lemonade-stand version:** an ad pays you a few cents. A premium voice hour costs a dollar or more. You'd need about 20–100 rewarded videos per listening hour to break even on a cloud voice, and nobody will watch that many.

Only template apps use ads (Voice Aloud Reader by MWM, @Voice, Easy TTS Reader). The premium players don't, and ads would undercut both the privacy pitch and VoiceOver users. **Recommendation: no ads.** Keep the free tier on-device so it costs nothing to serve.

### 10.9 What "PDF cleanup" means

A PDF isn't really a document. It's closer to a *picture of printed pages*: every word is placed at an x/y position, with no built-in notion of "this is the body text, read it in this order." A reader that simply reads everything on the page produces this:

> "…the committee recommended that the agency. CONFIDENTIAL — DRAFT v3 — Page 12 of 48. Section 4 Findings. Twelve. Increase funding by fifteen percent three. In the second quarter the impor- tant…"

Here's what went wrong in that example, and what "cleanup" does about it:

| Problem | What a naive reader says | Cleanup behaviour |
|---|---|---|
| Running headers, footers, page numbers | "CONFIDENTIAL — DRAFT v3 — Page 12 of 48" on every page, mid-sentence | Detect text that repeats on every page and skip it |
| Footnotes | Reads footnote ³ in the middle of a paragraph, or "three" after a word | Skip footnote markers; read footnotes at the end of the paragraph or section, or offer them on tap |
| Two-column layouts | Jumps across columns line by line | Rebuild the real reading order |
| Tables | "Q1 Q2 Q3 12 15 18 revenue cost…" | Read row by row ("Q1: revenue 12, cost 8…") or announce "table skipped" |
| Hyphenated line breaks | "impor- tant" | Rejoin the word to "important" |
| Headings | Read the same as body text | Pause, change emphasis, add chapter markers for navigation |
| Scans and screenshots | Silence (no text layer) | Recognize the text first (Apple's Vision reader or OCR) |

Word, Google Docs (exported as Word), plain text, EPUB and web pages already carry their structure, so they need little cleanup. PDFs and scans are where readers fail, and professional briefings are mostly PDFs.

### 10.10 What changes in the recommendation

| Before | After this addendum |
|---|---|
| Price at $69/yr with metered cloud voices | **Lead with a cheaper, private-by-design model:** free on-device reading, then $2.99/mo, $24.99/yr or a lifetime option for neural on-device voices, plus a family plan. Cloud voices only as optional top-ups. |
| Google Docs "fixed" by Google | **Only for paid desktop-web users.** Free and mobile Docs users are unserved. Import via "Send a copy" from the Docs app. |
| On-device voices as a differentiator | **Now table stakes** (Speechify, Dec 2025). The differentiator is *no account, no upload, no server* plus accurate document structure. |
| Server costs a concern | **Keep servers out of the reading path.** Use a hosted Kokoro API only for optional cloud voices, and self-host on DigitalOcean only above ~300–700 listening hours a day. |
| Verdict: test before building | **Unchanged**, but the downside is smaller. A $0-cost-of-goods, no-ads app can break even with a few hundred paying users and doesn't need venture funding. Distribution is still the binding constraint. |

**One new experiment:** add a price test to Experiment 4, comparing a $2.99/mo subscription, a $24.99/yr plan and a $39.99 lifetime option against $69/yr on the same landing page.

**New engineering spike:** check whether Kokoro can generate speech on the Neural Engine while the screen is locked. If it can't, ship "render ahead" and fall back to Apple's voices when locked.

---

## Appendices

### Appendix A: Key sources (all inline above; main ones listed)
- Competitors: [Speechify](https://speechify.com/), [ElevenReader pricing](https://elevenreader.io/blog/best-pricing-more-value), [Audeus](https://www.audeus.com/), [Listening](https://www.listening.com/), [Speech Central](https://speechcentral.net/), [Peech](https://apps.apple.com/us/app/peech-text-to-speech-reader/id1429704005), [NaturalReader](https://help.naturalreaders.com/en/articles/8854700-plans-pricing-personal-version), [Audioread](https://audioread.com/pricing), [Perkins on Voice Dream](https://www.perkins.org/resource/voice-dream-reader-subscription-controversy/)
- Platforms: [Google Docs Listen](https://workspaceupdates.googleblog.com/2025/08/listen-to-documents-using-gemini-google-docs.html), [Accessibility Reader](https://support.apple.com/guide/iphone/read-listen-text-apps-accessibility-reader-iph406a46ab8/ios), [WWDC26 session](https://developer.apple.com/videos/play/wwdc2026/219/), [NotebookLM](https://www.macrumors.com/2025/05/20/google-releases-notebooklm-app-for-ios-and-android/), [Google restricted scopes](https://developers.google.com/identity/protocols/oauth2/production-readiness/restricted-scope-verification), [App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)
- Voice of customer: [Apple Community 256013629](https://discussions.apple.com/thread/256013629), [256044481](https://discussions.apple.com/thread/256044481), [254777900](https://discussions.apple.com/thread/254777900), [Zotero](https://forums.zotero.org/discussion/124826/ios-ipados-spoken-content-not-continuing-to-next-page-instead-goes-in-circles), [Adobe](https://community.adobe.com/t5/acrobat-reader-mobile-discussions/text-to-speech-function-for-acrobat-reader-dc-with-option-to-omit-reading-footnotes/td-p/11165366), [Trustpilot Speechify](https://www.trustpilot.com/review/speechify.com), [BBB](https://www.bbb.org/us/fl/miami/profile/education/speechify-inc-0633-92046942/complaints), [mjtsai](https://mjtsai.com/blog/2024/04/08/voice-dream-reader-switches-to-subscriptions/), [AppleVis](https://www.applevis.com/comment/146280)
- Economics: [RevenueCat 2026](https://www.revenuecat.com/state-of-subscription-apps), [Google Cloud TTS](https://cloud.google.com/text-to-speech/pricing), [OpenAI TTS](https://developers.openai.com/api/docs/models/gpt-4o-mini-tts), [ElevenLabs API](https://elevenlabs.io/pricing/api), [Kokoro-82M](https://huggingface.co/hexgrad/Kokoro-82M), [Apple Small Business Program](https://developer.apple.com/app-store/small-business-program/)
- Market: [TechCrunch ElevenLabs](https://techcrunch.com/2026/02/04/elevenlabs-raises-500m-from-sequioia-at-a-11-billion-valuation/), [Sensor Tower Speechify](https://app.sensortower.com/overview/1209815023?country=US), [Edison Infinite Dial 2026](https://www.edisonresearch.com/the-infinite-dial-2026/), [APA / Publishers Weekly](https://www.publishersweekly.com/pw/by-topic/industry-news/audio-books/article/100588-u-s-audiobook-sales-up-9-in-2025-reaches-2-43-billion.html), [CDC ADHD](https://www.cdc.gov/mmwr/volumes/73/wr/mm7340a1.htm), [CDC vision](https://www.cdc.gov/vision-health-data/prevalence-estimates/vision-loss-prevalence.html)

### Appendix B: Extended quote database
[raw/voice-quotes.md](../raw/voice-quotes.md) has 58 items labeled [V] verbatim, [P] paraphrase and [T] thread title.

### Appendix C: Competitor details
[raw/competitor-data.md](../raw/competitor-data.md)

### Appendix D: Trend, pricing, platform and PM detail
[raw/trends-data.md](../raw/trends-data.md) · [raw/pricing-data.md](../raw/pricing-data.md) · [raw/local-context.md](../raw/local-context.md) · [raw/communities-found.md](../raw/communities-found.md) · [raw/pm-analysis.md](../raw/pm-analysis.md)
