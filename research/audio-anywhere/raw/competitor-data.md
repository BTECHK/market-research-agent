# Competitor Data: Audio Anywhere (AI long-document read-aloud, iOS-first)

**Compiled:** 2026-09-25 | **Agent:** Competitor Profiler | **Depth:** Deep dive (cut short by tooling; see Limitations)

## Research Limitations (read first)

- **WebFetch was blocked for every domain tried** (apps.apple.com, elevenreader.io, wikipedia, checkthat.ai, speedreadinglounge). Everything below comes from **web-search result snippets**, not full pages I read myself. Treat single-source numbers as directional.
- Direct App Store lookups were blocked, so **App Store rating counts are mostly unverified**. Where a count is given, the source is named.
- The session's **web-search budget ran out (200/200, shared across agents)** before I could cover these items: Wondercraft, Podcastle, Talkie/ReadAloud, Matter/Instapaper pricing, Microsoft Word/Edge on iOS, Perplexity's current read-aloud, the "Books Aloud AI Reader" and "AI Reader" apps, Speechify's App Store rating count, NaturalReader's App Store rating, and a wider App Store keyword sweep. These are **open gaps**, not proof that nothing is there.
- Revenue figures for private companies are third-party estimates (Latka, Sensor Tower), and they disagree with each other. See the Speechify section.

---

## Competitor Overview

### Direct Competitors (standalone AI read-aloud apps for documents)

#### 1. Speechify: category leader

**Background:** Founded in 2017 by Cliff Weitzman, who built it for his own dyslexia. HQ Miami, about 160 employees. Weitzman says the company has been **profitable for 4.5 consecutive years** and is entering a "new hyper-growth phase." Its growth engine is paid acquisition: it tests **about 1,300 AI-generated ads a day** and spends **$500K a month on creative testing**. It says inference costs are down to "single-digit dollars per million characters" (20VC interview).
- https://finance.biggo.com/news/82a0b4613f50dfa4
- https://speechify.com/blog/cliff-weitzman-speechify-20vc-lessons/
- https://app.dealroom.co/news/note/1-000-ai-ads-a-day-and-tokens-over-salaries-inside-speechify-s-playbook-for-owning-the-voice-ai-market

**Scale claims:** "50M+" and later "60M+ users." It claims "1.1 million five-star ratings across platforms" and calls itself the "#1 rated TTS app on the App Store." iOS rating is **4.7** (third-party review sites; I could not verify the count).
- https://speechify.com/ ; https://www.fahimai.com/speechify

**Revenue: the estimates conflict**
- Latka: **$17.6M ARR (2025)**, $100M valuation (2024). This is probably a large understatement.
- Sensor Tower snippet: about **500K downloads and about $2M revenue in one month, US App Store only** (month not stated). That annualizes to roughly $24M from US iOS alone, before web, Chrome extension, Android and other countries.
- Takeaway: Speechify is plausibly a **$30M–$100M+ revenue business**, profitable, with a heavy paid-acquisition machine. Funding was mostly bootstrapped. Crunchbase and Tracxn show only small seed rounds.
- https://getlatka.com/companies/speechify.com ; https://app.sensortower.com/overview/1209815023?country=US ; https://www.crunchbase.com/organization/speechify

**Offering:**
| Aspect | Details |
|---|---|
| Platforms | iOS, Android, web, Chrome/Edge extension, Mac; Google Workspace integration |
| Import | PDF, Google Drive/Google Docs (iOS and web), web pages, camera OCR scan, ePub |
| Voices | 200+ voices, 60+ languages, celebrity voices, up to 5x speed |
| Offline | Yes (Premium) |
| Sync/progress | Cross-platform library sync |
| Other | AI summaries, AI chat, voice typing, "Voice AI assistant" |

**Pricing:** Free tier (robotic voices, limited). **Premium $139/yr, annual only, no monthly plan** (raised from about $120 to $139). 7-day refund window. Pushes free-trial-to-annual conversion.
- https://www.fahimai.com/speechify ; https://texttolab.com/blog/speechify-alternatives ; https://fish.audio/vs/pricing/speechify/

