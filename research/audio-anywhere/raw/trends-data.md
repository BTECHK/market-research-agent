# Trends Data: Audio Anywhere (consumer TTS / long-document listening)

Researched 2026-09-25 by the Trend Detector. Market: US-first, iOS.

**Method limits (read first):** Google Trends (trends.google.com), Wikipedia, speechify.com, stripe.com and dealroom.co were all blocked by the network egress proxy, so I could not pull any Google Trends time series. The search-interest section below is inferred from proxy signals (app-store ranks, product launches, media volume) and is marked **UNVERIFIED**. Re-run Trends manually before using any direction claim in a deck.

---

## Search Interest Trends (UNVERIFIED: no direct Google Trends access)

| Keyword | Trend (12mo) | Current vs Peak | Evidence / confidence |
|---|---|---|---|
| text to speech app | Likely stable to rising | Unknown | Evergreen query, heavily SEO-farmed by vendors (ElevenReader, Speechify, Mira, CastReader, Readox all publish "best TTS app 2026" posts). Low confidence. |
| speechify | Likely stable | Unknown | Heavy paid acquisition (CEO says the company tests about 1,000–1,300 AI-generated ads a day), so branded search is partly ad-driven. Low confidence. |
| read aloud | Likely rising | Unknown | Platform features now carry this label: Google Docs "Listen to this tab" (Aug 2025), Edge Read Aloud, Safari Listen to Page. Low confidence. |
| elevenreader | Rising | Probably near peak after the May 2026 audiobook launch | #2–3 in Books & Reference on Google Play, about 82–90k downloads a month, 5M+ installs (AppBrain/Similarweb). Medium confidence. |

**Action:** Check Google Trends manually for 5 years, US, comparing "speechify", "elevenreader", "text to speech", "read aloud" and "notebooklm". Also check the September back-to-school spike, which is a likely seasonal pattern because student use is heavy.

---

## Market Size: TTS (and how good the numbers are)

| Source | 2025 size | CAGR | Quality |
|---|---|---|---|
| GM Insights | $4.8B, rising to $35.3B by 2035 | ~22% | LOW. Report mill; a 7x forecast with no consumer/enterprise split |
| Mordor / MarketsandMarkets / Technavio / Polaris / MRFR / Expert MR | $3.9–4.9B | 3.7% to 23.3% | LOW. The same year's CAGR ranges 6x across firms, which is a sign the numbers are not measured |
| Credence | $3.5B (2024), rising to $28.5B by 2032 | — | LOW |

**Verdict:** Do not cite any TTS "market size". These reports mix enterprise APIs, IVR, automotive and accessibility into one number. Better anchors:
- **ElevenLabs:** about $500M ARR (reported early 2026), $11B valuation (Series D, Feb 2026), with a secondary sale reportedly targeting $22B. This is credible (TechCrunch, CNBC, company blog), but most of its revenue is API/creator/agents, not consumer reading.
- **Speechify:** claims 50–60M users and 4.5 years of profitability (company/20VC). The revenue numbers are **low-confidence**. Latka's "$17.6M ARR / $100M valuation" and Tracxn's "$768K seed Oct 2025" look like scraped or garbage data. No audited or press-verified revenue exists. Treat Speechify's revenue as unknown.
- **Fish Audio:** $52M seed (Jul 2026) on $21M ARR, which shows investor appetite for voice models.
- **US audiobooks (APA, credible):** $2.43B in 2025, up 9% (2024: $2.22B). 58% of US adults have ever listened.

Sources: gminsights.com/industry-analysis/text-to-speech-market ; mordorintelligence.com/industry-reports/text-to-speech-market ; technavio.com/report/text-to-speech-market-industry-analysis ; polarismarketresearch.com/industry-analysis/text-to-speech-market ; credenceresearch.com/report/text-to-speech-market ; techcrunch.com/2026/02/04/elevenlabs-raises-500m-from-sequioia-at-a-11-billion-valuation/ ; cnbc.com/2026/02/04/nvidia-backed-ai-startup-elevenlabs-11-billion-valuation.html ; techtimes.com/articles/319752/20260705/elevenlabs-valuation-doubles-22-billion-voice-cloning-reaches-its-biggest-test.htm ; getlatka.com/companies/speechify.com (low quality) ; techcrunch.com/2026/07/28/fish-audio-raises-50m-seed-to-build-ai-voice-models-for-creators-and-enterprises/

---

## Accessibility Demand Base (credible sources)

