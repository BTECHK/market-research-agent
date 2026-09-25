# Voice Quotes: Audio Anywhere (long-document TTS)

**Collected:** 2026-09-25 | **Agent:** Voice Miner (+ Community Mapper)

## Method and limitations (read first)

- Egress from this environment blocked direct fetches of reddit.com, news.ycombinator.com, hn.algolia.com, apps.apple.com, discussions.apple.com, applevis.com, trustpilot.com, mjtsai.com and mail-archive.com. All evidence came from web-search result snippets; the session's 200-search budget ran out before the work was finished.
- The search index returned almost no Reddit pages, even with `site:reddit.com`. **Reddit (r/dyslexia, r/ADHD, r/lawschool, r/speechify and the rest) was not mined.** This is the largest gap. A follow-up pass with Reddit access is recommended.
- Quote labels:
  - **[V]** = verbatim text shown in the search snippet.
  - **[P]** = close paraphrase from the snippet. Re-check at the URL before using it in a deck.
  - **[T]** = the source thread's title, used as a signal.
- Total items: 58 quote/signal items (about 14 verbatim, about 32 paraphrases, about 12 thread titles) from 12 source types: Apple Community, AppleVis, Zotero Forums, Adobe Community, Trustpilot, BBB, Substack, mjtsai.com comments, Six Colors, mosen.org, Readwise feedback, review aggregators and competitor blogs.

---

## Pain Points

### PP1: iOS built-in TTS (Speak Screen / Spoken Content / Safari Listen to Page) stops, skips or loops on long content
**Frequency:** High and recurring. Threads span iOS 8.3, 13.4.1, 15, 17, 17.3, 18.x and 26, with at least 15 distinct Apple Community threads.
**Intensity:** High for accessibility users, medium for others.

- [T] "iOS 18: 'Speak Screen' is largely broken" — https://discussions.apple.com/thread/256013629
  - [P] In the same thread: 1.5x speed actually plays at about 2.5x, and 2x plays at about 4x (iOS 18.2 to 18.4.1).
- [T] "Why Is the Siri / Safari listen to page feature so unreliable?" — https://discussions.apple.com/thread/256044481
  - [P] "on some pages it reads all the article, but on other pages it skips paragraphs, freezes or just stops reading in the middle of the article"
  - [P] A user suspects "a memory leak, timing/asynchronous race condition".
- [T] "How to stop Safari from skipping paragraphs on iOS 17.3" — https://discussions.apple.com/thread/255489297
- [T] "Speak Screen sometimes halts while reading in Apple Books" — https://discussions.apple.com/thread/254777900
  - [V] Error on resume: "No speakable content could be found on the screen".
- [P] Reading stops at the end of each page, so the user must re-trigger on every page (iOS 13.4.1): "No more continuous spoken content" — https://discussions.apple.com/thread/251368603
- [P] After an iOS 8.3 update, Speak Screen reading a PDF in iBooks stopped once the page was done — https://discussions.apple.com/thread/6994327
- [P] "iPhone will only read a few words or a few lines of a PDF" — https://discussions.apple.com/thread/255360754
- [T] "Speak screen stops working" — https://discussions.apple.com/thread/256197246
- [T] "Speak screen errors and skips" — https://discussions.apple.com/thread/251119204
- [T] "Speak Screen skipping words…" — https://discussions.apple.com/thread/253664515
- [T] "Help iOS26 accessibility issues with Spoken Content" — https://discussions.apple.com/thread/256137942
- [P] "When users multitask … or if the screen locks, spoken content crashes and stops without remembering its place." (search summary of the Apple Community cluster)
- [P] Zotero iOS: at the end of a page, Spoken Content "begins from the top of the page and goes in circles endlessly" instead of turning the page — https://forums.zotero.org/discussion/124826/ios-ipados-spoken-content-not-continuing-to-next-page-instead-goes-in-circles
- [P] AppleVis: Spoken Content, Speak Screen and Speak Selection "stopped working properly with the Siri voices … after installing iOS 18" — https://www.applevis.com/forum/low-vision-accessibility-apple-products/spoken-content-speak-screen-speak-selection-stopped
- [P] A third-party guide says Speak Screen "reads with the default system voice and loses your place between sessions … reads the screen rather than a document" — https://aidictation.com/blog/text-to-speech-iphone