**Customer sentiment:**
- *Love:* broad format support, OCR, speed, sync, dyslexia/ADHD positioning.
- *Complaints:*
  - Billing is the #1 theme. Users feel "forced" into a trial that auto-renews at $139.99, find refunds hard, and "get steep discounts only after trying to cancel." Trustpilot has about 5,600 reviews. https://ie.trustpilot.com/review/speechify.com ; https://checkthat.ai/brands/speechify/reviews
  - Reliability on long content: it "stops reading after each paragraph if not on the screen," "stops the second the iPad screen sleeps," "if you select the wrong thing, it loses the page and goes back to the beginning of the book," and it "reads one sentence at a time and completely stops." https://ashishdoneriya.medium.com/bugs-in-speechify-f25852241cca ; https://justuseapp.com/en/app/1209815023/speechify-audio-text-reader/problems
  - Google Drive: "it takes hours before I can successfully upload the document… supposed to link to Google Drive, but only does so maybe one try in 10." PDFs: it "adds arbitrary pauses… at the end of each print line in a paragraph." (App Store reviews, via search snippet) https://apps.apple.com/us/app/speechify-text-to-speech-pdf/id1209815023?see-all=reviews
  - Voice quality is seen as behind ElevenReader: "ElevenReader… blows Speechify away." https://texttolab.com/blog/speechify-alternatives

**Strengths:** distribution and brand (it owns "text to speech" SEO and App Store search), profitability, ad-creative machine, most complete feature set.
**Weaknesses:** trust damaged by predatory-feeling billing, annual-only pricing, bugs on long content and PDF layout, flaky Google Drive import, feature bloat.
**Gap:** a trustworthy, fairly billed, *reliable-on-long-documents* alternative. But Speechify already *claims* every feature in the MVP.

---

#### 2. ElevenReader (ElevenLabs): the voice-quality leader, heavily subsidized

**Background:** Consumer app from ElevenLabs, which has **$500M+ ARR (April 2026)**, a **$11B valuation**, and a **$500M Series D led by Sequoia (Feb 2026)**, with $881M raised in total. The reader app is a consumer showcase and data flywheel for a company whose main business is enterprise and API.
- https://techcrunch.com/2026/02/04/elevenlabs-raises-500m-from-sequioia-at-a-11-billion-valuation/ ; https://elevenlabs.io/blog/500m-arr-and-new-investors

**Scale:** about **5M installs**. iOS rating **4.7–4.72 from about 9.2K ratings** (appbrain snippet). The web property had about 785K monthly visitors (April 2026).
- https://www.appbrain.com/appstore/elevenreader-read-books-aloud/ios-6479373050 ; https://wifitalents.com/elevenlabs-statistics/

**Offering:** PDF, ePub, DOCX, Markdown, TXT, links, image scan, paste. 1,000+ voices, 32+ languages. Syncs across iOS, Android and web. Offline downloads on Ultra. "GenFM" podcast-style summaries. A library of 200K+ AI-narrated audiobooks. Kindle read-aloud positioning. Upload limit is **500 pages** per document.
**Google Docs:** no native in-place Google Docs integration found. Reading a Google Doc "often means copy-pasting." https://castreader.com/blog/elevenreader-review-2026

**Pricing (2025–26):** They **cut prices 50%**. The free tier gives **10 hours a month** of top-quality audio. **Ultra is $11/mo or $99/yr** with unlimited listening, and annual buyers get a second year free. Students get a year of Ultra free.
- https://elevenreader.io/blog/best-pricing-more-value ; https://elevenreader.io/students ; https://help.elevenlabs.io/hc/en-us/articles/36191061815697-How-does-the-Ultra-plan-work