- **Dyslexia:** the IDA says "perhaps as many as 15–20% of the population" have *some symptoms*. This is an upper bound on symptoms, not diagnosis, so don't use it as a TAM. https://dyslexiaida.org/dyslexia-basics/
- **Adult ADHD:** 6.0% of US adults, about 15.5M, have a current diagnosis. About half were diagnosed in adulthood, and 84.5% are under 50 (CDC MMWR, Oct 2024). https://www.cdc.gov/mmwr/volumes/73/wr/mm7340a1.htm
- **Vision:** CDC VEHSS 2024 estimates 32.17M Americans with any presenting visual-acuity loss, and 7.15M with best-corrected loss (the real low-vision core). https://www.cdc.gov/vision-health-data/prevalence-estimates/vision-loss-prevalence.html
- **What this means:** The accessibility segment is real but already served. Apple's free Accessibility Reader and Spoken Content, Voice Dream, and Speechify (founded by a dyslexic founder, with an Apple Design Award in 2025) all serve it. The Voice Dream backlash in 2024 showed this segment is loud, organised (AppleVis, Perkins) and hostile to subscriptions.

---

## Audiobook / Listening Behaviour

- **Edison Infinite Dial 2026:** 37% of Americans aged 12+ listened to an audiobook in the past year, and 51% of monthly podcast listeners did. Edison also studied AI narration: 61% of those who heard the AI version thought a human narrated it, and purchase intent was 54% for AI vs. 56% for human. https://www.edisonresearch.com/the-infinite-dial-2026/ ; https://www.insideradio.com/free/edison-study-ai-audiobook-narration-clears-consumer-hurdle/article_1f33b1c0-c1c4-47c1-9431-9a959b898cf3.html
- **APA:** AI-narrated titles were only 0.03% of 2025 sales, and willingness to try AI narration *fell* from 70% to 61%. Audio-first titles grew 50%. https://www.publishersweekly.com/pw/by-topic/industry-news/audio-books/article/100588-u-s-audiobook-sales-up-9-in-2025-reaches-2-43-billion.html ; https://www.infodocket.com/2026/06/05/audio-publishers-association-reports-audiobook-sales-jump-9-to-2-43-billion/
- **Mixed signal:** The listening habit is growing and AI voice quality now passes blind tests. But consumers still carry an "AI voice" stigma for *content they pay for*. That stigma matters less for the user's *own* documents, which favours this use case.

---

## Industry Signals: Funding, M&A, Exits

| Date | Event | Signal |
|---|---|---|
| 2023 to Apr 2024 | Applause Group bought Voice Dream Reader, forced a $59.99–79.99/yr subscription, then backed down after a blind-community revolt | Bearish for monetizing accessibility users. Bullish for the idea that there is a gap with loyal users. https://www.perkins.org/resource/voice-dream-reader-subscription-controversy/ ; https://sixcolors.com/link/2024/04/another-app-switches-to-a-subscription-model/ |
| Oct–Nov 2024 | ElevenLabs acqui-hired Omnivore. The app was shut down with 14 days to export, and the founders moved to ElevenReader | The strongest player is buying read-later talent to fold it into a TTS reader. https://www.creativerly.com/the-exit-us-of-omnivore-from-open-source-to-ai-vc-money/ |
| Jul 8, 2025 | Mozilla shut down Pocket, with data deleted Oct 8, 2025 | Read-later as a standalone business is weak. Displaced users are being courted by ElevenReader ("best Pocket alternatives for read aloud"). https://www.macrumors.com/2025/05/22/mozilla-pocket-discontinued/ ; https://elevenreader.io/blog/best-pocket-alternatives-for-read-aloud |
| Feb 2026 | ElevenLabs Series D: $500M at $11B | A well-funded incumbent with its own consumer reader |
| May 2026 | ElevenReader Ultra: 200k human-narrated titles (HarperCollins, Blackstone), $11/mo or $99/yr for 20 hours | ElevenReader is moving *up* into audiobooks and away from pure document reading. That could leave a focused "work documents" niche less contested, or it could mean the bundle wins. https://www.publishersweekly.com/pw/by-topic/industry-news/publisher-news/article/100500-elevenlabs-adds-200k-audiobooks-to-stream-offers-premium-tier.html ; https://elevenlabs.io/blog/elevenreader-launches-premium-audiobooks |
| Nov 2025 and Aug 2026 | Wispr (dictation): $700M valuation, then $280M at $2B | The founder's analogy holds: a voice-input app earns a unicorn valuation. There is no equivalent venture winner in voice *output* for reading besides ElevenLabs. https://techcrunch.com/2026/08/17/wispr-raises-280m-at-2b-valuation-as-it-looks-beyond-dictation/ |
| May 2026 | Speechify SIMBA 3.0 reaches the Artificial Analysis top 10; Speechify expands into Windows on-device TTS and voice agents | The incumbent is diversifying into B2B and agents |
| Ongoing | Voice Dream is still shipping (v5.5.8, Sept 2026) with AI Summary and Chat | Legacy player adding AI features |