**Analysis:** This is the strongest evidence for H1. The founder's complaints (chokes on long content, loses place) are repeated by many independent users across OS versions for more than 10 years. Two caveats: the complainers are mostly accessibility users on Apple's forums, and most complaints are about bugs, not voice quality.

### PP2: PDFs are read badly (headers, footers, footnotes and page numbers read mid-sentence; multi-column layouts and tables garbled)
**Frequency:** Medium. Standards bodies and accessibility communities have discussed it for a long time. Consumer complaints are scattered.
**Intensity:** High for academics, lawyers and students, whose documents are footnote-heavy.

- [P] Adobe Community: Read Out Loud does not allow "selecting to read just the main content of each page without repeating the same footnotes at the bottom of each page … haven't come across any app in the market that can omit the footnotes" — https://community.adobe.com/t5/acrobat-reader-mobile-discussions/text-to-speech-function-for-acrobat-reader-dc-with-option-to-omit-reading-footnotes/td-p/11165366
- [P] W3C WAI-GL thread: "It is very confusing … to have the headers and footers read in the middle of the sentence when the sentence spans the page break" — https://lists.w3.org/Archives/Public/w3c-wai-gl/2015AprJun/0224.html
- [T] Adobe: "Read out loud stops after each paragraph even when I've chosen whole document" — https://community.adobe.com/t5/acrobat-discussions/read-out-loud-stops-after-each-paragraph-even-when-i-ve-chosen-whole-document/m-p/10903349
- [P] ElevenReader reviews (per an aggregator): complex PDFs such as academic papers with tables, multi-column layouts and forms come out "incompletely, out of order, or with omissions". The same PDF uploaded several times dropped different sections each time — https://www.speedreadinglounge.com/elevenreader-review
- [P] ElevenReader: a chapter "cuts off at the end of those 11 minutes"; "When uploading large files like a PDF or EPUB … there is always an error message" — https://justuseapp.com/en/app/6479373050/elevenlabs-reader-ai-audio/reviews

**Analysis:** Clean extraction of structured professional PDFs looks like a real open wedge, even against ElevenReader. Speechify, however, already markets "skip footnotes, citations, headers".

### PP3: Speechify billing, trial and paywall practices
**Frequency:** High. It appears on Trustpilot, BBB, PissedConsumer, Apple Community, Substack and in almost every review article.
**Intensity:** High, and emotionally loaded ("predatory", "hoping you forget").

- [V] "There is no way to sign up free plan straightaway. They force you to accept free trial and force you to provide credit card details" (Trustpilot) — https://www.trustpilot.com/review/speechify.com
- [P] "…hoping you forget to cancel" (Trustpilot) — https://www.trustpilot.com/review/speechify.com
- [P] Canceled a free trial within 24 hours and was charged $139 more than a month later (Trustpilot) — https://www.trustpilot.com/review/speechify.com?page=8
- [P] Apple Community: signed up for a 3-day trial, got no alert, and was charged $139.99 against an expected $12 a month. The user called it "predatory". Speechify told them to ask Apple for the refund — https://discussions.apple.com/thread/256048372
- [V] BBB (Nov 18 2025): "charged $1.00 the same day and $188.00 after free trial expired on November 21 2025", despite canceling "after just one hour" — https://www.bbb.org/us/fl/miami/profile/education/speechify-inc-0633-92046942/complaints
- [P] BBB: Speechify is "using unethical and harmful tactics to financially take advantage of people with disabilities" — https://www.bbb.org/us/fl/miami/profile/education/speechify-inc-0633-92046942/customer-reviews?page=34
- [P] Substack note: forgot to cancel the free week and was charged for the full year — https://substack.com/@peterbanks/note/c-223072382
- [P] "Speechify is very expensive… price increased from $120/year to $140/year" — https://readaloud.net/en/blog/best-text-to-speech-app
- [P] The free tier has about 10 robotic voices, and "upgrade prompts appear constantly" — https://costbench.com/software/ai-voice-tools/speechify/free-plan/
- [P] The 3-day trial gets no reminder email; reminders go out only for trials longer than 31 days — https://checkthat.ai/brands/speechify/reviews
- [P] A voice the user picked years ago is "now robotic and awful" and changed without their action — https://www.justanswer.com/mac-computers/v7whs-speechify-voice-changed-robotic-sound.html
- [P] App Store: the new AI chat and workflows home screen is "obnoxious", with "no recently opened files" — https://apps.apple.com/us/app/speechify-text-to-speech-pdf/id1209815023?see-all=reviews