**Sentiment:**
- *Love:* best-in-class voices. People keep using it despite bugs "because of its high-quality voice."
- *Complaints:* "**loses its place** and I have to locate where I last was." "Don't want to sink a few hours into a text only to have ElevenReader freeze, without even having a way to restart from the right point." "Fails constantly and stops in the middle of a text." A PDF upload "just presents the file names of images." Android is rougher. Plan and hours limits confuse people. https://justuseapp.com/en/app/6479373050/elevenlabs-reader-ai-audio/reviews ; https://discuss.grapheneos.org/d/18980-any-workarounds-for-11reader-not-working

**Strategic read:** This is the biggest threat. A better-funded company with the best voice model is giving away 10 free hours a month and charging $99/yr for unlimited. **A startup cannot beat it on voice quality or price.** Its weak spots are exactly the founder's pain: reliability and position-keeping on long docs, plus no in-place Google Docs import.

---

#### 3. NaturalReader, now in the same corporate family as Voice Dream

**Background:** Long-time desktop and web TTS vendor (NaturalSoft, Vancouver). Voice Dream appears to have been folded into the same family: the App Store listing id496177674 is now titled "**Voice Dream – Natural Reader**." https://apps.apple.com/us/app/voice-dream-natural-reader/id496177674 ; https://www.yaps.ai/blog/voice-dream-reader-alternative
**Platforms:** web, Windows/Mac desktop, iOS, Android, Chrome extension. The iOS app can import from Google Drive, Dropbox and OneDrive.
**Pricing:** free tier (about 20 min/day of premium voices). Personal plans run **$9.92–$25.90/mo, about $99.50–$119/yr**. Commercial plans run $16.50–$49/mo. https://help.naturalreaders.com/en/articles/8854700-plans-pricing-personal-version ; https://texttolab.com/blog/naturalreader-pricing
**Sentiment:** "document workhorse," with a pronunciation editor that technical readers like. Complaints: long texts load slowly, voices sound "flat on long documents," the mobile app is "narrower than the web app," and Google Drive integration is "basic… lacks deeper workflow integrations like syncing reading progress." **Trustpilot 1.6/5 (55 reviews, 84% one-star).** https://www.trustpilot.com/review/www.naturalreaders.com ; https://castreader.com/blog/naturalreader-review-2026
**App Store rating:** not verified.

---

#### 4. Voice Dream Reader: the accessibility incumbent, weakened by the subscription controversy

**History:** Indie developer Winston Chen sold it to **Applause Group in 2023**. The blind community learned of the sale secondhand. In 2024 Applause moved new users to **$59.99/yr** (later reported at about **$79.99/yr on iOS, $49.99/yr on Mac**) and announced that one-time purchasers would **lose features on May 1, 2024 unless they subscribed**. That was widely called a breach of App Store guidelines. After backlash (AppleVis, Jonathan Mosen, Living Blindfully, Perkins), **Applause reversed course**: legacy buyers keep their existing features, and new features are subscription-only. The app is still maintained (updated June 2026) and has been rebranded "Voice Dream – Natural Reader."
- https://www.perkins.org/resource/voice-dream-reader-subscription-controversy/ ; https://mosen.org/voicedream/ ; https://www.applevis.com/forum/ios-ipados/applause-has-backed-down-purchased-voice-dream-features-will-stay ; https://mjtsai.com/blog/2024/04/08/voice-dream-reader-switches-to-subscriptions/ ; https://vi.ie/voice-dream-readers-subscription-drama-explained-is-the-bubble-going-to-burst/ ; https://speechcentral.net/2023/08/22/applause-group-and-voice-dream-reader-a-shift-in-vision/
**Strengths:** deep accessibility features, offline, strong bookmarks and position handling. It was historically *the* app for blind and dyslexic power users.
**Weaknesses:** community trust is damaged, pricing moved from one-time to about $80/yr, and it is legacy technology.
**Signal:** (a) This segment **will pay** but is **hostile to subscriptions it sees as unfair**. (b) Trust and ownership matter a lot to accessibility users. That opening has already been taken by Speech Central (below).

---

#### 5. Speech Central: the indie accessibility challenger