---

## Platform Threats (the biggest risk)

- **Apple:** Safari *Listen to Page*. **Accessibility Reader** in iOS 26 is a systemwide reading mode that works in *any app*, is triggered by triple-click, and has playback with autoplay. That means "read anything from anywhere on your phone" (MVP2) is **already a free OS feature**, although it uses Apple's older voices. iOS 27 (WWDC Jun 8, 2026) adds a Gemini-derived foundation model and Siri that can "read a document", and brings Apple Intelligence into VoiceOver. Voice quality could close the gap within 12–18 months. https://support.apple.com/en-ca/guide/iphone/iph406a46ab8/ios ; https://www.engadget.com/mobile/smartphones/how-to-use-accessibility-reader-on-apple-devices-212231319.html ; https://www.bgr.com/2177707/cool-new-ios-27-accessibility-features-look-forward-to-fall/ ; https://www.macrumors.com/roundup/ios-27/
- **Google:** Docs Tools > Audio > "Listen to this tab" is Gemini TTS with natural voices, a player and speed control, shipped Aug 2025. It is paywalled to Workspace and Google AI plans. Audio summaries arrived Feb 2026. **This directly targets the MVP1 Google Docs use case.** https://workspaceupdates.googleblog.com/2025/08/listen-to-documents-using-gemini-google-docs.html ; https://workspaceupdates.googleblog.com/2026/02/listen-to-audio-summaries-in-google-docs.html
- **NotebookLM Audio Overviews:** these *summarize* documents into podcast-style conversations rather than reading them verbatim. The category is shifting from "listen to the whole thing" to "listen to the gist", which is a substitute for many knowledge workers. (Gitnux and Zipdo usage stats are junk: one claims "167% of notebooks". Ignore them.)
- **Microsoft:** Edge Read Aloud is faster, and Copilot can generate podcasts from tabs. But the consumer Copilot Podcasts feature was **retired Aug 18, 2026**, a hint that AI-podcast novelty fades. https://www.windowscentral.com/software-apps/microsoft-edge-just-got-two-new-ai-features-and-theyre-actually-useful ; https://support.microsoft.com/en-gb/topic/podcasts-in-microsoft-copilot-11c7e451-e810-4a82-b619-f96d9badc0a8
- **ChatGPT:** Read Aloud plays a single reply in a stock voice, and Voice Mode was removed from the macOS app in Jan 2026. Claude has no read-aloud button. A cottage industry of Chrome extensions fills this gap. Chatbots are not yet long-document readers.

---

## Cost Curve of Neural TTS (enabler)

- Mainstream neural APIs cost about $12–22 per 1M characters (OpenAI gpt-4o-mini-tts about $15/M, Google Neural2 $16/M, Chirp 3 HD $30/M). ElevenLabs costs about $50/M for Flash and about $100/M for v3. https://texttolab.com/blog/openai-tts-pricing ; https://texttolab.com/blog/google-cloud-tts-pricing ; https://inworld.ai/resources/tts-api-pricing-comparison
- **Kokoro-82M** (Apache 2.0, Jan 2025) runs at about 6x real-time on a laptop CPU and costs under $1 per 1M characters when served. It can run on-device. https://huggingface.co/hexgrad/Kokoro-82M ; https://github.com/hexgrad/kokoro
- **Unit economics:** A 20-page brief is about 60k characters. That costs about $0.90 on OpenAI, about $6 on ElevenLabs v3, and about $0 on-device with Kokoro. **A subscription is viable on cost. But voice quality is now commoditized, so it is not a moat.** Any team, including Apple and Google, can match it.

---

## Regulatory Tailwinds (weak for B2C)

- **European Accessibility Act**, enforceable from Jun 28, 2025: e-books and e-readers must support TTS, with a grace period to 2030 for books already on the market. This is EU-only and binds publishers and hardware makers, not a US consumer app. It helps normalise TTS rather than drive demand. https://www.traverssmith.com/knowledge/knowledge-container/a-new-milestone-for-accessibility-the-european-accessibility-act-now-applies/ ; https://nipi.care/?page_id=62
- **ADA Title II web rule:** requires WCAG 2.1 AA for state and local governments and public universities. DOJ **delayed the deadlines by one year** (interim final rule, Apr 20, 2026) to Apr 26, 2027 for large entities and 2028 for small ones. This matters mainly for B2B/edu procurement, and the timeline has now slipped. https://www.federalregister.gov/documents/2026/04/20/2026-07663/extension-of-compliance-dates-for-nondiscrimination-on-the-basis-of-disability-accessibility-of-web ; https://upcea.edu/doj-extends-accessibility-deadline-to-april-2027-policy-matters-april-2026/