**Counter-evidence:**
- Speechify holds 4.7/5 on Trustpilot from about 6,600 reviews. The distribution is bimodal: about 83% five-star and 8% one-star.
- About 80% of refund requests reportedly succeed.
- The company claims 50M+ users, and Getlatka estimates ARR at about $17.6M (unverified).
- Anger is concentrated in a minority. Most users seem satisfied.

### PP4: Subscription backlash (Voice Dream) and price sensitivity in the accessibility segment
**Frequency:** High among blind and low-vision users in 2024 (AppleVis, mosen.org, Perkins, Vision Ireland, the viphone Google Group, Six Colors, mjtsai).
**Intensity:** Very high.

- [V] "Subscription = deal breaker!" (mjtsai.com comment) — https://mjtsai.com/blog/2024/04/08/voice-dream-reader-switches-to-subscriptions/
- [V] "User of the app myself, love it for what it does, but genuinely disgruntled by the change and was not willing to pay for what, ultimately, is local-only software." — same URL
- [P] Jonathan Mosen: the existing-customer "discount" to $99 instead of $79 was 25% more expensive, and the change breached Apple's guidelines — https://mosen.org/voicedream/
- [P] AppleVis users: "will not pay $60 a year"; "$60 a year is not reasonable for a simple reading app"; "for £59 a year I expect considerably more" — https://www.applevis.com/comment/146280
- [P] Persistent bugs reported "for several years with no response from the developer" — https://applevis.com/forum/ios-ipados/voice-dream-reader-oddities-possible-alternatives
- [T] "Applause has backed down: Purchased Voice Dream features will stay" (the owner reversed within days) — https://www.applevis.com/forum/ios-ipados/applause-has-backed-down-purchased-voice-dream-features-will-stay
- [P] ElevenReader's first paid tier was $100/yr with a 10 hr/month cap, and "caused frustration" among users used to unlimited free listening. ElevenLabs later cut it to $99/yr unlimited (Ultra) — https://speechcentral.net/2025/05/13/elevenreader-introduces-100-year-subscription-with-strict-limits-speech-central-offers-unlimited-use-for-10-lifetime/ and https://elevenreader.io/blog/best-pricing-more-value
- [P] NaturalReader is "disappointing, frustrating, time-consuming, and very expensive"; free voices sound "2019-era"; "many of the voices appear to be Microsoft voices" available free elsewhere — https://www.trustpilot.com/review/www.naturalreaders.com and https://qcall.ai/naturalreaders-review

**Analysis:** The accessibility segment is vocal, loyal and price-hostile. It rewards one-time pricing: Speech Central sells unlimited use for $10 lifetime. It is a poor fit for a $100+/yr subscription.

### PP5: No resume or progress saving
**Frequency:** Low to medium as a named complaint. It is mostly implied by the "loses place" reports.

- [P] Readwise Reader user: returning to a half-listened article starts TTS "back at the top"; "It would be useful if the text-to-speech function remembered where it had last been reading" — https://docs.readwise.io/changelog
- [P] Speak Screen "loses your place between sessions" — https://aidictation.com/blog/text-to-speech-iphone

**Counter-evidence:** Resume-from-position is already standard in Voice Dream, Text to Speech PDF Reader, WebOutLoud, TTSReader, Readwise and ElevenReader. It is table stakes, not a differentiator.

### PP6: ElevenReader gaps
- [P] "no desktop app" is "the loudest and most consistent user complaint since launch, still unresolved as of May 2026" — https://www.speedreadinglounge.com/elevenreader-review
- [P] Generated audio is locked in the app. Audio stops when the user switches apps (background playback). Android lags behind iOS — same source and https://castreader.com/blog/elevenreader-review-2026