iOS, Mac, Windows and Android. **Pro is a one-time $9.99.** It is **free for VoiceOver/TalkBack users** and free in schools. It has 70+ customization options, reads PDFs, ePubs, web and documents, and has an "AI Voice Reader" rebrand. Its developer broke the Voice Dream subscription news and picked up users who left. https://speechcentral.net/ ; https://www.applevis.com/apps/ios/productivity/speech-central-ai-voice-reader ; https://www.neilsquiresolutions.ca/news/speech-central-ai-voice-reader/
**Signal:** a low-price, one-time-purchase competitor already serves the accessibility niche.

---

#### 6. Peech (iOS)

Launched in 2021. Claims **1M+ users**. OCR, PDFs, eBooks, web, 60+ languages. Several subscription tiers appear in snippets ($99/yr, $69.99/yr, $6.99/week, $19.99/mo), which suggests aggressive paywall A/B testing. Some reviews call it "by far the most accurate and reliable of all of those tested, including Speechify, Natural Reader, and Eleven Reader." Complaints: limited voice choice, minor bugs. https://apps.apple.com/us/app/peech-text-to-speech-reader/id1429704005 ; https://ai-review.com/text-to-speech/getpeech/ ; https://beingpaperless.com/peech-text-to-speech-reader-for-ipad-full-review/

#### 7. Audeus

A PDF and document reader with read-along highlighting, notes and chat. **Explicitly markets Google Docs ("Read Aloud PDFs, Gdocs & more")** and "automatically saves your place, so you can pause and resume… without losing your spot." iOS, Android and web. **Pro $19/mo or $119/yr**, with 50% off for students. Funding unknown. https://www.audeus.com/ ; https://www.audeus.com/pricing ; https://www.audeus.com/text-to-speech-ios
**Signal:** **The founder's exact MVP positioning (Google Docs + PDF + saved progress, iOS) is already on a competitor's homepage.**

#### 8. Listening.com: academic niche

Built for research papers. It understands paper structure and skips citations and watermarks. Sentence bookmarks, a "note the last 2 sentences" button, 20+ voices. About **$4.92/mo billed yearly (about $59/yr)**, 3-day trial. iOS, Android and web. https://www.listening.com/ ; https://www.listening.com/pricing ; https://www.listening.com/features
**Signal:** vertical specialization works. A focused niche can hold users against the generalists.

#### 9. Audioread (formerly Audiblogs)

Turns articles, PDFs, Word docs, email forwards and RSS into a **private podcast feed**, so you listen in your existing podcast app. Web, extension, iOS Shortcut, Android. Pro from **$4.99/mo**. Up to 100K characters per document on paid plans. It was Product Hunt #1 product of the month. https://audioread.com/pricing ; https://www.producthunt.com/products/audioread-formerly-audiblogs/reviews
**Signal:** "Audiobook-style progress" is solved for free by podcast players, which already save position, sync across devices and play offline. That is a cheap way to satisfy the progress-saving need.

#### 10. @Voice Aloud Reader (Hyperionics, Android) and "Voice Aloud Reader" (MWM, iOS)

- Hyperionics @Voice is Android-only, free with ads plus a premium license. Snippets give 2.5M+ downloads, rated about 4.5–4.8. https://hyperionics.com/atVoice/
- A *different* iOS app named "Voice Aloud Reader" (MWM, id1446876360) is rated **4.64 from about 19K ratings** (appbrain snippet). https://www.appbrain.com/appstore/voice-aloud-reader/ios-1446876360
**Signal:** the App Store has many template "TTS reader" apps from app studios (MWM and others), which suggests competitive paid-keyword bidding.

#### 11. Long tail of App Store look-alikes (keyword saturation)