---

## Timing Analysis

**Seasonal:** Student and edu demand probably spikes in Aug–Sep and Jan (unverified; check Trends).

**Upcoming events:**

| Event | Date | Implication |
|---|---|---|
| iOS 27 public release | Fall 2026 (now) | Audit how good Siri's "read document" and Accessibility Reader voices are before building |
| ADA Title II deadline | Apr 26, 2027 | Possible edu/B2B wedge |
| ElevenLabs IPO talk | 2026–27 | More consumer marketing spend from ElevenReader |

**Market Timing Assessment: Is now a good time? MIXED, leaning toward the window closing for a broad "read anything" app.**

- **Opening:** Voice quality has passed the blind-test threshold (Edison). Costs have collapsed and on-device TTS is possible. Read-later incumbents have died (Pocket, Omnivore), which displaced users. ElevenReader is drifting toward audiobook retail. Voice AI is a hot category for investors (Wispr, Fish, ElevenLabs).
- **Closing:** Apple (Accessibility Reader, Listen to Page, Gemini-powered Siri) and Google (Docs Listen, audio summaries, NotebookLM) are shipping free or bundled versions of both MVP1 (Google Docs) and MVP2 (read anything on the phone). ElevenReader already offers 10 free hours a month with more than 1,000 voices, and Speechify has 50M+ users and heavy ad spend. There is no "old way vs. new way" shift left for a newcomer to own. That shift already happened in 2023–25, and ElevenLabs and Speechify captured it.

## Momentum Summary

**Overall trend:** The category is growing. The opportunity for new independent entrants is shrinking.

**Key signals:**
1. The ElevenLabs $11B to $22B valuation and the ElevenReader Ultra launch: **bearish** for a newcomer, because a funded incumbent is bundling.
2. iOS 26 Accessibility Reader and Google Docs Listen: **bearish**. The MVP1 and MVP2 surfaces are commoditized by the platforms.
3. The TTS cost collapse and Kokoro on-device: **bullish** on cost, **bearish** on defensibility.
4. The Pocket and Omnivore deaths and the Voice Dream backlash: **mixed**. There are orphaned users, but they resist paying.
5. The Wispr $2B raise: **bullish** as proof that a narrowly focused voice productivity tool can win despite OS-level dictation. This is the best counter-argument to the platform threat.

**Timing recommendation:** Build only as a narrow, fast wedge within 6–12 months, before iOS 27/28 voice upgrades land. That wedge is long work documents, reliable resume and position sync across devices, and fidelity for structure (tables, footnotes, headings) that built-in readers mangle. Do not build a general "listen to anything" app. That market already belongs to Apple, Google, ElevenReader and Speechify.

**Risks:** (1) Apple ships premium neural voices plus position memory in Accessibility Reader, which would wipe out the wedge overnight. (2) "Summaries not full reads" (NotebookLM, Docs audio summaries) shrinks the verbatim-listening use case for knowledge workers.

## Sources
All URLs are inline above. Also: https://www.audiopub.org/surveys ; https://bookriot.com/audio-publishers-association-consumer-survey-2025/ ; https://www.techtimes.com/articles/317030/20260522/elevenreader-lands-200000-human-narrated-titles-11-subscription-takes-aim-audible.htm ; https://www.similarweb.com/app/google/io.elevenlabs.readerapp/ ; https://www.appbrain.com/app/elevenlabs-reader-ai-audio/io.elevenlabs.readerapp ; https://mjtsai.com/blog/2024/04/08/voice-dream-reader-switches-to-subscriptions/ ; https://www.applevis.com/forum/ios-ipados/applause-has-backed-down-purchased-voice-dream-features-will-stay ; https://9to5google.com/2025/08/18/google-docs-audio-gemini/ ; https://mcmw.abilitynet.org.uk/how-to-listen-to-web-pages-in-ios-26-on-your-iphone-or-ipad ; https://techcrunch.com/2025/02/20/spotify-partners-with-elevenlabs-to-expand-its-library-of-ai-narrated-audiobooks/ ; https://castreader.com/listen-to-chatgpt ; https://chadd.org/about-adhd/general-prevalence-adults/