---

## Evidence AGAINST the hypotheses (adversarial)

1. **ElevenReader is strong.**
   - [P] "voices are incredibly human … miles ahead of other consumer apps"; "I was looking at paying hundreds a year for other AI reading apps, but ElevenReader is a game changer" — https://www.speedreadinglounge.com/elevenreader-review
   - Pricing: 10 hrs/month free, then $99/yr unlimited.
2. **Google closed part of the founder's own gap.** Google Docs launched Gemini "Listen to this tab" (Tools > Audio) in Aug 2025, with natural voices and one-click audio buttons, then added audio summaries in Feb 2026. It needs a Workspace or Google AI plan. Reviewers call it "brilliant" and say it is pleasant for extended listening.
   - https://workspaceupdates.googleblog.com/2025/08/listen-to-documents-using-gemini-google-docs.html
   - https://www.makeuseof.com/audio-generation-in-google-docs/
3. **The market is crowded and cheap.** Apps include Speech Central ($10 lifetime, heavy PDF cleanup and ADHD profiles), Paper2Audio, Eist (free, unlimited), Audeus, CastReader, VoicePod, Spokt, Readaloud Reader, UPDF, Wordcast, SayTXT (free), Matter, Instapaper and Readwise TTS.
   - SEO pages titled "Pay Once, Not $139/yr" show that competitors are already positioning on price.
4. **Built-in is "good enough" for casual users.** [P] "Apple's built-in Spoken Content is the best free option … if you only need the occasional article read aloud, you may not need to install anything" — https://aidictation.com/blog/text-to-speech-iphone
5. **Speechify's billing anger has not visibly hurt its growth.** It has 50M+ users and is profitable.

---

## Segments observed

| Segment | Evidence strength | Notes |
|---|---|---|
| Blind / low vision | Strong (AppleVis, Apple Community, mosen.org, Perkins) | Most vocal and loyal, but price-hostile and prefers one-time purchase. Voices are a secondary concern; control and navigation matter more. |
| Dyslexia / ADHD | Medium (secondary sources; Reddit not mined) | Core Speechify market, and the target of the "exploiting disabled users" complaints. |
| Academics / researchers | Medium (Zotero, Adobe footnotes, Readwise) | Footnotes, multi-column layouts and resume. |
| Lawyers / consultants | Weak direct voice | Found only in vendor content: "a 40-page brief at 1.25x ≈ 90 min" of commute time. Confidentiality (ABA Rule 1.6) is a likely objection to cloud TTS. On-device processing could be a wedge (unvalidated). |
| Commuters / Pocket refugees | Medium | Pocket shut down in July 2025, displacing about 20M users and its free "Listen" feature. |
| Students (law, med) | Weak direct voice | Mostly Speechify marketing content. |

## WTP Signals

| Signal | Evidence | Implication |
|---|---|---|
| Existing spend | Speechify's $139/yr has a large paying base (ARR estimated at about $17.6M) | People do pay subscriptions |
| Price ceiling | $59–79/yr drew mass backlash (Voice Dream); $100/yr with caps drew backlash (ElevenReader) | For heavy users, $100/yr is the upper bound, and caps are resented |
| Floor | Speech Central $10 lifetime; many free apps | Hard to charge for commodity TTS |
| Friction resentment | "force you to provide credit card"; "hoping you forget to cancel" | Honest billing (no card for trial, reminder emails) is a positioning angle |
| "Hundreds a year" | An ElevenReader reviewer was considering paying hundreds a year before finding it | Some heavy users have high WTP |

## Language patterns
- **Problem language:** "skips paragraphs", "stops reading in the middle", "goes in circles", "loses place", "robotic", "reads the footnotes", "largely broken", "unreliable"
- **Competitor anger:** "predatory", "hoping you forget to cancel", "deal breaker", "take advantage of people with disabilities", "local-only software"
- **Desired outcomes:** "read to the end of the document without stopping", "just the main content", "remember where I left off", "listen while commuting"