Found by search, not profiled: "AI Reader: Read Aloud Pdf Book" (id6754524209, a 2025–26 entrant), "Books Aloud AI Reader" (Kindle sync), "Speakify," "Talk PDF: Text To Speaker" (id6752616795, 2025–26), "TTS Reader Pro – Voice Aloud Reader" (id6746346171, 2025–26), "PDF Voice Reader – Docs Aloud," "Text to Speech PDF Reader" (remembers position), "Read Text Aloud AI – Speechie," and "Text Reader: Text to Speech" ("resume where you left off"). Web tools include CastReader, Read Aloud Reader, Mira Reader and Frateca.
- https://apps.apple.com/us/app/ai-reader-read-aloud-pdf-book/id6754524209 ; https://apps.apple.com/us/app/books-aloud-ai-reader/id6473523196 ; https://apps.apple.com/us/app/ttsreader-text-to-speech-ai/id6746346171 ; https://apps.apple.com/us/app/text-to-speech-pdf-reader/id1519637964
**Signal:** **Resume position is table stakes.** Even the low-end template apps advertise it. It cannot be the headline differentiator.

---

### Indirect Competitors (read-it-later apps with TTS)

| Product | TTS status (2025–26) | Notes / URL |
|---|---|---|
| **Pocket** | **Shut down July 8, 2025.** Data deleted Oct 8, 2025. It had TTS. | Left read-later + listen users without a home, now mostly absorbed. https://techcrunch.com/2025/05/22/mozilla-is-shutting-down-read-it-later-app-pocket |
| **Instapaper** | AI voices (Premium), a redesigned floating TTS player, playlists, iOS 9.4+ | Audio is a feature there, not the product. https://blog.instapaper.com/post/802011928668094464/ai-voices-text-to-speech-redesign-and-android |
| **Matter** | Said to have "the strongest TTS in the category." Upgraded its voice provider in Sept 2025. Word-by-word tracking. Handles newsletters and PDFs. | https://x.com/matter/status/1972721270774173711 ; https://tooliverse.ai/tools/matter |
| **Readwise Reader** | AI TTS (Unreal Speech voices). Starts from the scrolled position. **PDFs only in text view.** About $10–13/mo bundled with Readwise (price not re-verified). | https://docs.readwise.io/reader/docs/faqs/text-to-speech |

**Signal:** For web articles and newsletters (the "read anything" phase 2), read-later apps already include decent AI TTS. Pocket's shutdown freed some users, but that was a one-time event in 2025.

### Indirect: AI summarization audio (a different job)

- **Google NotebookLM Audio Overviews:** podcast-style two-host summaries of uploaded documents. iOS and Android apps since **May 2025** with offline audio. Free. "Millions" of users. https://www.macrumors.com/2025/05/20/google-releases-notebooklm-app-for-ios-and-android/ ; https://blog.google/innovation-and-ai/products/notebooklm-app/
- **Google Docs Audio summaries (Feb 2026):** Gemini summaries under a few minutes long, with voice personas. Paid Workspace/AI plans, web. https://workspaceupdates.googleblog.com/2026/02/listen-to-audio-summaries-in-google-docs.html
- **ChatGPT Read Aloud:** natural voice, but reported to cut out at about **one minute** ("Failed to play message"). Not usable for long documents. https://summary.ai/blog/chatgpt-voice-read-word-documents/
- **Perplexity voice mode:** speaks answers only. Not a document reader.
- **Wondercraft / Podcastle:** not verified this session (search budget ran out). They are known as creator tools for turning documents into podcasts, not consumer readers.
**Signal:** Summaries replace *some* long-document listening, such as "get the gist of a 20-page briefing." That weakens the "must hear every word" use case for professionals.

---

### Substitutes: built-in, free platform features (the biggest threat to H2)

| Feature | Current state | Long-document behavior | URL |
|---|---|---|---|
| **Google Docs "Listen to this tab" (Gemini audio)** | **Launched Aug 18, 2025.** Natural Gemini voices, speed control, floating player with duration, author-inserted "Audio buttons." English, **web only** at launch. | Reads the whole tab in natural voices. **This directly attacks the founder's Google Docs use case on desktop.** I could not confirm whether it has reached the iOS Docs app. | https://workspaceupdates.googleblog.com/2025/08/listen-to-documents-using-gemini-google-docs.html ; https://9to5google.com/2025/08/18/google-docs-audio-gemini/ |
| **Google Docs Live (Sept 2026)** | Gemini live voice conversations in the Docs, Gmail and Keep mobile apps | Conversational, not a linear reader, but it shows Google is putting voice into Docs mobile | https://www.androidheadlines.com/2026/09/google-workspace-live-voice-conversations-gemini-gmail-docs-keep.html |
| **Chrome "Listen to this page"** | Android and desktop. Added an AI two-host podcast mode in Sept 2025. **Not on Chrome for iOS.** | Web pages only | https://www.ghacks.net/2025/09/22/chrome-for-android-can-now-read-web-pages-aloud-like-a-podcast/ |
| **iOS Speak Screen / Speak Selection / Spoken Content** | Free, on-device, with premium Siri voices | **Well-documented unreliability:** "stops reading entirely in the middle of text," skips paragraphs, halts on page turns ("No speakable content"), and gets broken by iOS updates ("insanely unreliable"). **Supports H1.** | https://discussions.apple.com/thread/255489297 ; https://discussions.apple.com/thread/254777900 ; https://discussions.apple.com/thread/256209564 |
| **Safari "Listen to Page"** | iOS 17+ | Skips paragraphs, breaks after Bluetooth disconnects, sometimes greyed out | https://discussions.apple.com/thread/255894417 ; https://discussions.apple.com/thread/255898927 |
| **iOS 26 Accessibility Reader (Sept 2025)** | **System-wide:** triple-click pulls text from *any app* into a clean reader with highlighted read-aloud and autoplay | **Apple has entered "read anything from anywhere on your phone"** (the founder's phase 2). Voice quality is Apple's own, not generative AI. WWDC26 had a session on making reading apps work with it. | https://support.apple.com/guide/iphone/read-listen-text-apps-accessibility-reader-iph406a46ab8/ios ; https://developer.apple.com/videos/play/wwdc2026/219/ |
| **Microsoft Edge Read Aloud / Immersive Reader / Word** | Free Azure neural voices (Aria, Jenny, Guy), about 50 languages. Reads PDFs, web and Word in Edge. Works offline with basic voices. | Decent on desktop, free. iOS coverage not verified. | https://www.microsoft.com/en-us/edge/features/read-aloud |
| **Kindle Assistive Reader + AI Narration** | Assistive Reader added to the Kindle app in 2025 (system voice, "robotic"). Publisher opt-in AI narration is expanding. | Books only | https://www.amazon.com/gp/help/customer/display.html?nodeId=TqLHvK6eo6O7DJVQoZ |
| **Podcast apps via Audioread-style feeds** | Save position, sync, offline | A DIY route to "audiobook progress" | see Audioread |

---

## Competitive Positioning Map

| Competitor | Price (annual) | Voice quality | Long-document reliability | Google Docs import | Progress sync | Offline | Funding/scale |
|---|---|---|---|---|---|---|---|
| Speechify | $139 (annual only) | High (behind Eleven) | Mixed, many stop/lose-place complaints | Yes (Drive, flaky) | Yes | Yes | Profitable, 50–60M users claimed, ~$2M/mo US iOS (Sensor Tower est.) |
| ElevenReader | Free 10 hr/mo; $99 | **Best** | Mixed, freezes and loses place; 500-page cap | No native (copy/paste or file) | Yes | Yes (Ultra) | $11B parent, ~5M installs, 4.7 (~9K ratings) |
| NaturalReader / Voice Dream | ~$99–119 / ~$80 | Medium-high | OK, flat on long docs | Yes (Drive, basic) | Limited | Yes | Legacy, trust issues |
| Speech Central | $9.99 one-time | Uses system + AI voices | Good (accessibility) | Via files | ? | Yes | Indie |
| Peech | ~$70–99 | High | Reportedly reliable | Files/PDF | ? | ? | 1M+ users claimed |
| Audeus | $119 | High | Markets auto-resume | **Yes (markets "Gdocs")** | Yes | ? | Unknown |
| Listening.com | ~$59 | Medium-high | Strong for papers | PDF | Bookmarks | ? | Niche |
| Audioread | ~$60 | High | Podcast-app resume | Via forward/URL | Via podcast app | Via podcast app | Small |
| Google Docs Listen | Free | High (Gemini) | Good on web | **Native** | ? | No | Google |
| iOS Speak Screen / Accessibility Reader | Free | Medium | **Poor** | N/A | No | Yes | Apple |
| NotebookLM | Free | High | N/A (summaries) | Via Drive | N/A | Yes | Google |

---

## White Space Analysis

**Hypothesis check (adversarial):**
- **H1 (built-ins and incumbents handle long docs badly): partly supported.** There is strong evidence for iOS Speak Screen and Safari, and repeated "loses place / stops mid-text" complaints for *both* Speechify and ElevenReader. But (a) Google fixed its own Google Docs read-aloud with Gemini voices in Aug 2025 (web), and (b) Apple shipped a system-wide Accessibility Reader in iOS 26.
- **H2 (no strong AI audiobook-style document reader dominates the App Store): rejected.** Speechify dominates the App Store category with a profitable ad machine. ElevenReader holds the quality high end, subsidized by an $11B parent, with 10 free hours a month. Audeus, Peech, NaturalReader, Voice Dream and Speech Central fill the mid-tier. Dozens of template apps bid on the keywords. **The space is saturated at the feature level.**
- **H3 (niche = long docs + progress saving + Google Docs/PDF import): weak as stated.** Every one of these features is already *claimed* by at least three competitors (Speechify, Audeus, NaturalReader), and resume-position is table stakes even in low-end apps. What is open is *execution quality*: nobody is trusted to be reliable on 20–200-page documents. Reliability is hard to market until reviews build up.
- **H4 (people pay subscriptions): supported, with caveats.** Speechify earns tens of millions. The price anchors are $99 (Eleven, NaturalReader), $119 (Audeus) and $139 (Speechify), with Listening and Audioread at about $60 and Speech Central at a one-time $10. Accessibility users react badly to subscriptions they see as unfair (Voice Dream), and to dark-pattern billing (Speechify's top complaint).

**Unmet needs (with evidence):**
1. **Reliability on long content.** No stopping, no losing place, no freezing, and a way to "restart from the right point" (ElevenReader, Speechify and Speak Screen complaints above).
2. **Live Google Docs sync.** Competitors *import a copy* through Drive (flaky for Speechify, basic for NaturalReader). Nobody was found that keeps listening position anchored to a *living* Google Doc that changes, or re-syncs edits. This is unverified, but it is a possible wedge for teams handling briefings.
3. **PDF layout handling.** Pauses at line breaks, reading headers, footers and citations (the Speechify complaint; Listening solved this only for academic papers).
4. **Honest billing.** Monthly plans, no trial traps. That is positioning against Speechify's reputation.
5. **Professional briefing workflows** (legal, policy, consulting, investor memos): reading notes, skipping appendices, chapter and heading navigation. Listening.com shows vertical focus works for academia; the equivalent for business professionals is unclaimed as far as this search found.

**Positioning opportunities:**
- A vertical play on "the reliable reader for work documents" (briefings, memos, reports), rather than a general "read anything."
- An **anti-Speechify on trust** (monthly pricing, easy cancel), but note that ElevenReader already undercuts on price.
- **Build on top of a commodity TTS API** (ElevenLabs, OpenAI, Google) and compete on document handling and UX, not on voices.

**What to avoid:**
- Competing on voice quality or price against ElevenReader.
- Phase 2, "read anything from anywhere on iOS": Apple's iOS 26 Accessibility Reader and iOS sandboxing (third-party apps cannot read other apps' screens) make this both hard to build and already partly served by the operating system. Share-sheet and Safari extensions are the only routes in.
- Relying on "progress saving" as the headline. It is table stakes.

---

## Key Takeaways

1. **The space is saturated at the feature and keyword level.** One profitable leader (Speechify), one quality leader backed by $11B (ElevenReader, free 10 hr/mo, $99/yr), a crowded mid-tier (Audeus already markets Google Docs + PDF + auto-resume on iOS), and platform owners giving away good-enough features (Google Docs Gemini Listen, iOS 26 Accessibility Reader, NotebookLM).
2. **The real gap is execution reliability on long documents**, which is documented across incumbents. That is a hard wedge to *communicate* against Speechify's paid-acquisition machine. Any entrant needs a sharper vertical, such as professional briefings with live Google Docs sync, or a distribution channel, such as enterprise or education, rather than competing on App Store keywords.
3. **Lessons:** Voice Dream shows that accessibility users punish subscription bait-and-switch. Speechify's reviews show that billing dark patterns create lasting resentment competitors can use. Pocket's closure shows that listening alone is not enough to sustain a product.

---

## Sources
(All URLs are cited inline above. Main ones:)
- https://getlatka.com/companies/speechify.com
- https://app.sensortower.com/overview/1209815023?country=US
- https://finance.biggo.com/news/82a0b4613f50dfa4
- https://speechify.com/blog/cliff-weitzman-speechify-20vc-lessons/
- https://ie.trustpilot.com/review/speechify.com
- https://ashishdoneriya.medium.com/bugs-in-speechify-f25852241cca
- https://texttolab.com/blog/speechify-alternatives
- https://elevenreader.io/blog/best-pricing-more-value
- https://www.appbrain.com/appstore/elevenreader-read-books-aloud/ios-6479373050
- https://justuseapp.com/en/app/6479373050/elevenlabs-reader-ai-audio/reviews
- https://castreader.com/blog/elevenreader-review-2026
- https://techcrunch.com/2026/02/04/elevenlabs-raises-500m-from-sequioia-at-a-11-billion-valuation/
- https://elevenlabs.io/blog/500m-arr-and-new-investors
- https://help.naturalreaders.com/en/articles/8854700-plans-pricing-personal-version
- https://www.trustpilot.com/review/www.naturalreaders.com
- https://www.perkins.org/resource/voice-dream-reader-subscription-controversy/
- https://mosen.org/voicedream/
- https://www.applevis.com/forum/ios-ipados/applause-has-backed-down-purchased-voice-dream-features-will-stay
- https://speechcentral.net/
- https://apps.apple.com/us/app/peech-text-to-speech-reader/id1429704005
- https://www.audeus.com/ ; https://www.audeus.com/pricing
- https://www.listening.com/pricing
- https://audioread.com/pricing
- https://hyperionics.com/atVoice/
- https://techcrunch.com/2025/05/22/mozilla-is-shutting-down-read-it-later-app-pocket
- https://blog.instapaper.com/post/802011928668094464/ai-voices-text-to-speech-redesign-and-android
- https://docs.readwise.io/reader/docs/faqs/text-to-speech
- https://workspaceupdates.googleblog.com/2025/08/listen-to-documents-using-gemini-google-docs.html
- https://workspaceupdates.googleblog.com/2026/02/listen-to-audio-summaries-in-google-docs.html
- https://www.ghacks.net/2025/09/22/chrome-for-android-can-now-read-web-pages-aloud-like-a-podcast/
- https://discussions.apple.com/thread/255489297 ; https://discussions.apple.com/thread/254777900
- https://support.apple.com/guide/iphone/read-listen-text-apps-accessibility-reader-iph406a46ab8/ios
- https://developer.apple.com/videos/play/wwdc2026/219/
- https://www.microsoft.com/en-us/edge/features/read-aloud
- https://www.amazon.com/gp/help/customer/display.html?nodeId=TqLHvK6eo6O7DJVQoZ
- https://www.macrumors.com/2025/05/20/google-releases-notebooklm-app-for-ios-and-android/
- https://summary.ai/blog/chatgpt-voice-read-word-documents/
