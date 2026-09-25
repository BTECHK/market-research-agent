# PM Strategic Analysis: Audio Anywhere

**Research Question:** Is there a viable market for an iOS-first app that reads long documents aloud with audiobook-grade quality and audiobook-style progress saving, starting with Google Docs and PDF (MVP1) and later "read anything from anywhere on your phone" (MVP2)?
**Analysis Date:** 2026-09-25
**Stance:** Adversarial, as requested. The goal is to find the reasons this fails before any code is written.
**Frameworks Applied:** JTBD, Four Forces, April Dunford Positioning, 7 Powers and Counter-Positioning, Pre-mortem (Tigers and Elephants), PMF / Very Disappointed Test, WTP through a JTBD lens. Added at the founder's request: Porter's Five Forces; a Why now / Why you / Why not Apple, Google or ElevenLabs test; and a bottom-up TAM/SAM/SOM.

**Evidence quality warning.** All inputs come from search snippets. Reddit, App Store reviews and Google Trends were not reached. There is **no first-person evidence from the professional segment**, which is the segment this analysis ends up recommending. Every conclusion about professionals is therefore a hypothesis to test, not a finding. Several raw inputs also conflict and are flagged where used:
- ElevenReader Ultra is described as "unlimited" in some places and "20 hours" in others (May 2026).
- Speechify is described both as "annual only" and as offering a "$29/mo" plan.
- Listening.com is priced at about $59/yr in one source and $99/yr in another.
- Speechify's revenue ranges from $17.6M (Latka) to about $24M from US iOS alone (Sensor Tower).

---

## 0. Bottom Line (Read This First)

1. **Don't build as specified.** MVP1 is "Google Docs + PDF + progress saving + great voices" as a consumer subscription. Every feature in it is already claimed by at least three competitors, and Audeus's homepage already reads "Read Aloud PDFs, Gdocs & more… saves your place." Resume-position is table stakes even in template apps. The voice-quality lead belongs to a competitor valued at $11B that gives away 10 free hours a month.
2. **Drop MVP2 ("read anything from anywhere") for iOS permanently.** On iOS it is technically impossible: sandboxing blocks it and texts cannot be read. It is also already a free OS feature through the iOS 26 Accessibility Reader. What remains possible (Share Sheet, Safari extension, OCR, Shortcuts) is parity with Speechify and ElevenReader.
3. **The only wedge that survives the evidence is narrow:** a "briefing-grade" reader for professionals who must hear *structured, long, often confidential* work documents *verbatim*. It would compete on three things:
   - **(a) document-structure fidelity:** strip headers, footers and page numbers, handle footnotes, get reading order right, narrate tables, navigate by heading;
   - **(b) guaranteed long-session reliability and exact resume;**
   - **(c) on-device voice for confidentiality.**

   This is a *feature-gap* wedge, not a moat. It is worth pursuing only if it passes the kill criteria in section 11.
4. **The realistic outcome if it works is a small business, not a venture-scale one.** The bottom-up SOM is about **$50K–$110K in gross bookings in year 1 and about $0.35M–$0.7M ARR by year 3** (section 9). That is unless a B2B or firm-license channel is proven, which no evidence yet supports.
5. **Spend the next 2–4 weeks on seven experiments costing under $1.5K in total, not on the app** (section 11). The single most important one is a concierge "cleaned audio via private podcast feed" test with real professionals, scored against a 40% very-disappointed threshold and a ≥25% pay-conversion threshold.

---

## 1. Hypothesis Verdicts

| Hypothesis | Verdict | Deciding evidence |
|---|---|---|
| H1: Built-ins and incumbents handle long docs badly | **Partly supported.** Strongest for iOS built-ins and accessibility users; weaker for professionals | 15+ Apple Community threads spanning iOS 8 to 26 ("No speakable content", "goes in circles"). Speechify: "loses the page and goes back to the beginning." ElevenReader: "loses its place," "freeze without a way to restart from the right point." **Against:** Google Docs "Listen to this tab" (Gemini, Aug 2025) fixed the founder's own Google Docs complaint on the web. The UK DfE now argues built-in tools are "good enough." |
| H2: No strong AI audiobook-style reader dominates | **Rejected** | Speechify: 50–60M users claimed, profitable, ~$2M/month on US iOS, 1,300 AI ads a day. ElevenReader: best voices, 10 free hours a month, $99/yr, $11B parent. A crowded mid-tier (Audeus, Peech, NaturalReader, Speech Central) plus template apps. |
| H3: A niche of long docs + progress + Google Docs/PDF import can be owned | **Rejected as stated.** It survives only if narrowed to *structure fidelity + reliability + privacy for professional documents* | Resume is "table stakes"; Google Drive import is parity; Audeus already markets the exact MVP. Open gaps: PDF structure ("haven't come across any app… that can omit the footnotes"), long-session reliability, and live Google Doc sync (unverified). |
| H4: People will pay a subscription | **Supported for the category, unproven for an entrant, and the economics are hostile** | Speechify, NaturalReader and Readwise sustain $80–160/yr. But productivity apps have the **lowest renewal rate of any category (~23%)**, median NA year-1 LTV is **$32**, install-to-paid is **2.6%**, and the accessibility segment punishes subscriptions (Voice Dream). |

---

## 2. Jobs-to-be-Done Mapping

### Functional Jobs
| Job | Evidence (Quote) | Source | Frequency |
|---|---|---|---|
| Get through an entire long document hands- and eyes-free without babysitting the player | [P] "stops reading in the middle of the article"; [V] "No speakable content could be found on the screen"; Speechify "stops the second the iPad screen sleeps" | Voice Miner PP1; Competitor Data | High (accessibility), unverified (professionals) |
| Hear only the *main content* of structured documents | [P] "haven't come across any app in the market that can omit the footnotes"; W3C: "headers and footers read in the middle of the sentence" | Voice Miner PP2 | Medium |
| Resume exactly where I left off, across sessions and devices | [P] "It would be useful if the text-to-speech function remembered where it had last been reading" (Readwise user) | Voice Miner PP5 | Low–Med as a named pain (it is table stakes) |
| Turn dead time (commute, walking) into document consumption | "a 40-page brief at 1.25x ≈ 90 min" of commute time (vendor content only, no first-person quote) | Voice Miner, segments | **Unverified** |
| Get the gist of a long document fast (a competing job) | NotebookLM Audio Overviews, Google Docs audio summaries (Feb 2026) | Trends | Rising |

### Emotional Jobs
| Job | Evidence | Confidence |
|---|---|---|
| Trust that the investment of listening time won't be wasted | [P] "Don't want to sink a few hours into a text only to have ElevenReader freeze, without even having a way to restart from the right point" | Medium |
| Not feel exploited by the tool I depend on | [P] "hoping you forget to cancel"; "take advantage of people with disabilities"; [V] "Subscription = deal breaker!" | High (accessibility), Medium (general) |
| Own my tools / control | [V] "not willing to pay for what, ultimately, is local-only software" | Medium |

### Social Jobs
| Job | Evidence | Confidence |
|---|---|---|
| Show up prepared (to have "read the brief") | **No evidence in the raw data.** This is inferred. | Low |
| Independence and dignity for print-disabled users | AppleVis and Perkins mobilization around Voice Dream | Medium |

**JTBD Summary:** The job with the strongest evidence is "finish a long document by ear without the tool failing me," and it is voiced mostly by accessibility users about *free built-ins*. The founder's intended job, "a professional absorbs a 20-page briefing on the go," has **zero first-person evidence** in the raw data. It also competes with a fast-growing substitute job, "just give me the gist" (NotebookLM, Docs summaries). The first thing to validate is whether professionals need *verbatim* listening often enough to form a habit.

**Frequency elephant (the Wispr analogy breaks here).** Dictation (Wispr Flow) is used dozens of times a day, because it is how you *produce* work. Long-document listening is episodic, perhaps 1–3 times a week for a heavy professional. Lower frequency means weaker habit, higher churn, and the ~23% productivity renewal benchmark. The analogy supports "a focused voice tool can beat OS features." It does not support "this job has Wispr-like retention."

---

## 3. Switching Dynamics (Four Forces)

| Force | Direction | Evidence | Strength |
|---|---|---|---|
| Push of current situation | Away from built-ins | "iOS 18: 'Speak Screen' is largely broken"; Safari "skips paragraphs, freezes" | **Strong for built-in users. Weak/unknown for Speechify and ElevenReader users**, who complain but stay: people keep using ElevenReader "because of its high-quality voice" |
| Pull of new solution | Toward a clean, reliable reader | "just the main content", "read to the end without stopping" | Moderate. The pull is real but invisible pre-trial: reliability cannot be seen on an App Store page |
| Anxiety of change | Against switching | Billing distrust ("force you to provide credit card"); confidentiality of work documents (ABA Rule 1.6, inferred); Apple 5.1.2(i) consent screens make cloud AI sharing explicit | Moderate–Strong |
| Habit of status quo | Against switching | "Apple's built-in Spoken Content is the best free option… you may not need to install anything"; reading on screen; skimming; asking an AI for a summary | **Strong** |

**Net Switching Likelihood:** **Low** for general consumers and existing ElevenReader users. **Medium** for built-in users who hit long-document failures. **Unknown** for professionals.
**Key Insight:** Push is strongest against *free* built-ins, and those users are the least likely to pay. Among paying incumbent users, voice quality anchors them despite bugs. So the go-to-market must *demonstrate* reliability and cleanup before install, using side-by-side demo audio of the same messy PDF read by Speechify, ElevenReader and "us," and must remove anxiety with no card required for the trial and on-device processing.

---

## 4. Positioning Opportunity (April Dunford)

**1. Competitive alternatives** (what the target professional does today):
- Read on screen or skim. This is the real #1 alternative, with a price of $0.
- Ask for a summary (NotebookLM, Gemini in Docs, ChatGPT).
- Google Docs "Listen to this tab" (web, Workspace/AI plan).
- ElevenReader free tier (10 hr/mo, roughly eight 20-page docs).
- Speechify ($139/yr).
- iOS Speak Screen or Accessibility Reader.

**2. Differentiated capabilities** (only ones incumbents are *documented* as failing at):
- Structure-aware cleanup: headers, footers, footnotes, reading order, tables. Speechify *claims* footnote skipping; ElevenReader drops sections of complex PDFs "differently on each upload."
- Pre-rendered audio files, which give guaranteed background playback, exact resume, offline listening, and a stronger CarPlay case.
- On-device synthesis (Kokoro-82M), so documents never leave the phone. This is a confidentiality claim ElevenReader and Speechify's cloud voices cannot make.
- An optional live Google Doc re-sync (unverified that nobody does it).

**3. Differentiated value:** "Hear the whole brief, only the brief, and never lose your place, without uploading client documents to anyone."

**4. Best-fit customers** (hypothesis, no first-person evidence yet): professionals who get 20–100+ page structured documents at least weekly and must know the contents verbatim. Examples: litigation and transactional lawyers, law and med students, policy analysts, consultants, investment analysts, academic researchers (Zotero and Listening.com evidence).

**5. Market category:** Not "text-to-speech app," a category Speechify owns through SEO, ASO and $500K/month creative testing. Instead: **"briefing reader" or "audio for work documents,"** a sub-category Listening.com proved works for academic papers.

**Positioning statement (test it, don't adopt it):** *For professionals who have to absorb long, structured work documents, Audio Anywhere is a private briefing reader that plays only the substance of your PDFs and Google Docs, start to finish, on-device, and never loses your place. Unlike Speechify or ElevenReader, which read everything including page furniture and send your files to the cloud, it is built for documents that matter and stay confidential.*

---

## 5. Porter's Five Forces (Consumer long-document TTS, US iOS)

| Force | Intensity | Evidence | Implication |
|---|---|---|---|
| **Rivalry among existing competitors** | **Very high** | Speechify (profitable, ad machine), ElevenReader (price cut 50%, 10 hr free), Audeus, Peech, NaturalReader/Voice Dream, Speech Central ($10 lifetime), dozens of template apps; SEO pages titled "Pay Once, Not $139/yr" | Price and feature parity arrive fast. Head keywords are unwinnable. |
| **Threat of new entrants** | **Very high** | Kokoro-82M is free and on-device; neural APIs cost $15–30 per 1M characters; 2025–26 template apps keep launching (Talk PDF, TTS Reader Pro, AI Reader) | Whatever the founder can build, a template studio can clone within a quarter, *except* hard document-cleanup quality. |
| **Threat of substitutes** | **Very high** | Free built-ins (Accessibility Reader, Speak Screen, Safari Listen, Edge Read Aloud); Google Docs Listen; NotebookLM summaries (free); Audioread-style podcast feeds; reading it yourself | The ceiling on willingness to pay is set by "free and good enough." |
| **Buyer power** | **High** | Zero switching costs (import is one tap); monthly cancel; accessibility users organized and price-hostile (AppleVis revolt forced Applause to reverse within days); students get ElevenReader free for a year | Hard to raise prices; renewals weak (~23% productivity median). |
| **Supplier power** | **Medium–High** | Apple takes 15–30% and gatekeeps (5.1.2(i) AI consent, CarPlay entitlement ambiguity, web-link fee still being set); Google gatekeeps Drive scopes (CASA $500–4.5K/yr for restricted scopes); **the leading voice supplier (ElevenLabs) is also the leading competitor**; PlayHT died with ~5 months' notice | Use on-device voices by default and abstract across two or more cloud vendors. Use `drive.file` with the Picker. |

**Verdict:** The structure is unattractive. Value accrues to (a) owners of voice models, who have marginal cost below list API rates (ElevenLabs, and Speechify with SIMBA), and (b) owners of paid-acquisition machines (Speechify). A small entrant without either can capture profit only in a pocket where rivalry is low *because the job is specialized*. That argues for the narrow vertical, or for not entering at all.

---

## 6. Why Now / Why You / Why Not Apple, Google or ElevenLabs

**Why now: mixed, and mostly "the shift already happened."**
- *For:* TTS costs have collapsed (a 20-page doc costs about $0.90 on OpenAI and about $0 on-device). Kokoro makes on-device voice good enough to test. AI narration passes blind tests (Edison: 61% thought an AI narrator was human). Pocket and Omnivore died. ElevenReader is drifting toward audiobook retail (200K titles, May 2026).
- *Against:* The "robotic to human voice" shift, the only strategic-narrative-grade change, was captured in 2023–25 by ElevenLabs and Speechify. Platforms are now absorbing the rest: Google Docs Listen (Aug 2025), iOS 26 Accessibility Reader, and iOS 27 Siri "read a document." **The window for the wedge is 6–12 months**, the time before Apple or Google close the reliability gap.

**Why you: unanswered, and this is the weakest link.** The raw data gives the founder a personal pain point, but no evidence of any of the following:
- distribution in a vertical (for example, being a lawyer or consultant with a network);
- proprietary technology (for example, document-parsing expertise);
- an audience.

"I felt the pain" is also true of Speechify's founder, who had a nine-year head start. **Before building, the founder should write one sentence on why they would win the briefing-reader vertical specifically.** If the honest answer is "I'm a good iOS engineer," that is necessary but not sufficient.

**Why not Apple?**
- Apple's incentives are accessibility compliance and platform stickiness, not premium professional document workflows.
- Its built-ins have been buggy on long content for 10+ years, which is evidence that it deprioritizes this.
- **Risk:** iOS 27 brings a Gemini-derived model and Siri "read a document" into the OS. If Apple ships neural voices plus position memory in Accessibility Reader, the generic reliability pain disappears overnight for free. Structure cleanup (footnotes, tables) is less likely to be an Apple priority.
- *Probability that Apple kills the generic wedge within 18 months: medium. Probability that it kills the structure-fidelity wedge: low–medium.*

**Why not Google?**
- Google already did it for Docs on the web, paywalled to Workspace and AI plans, which bundles it into Gemini upsell.
- Docs Live (Sept 2026) shows voice is coming to the Docs *mobile* apps. Expect "Listen" in iOS Google Docs.
- **This kills "Google Docs import" as a reason to exist.** Google won't handle PDFs from other sources, footnote-heavy legal PDFs, or on-device confidentiality.
- *Probability of neutralizing the Google Docs angle: high.*

**Why not ElevenLabs?**
- ElevenLabs owns the best model at near-zero marginal cost and could fix resume and PDF parsing in one sprint.
- Its incentives point elsewhere: $500M ARR is mostly API and enterprise, and the consumer app is chasing audiobooks. Its bugs have persisted since launch, and "no desktop app" remains the #1 complaint.
- It *cannot* credibly claim on-device privacy, because its business is cloud inference. **That is the only real counter-position against ElevenLabs.**
- *Probability that it out-executes you on reliability if it chooses to: high. Probability that it chooses to within 12 months: medium.*

**Net:** Every open gap is one an incumbent *could* close cheaply but hasn't prioritized. That is a speed-and-focus wedge, not structural protection. It is only worth taking if it is cheap to validate and the founder has a vertical-distribution edge.

---

## 7. Defensibility Assessment (7 Powers + Counter-Positioning)

| Power | Applicable? | Evidence | Confidence |
|---|---|---|---|
| Scale Economies | **No (incumbents have it)** | ElevenLabs and Speechify run their own models, so their marginal cost is below list API rates. Speechify spends $500K a month on creative testing. | High |
| Network Effects | No | Single-player utility. A "shared team briefing library" could create weak within-team effects, but that is speculative. | Medium |
| Counter-Positioning | **Partial: the best available** | (1) *Honest billing*: Speechify's trial-to-annual auto-conversion is a revenue engine it can't drop without hurting revenue, but Speech Central ($10 lifetime) already occupies "anti-subscription." (2) *On-device confidentiality*: ElevenLabs and Speechify cloud businesses can't match it without undermining their model. Apple can, but with weaker voices and no document cleanup. | Medium |
| Switching Costs | Weak | Libraries, notes and progress are easy to re-import. Deeper workflow hooks (Drive folders, firm integrations) could add some. | Medium |
| Branding | No (not yet) | Speechify owns "text to speech." Trust branding among AppleVis-style communities is earnable but slow. | High |
| Cornered Resource | No | Voices, parsers (Mistral OCR at ~$1–2 per 1,000 pages) and on-device models are all commodities. | High |
| Process Power | **Partial** | A tuned cleanup pipeline per document type (court filings, 10-Ks, academic papers, policy briefs), plus an evaluation set of real messy PDFs. Replicable in 6–12 months by a motivated team, but incumbents have shown little motivation. | Low–Medium |

**Primary defensibility path:** Counter-positioning on *on-device confidentiality*, plus process power in *document cleanup for specific professional document types*. Both are thin. Real defensibility would come only from a B2B or firm channel (switching costs through procurement, VPAT, firm-wide deployment), which is unvalidated.
**Defensibility risk:** Apple adds neural voices and position memory to Accessibility Reader. ElevenReader fixes PDF parsing and resume. Either removes the reliability half of the wedge, leaving only confidentiality and structure.

---

## 8. Strategic Risks / Pre-mortem

*Assume it is September 2027 and Audio Anywhere has failed. Why?*

### Tigers (Rapid, visible threats)
| Risk | Likelihood | Impact | Evidence | Mitigation |
|---|---|---|---|---|
| Apple ships premium neural voices plus resume in Accessibility Reader or Siri (iOS 27.x/28) | Medium | High | iOS 27 Gemini-derived model; Siri "read a document"; WWDC26 session on reading apps | Run the iOS 27 test first (Exp. 5). Anchor on structure fidelity and confidential documents, not generic reliability. |
| Google ships "Listen" in the iOS Docs app | High | Medium | Docs Listen (web, Aug 2025); Docs Live on mobile (Sept 2026) | Do not lead with Google Docs. Lead with messy PDFs. |
| ElevenReader fixes resume and PDF parsing | Medium | High | It has $500M of fresh capital and the best model | Move faster in one vertical; publish head-to-head demos. |
| Unit economics break on premium cloud voices | High if "unlimited cloud" | High | At $9.99/mo, ElevenLabs v3 has **−1,113%** gross margin for a 20 h/mo user | On-device by default; meter cloud "studio" hours; cache per document. |
| Can't acquire users: ASO head terms locked, paid CAC above LTV | High | High | NA year-1 LTV $32 vs Speechify's ad machine; 57.7% of new apps never reach $1K revenue | Organic community and content in one vertical; measure CAC in Exp. 4 before building. |

### Elephants (Slow, ignored truths)
| Risk | Likelihood | Impact | Evidence | Mitigation |
|---|---|---|---|---|
| **The professional segment doesn't exist at habit-forming frequency.** Professionals want summaries, not verbatim audio. | **Medium–High** | **Fatal** | No first-person professional quotes; NotebookLM and Docs audio summaries growing | Exp. 2 and 3 exist to test exactly this. |
| **The founder's pain is an accessibility-user pain,** and those users are served, price-hostile and loyal to trusted indies | High | High | AppleVis and Voice Dream backlash; Speech Central $10 lifetime; DfE "built-ins good enough" | Don't target accessibility users with a $69–99 subscription. Consider a lifetime tier or free VoiceOver access as goodwill, not revenue. |
| **Retention decays like a productivity app** (~23% annual renewal), so LTV stays near $32 | High | High | RevenueCat 2026; AI apps show weaker long-term retention | Hard gate: week-4 retention in the concierge test. Consider team plans. |
| "Reliability" can't be marketed. It is only proven after weeks of use and reviews. | High | Medium | Positioning map: everyone *claims* resume | Side-by-side demo audio; free on-device tier so users discover reliability. |
| Founder-market fit gap | Unknown | High | No stated vertical access | The "why you" sentence; recruiting speed in Exp. 2 is itself a test. |

### Paper Tigers
- **"The TTS market is $4–5B."** These are report-mill numbers and irrelevant (section 9).
- **Google CASA cost.** Avoided with `drive.file` and the Picker.
- **Cost of on-device quality.** Kokoro runs at about 3.3x real-time on an iPhone 13 Pro. Only a blind listening test matters (Exp. 6).

**Top risk to address:** The frequency and "verbatim vs gist" elephant. If professionals don't listen to full long documents weekly, nothing else matters. It is also the cheapest risk to test.

---

## 9. TAM / SAM / SOM (bottom-up; every assumption stated)

Report-mill TTS market sizes ($3.5–4.9B, CAGRs from 3.7% to 23.3%) are **excluded**. They blend enterprise APIs, IVR and automotive.

### TAM: revealed US consumer spend on read-aloud apps (built up company by company)
| Component | Calculation | Estimate | Confidence |
|---|---|---|---|
| Speechify, US iOS | Sensor Tower snippet: ~$2M in one month × 12. **Assumes that month is representative.** | ~$24M | Low–Med |
| Speechify, US other channels (web, Chrome, Android, Mac) | **Assume +50–100% of US iOS** | $12–24M | Low |
| ElevenReader, US | 5M global installs × 2.6% paid (RevenueCat median) × ~$80 net blended × **~40% US share (assumption)** | ~$4M | Low |
| Mid-tier and long tail (NaturalReader/Voice Dream, Peech, Audeus, Listening, Audioread, Speech Central, template apps) | **Assume 10–15 apps × $0.5–1.5M US each** | $5–20M | Low |
| **Total TAM (US consumer read-aloud spend)** | | **≈ $45–70M/yr gross, midpoint ~$55M** | Low–Med |

This is a real but modest market, and roughly two-thirds of it is one company's revenue.

### SAM: the briefing-reader wedge (US, iOS, professionals)
Assumptions marked **[A]** are external or analyst assumptions not in the raw data. Verify them with BLS and a quick survey.
| Step | Assumption | Result |
|---|---|---|
| US professionals who routinely consume 20+ page structured documents | **[A]** Lawyers ~1.3M + management analysts/consultants ~1M + financial/investment analysts ~0.4M + policy/government analysts ~0.5M + researchers, faculty and grad/professional students ~3.5M ≈ **6.7M** | 6.7M |
| Share with a weekly verbatim-listening need who prefer audio for part of it | **[A] 10–20%.** Anchored loosely on Edison's 37% past-year audiobook listening, discounted for work content and the summary substitute. | 0.67–1.34M |
| On iPhone | **[A] ~57%** US iPhone share | 0.38–0.76M |
| Willing to pay ≥$69/yr rather than use ElevenReader free, Google Docs Listen or summaries | **[A] 20–30%** | **76K–230K potential payers** |
| × $69/yr list price | | **SAM ≈ $5M–$16M/yr** |

**Accessibility segment (not in SAM, upside only).** 15.5M adults with ADHD, 7.15M with best-corrected vision loss, and dyslexia (the 15–20% figure is symptoms, not diagnoses). This group is already served by free built-ins, Speechify and Speech Central, and it is subscription-hostile. Winning it requires a lifetime tier and community trust, which does not fit an early SOM.
**Students are excluded:** ElevenReader gives them a year free and Speechify gives 50% off.

### SOM: what a solo or small team can realistically capture
| Horizon | Assumptions | Result |
|---|---|---|
| Year 1 | 30K installs from long-tail ASO ("read PDF aloud", "briefing reader"), vertical communities and content (**[A]**, no paid engine) × **3–6% install-to-paid** (above the 2.6% median because of niche intent, a hard paywall after an on-device free tier, and a 14–30 day trial at 42.5% median trial conversion) = 900–1,800 payers × $69 × 0.85 after Apple's 15% | **≈ $53K–$106K gross bookings.** Realized LTV about $32–50 per payer. |
| Year 3 | 5–10K active payers, **assuming annual renewal ≥40%** (vs the 23% productivity median) plus a small-team plan | **≈ $0.35M–$0.7M ARR** (~3–6% of SAM) |
| Venture case | Needs firm or enterprise licensing (on-device confidentiality for law and consulting) or an education/disability-services channel with a VPAT | **Unvalidated.** No raw evidence of B2B demand. |

**Implication:** Even the success case is a good indie business. It is not a venture-scale "Wispr for listening" unless a B2B channel is proven. The founder should decide up front which outcome they want, because that choice changes whether the next four weeks are worth it.

---

## 10. PMF Signals (Very Disappointed Test)

**Evidence FOR (the category has PMF; incumbents own it):**
- Speechify: "worth every penny" and "transformative" for dyslexia and ADHD. Its revenue shows people pay at scale.
- ElevenReader: users stay despite bugs "because of its high-quality voice"; "I was looking at paying hundreds a year… ElevenReader is a game changer."
- Accessibility users fought publicly to keep Voice Dream. That is "very disappointed" behavior.

**Evidence AGAINST (for *this* product):**
- "if you only need the occasional article read aloud, you may not need to install anything"
- The UK DfE proposes funding only where built-ins fall short.
- Pocket shut down, which shows listening alone didn't sustain a product.
- No professional-segment quote exists anywhere in the raw data.
- Speechify's billing anger "has not visibly hurt its growth," so pain with incumbents is not the same as willingness to switch.

**PMF Assessment:** Category: **strong signals, captured by incumbents.** Founder's product as specified: **weak signals.** Briefing-reader wedge: **insufficient data.**
**Confidence:** Medium on the category, Low on the wedge.

---

## 11. Decision Rules: Validation Experiments and Kill Criteria (next 2–4 weeks, under $1.5K, minimal code)

| # | Experiment | Duration / cost | Proceed threshold | Kill threshold |
|---|---|---|---|---|
| 1 | **Incumbent bake-off.** Take 10 real long documents: 3 footnote-heavy legal or academic PDFs, 2 multi-column, 2 with tables, 3 Google Docs of 20–100 pages. Run them through ElevenReader (free), Speechify (trial, and cancel), Audeus, Peech, Google Docs Listen (web) and iOS Accessibility Reader. For each, score: finished without intervention; kept position after screen lock, app switch and force-quit; header/footer/footnote errors per 10 pages. | Days 1–4, ~$20 | Every incumbent fails at least 3 of the 10 documents on completion or resume, **or** averages ≥3 structural errors per 10 pages | Two or more incumbents complete ≥9 of 10 documents with ≤1 structural error per 10 pages **and** reliable resume. The gap is imaginary. |
| 2 | **JTBD switch interviews.** 15–20 target professionals (lawyers, consultants, analysts, researchers), recruited from the founder's network, r/lawschool, r/LawFirm and Zotero forums. Ask about their last long document: how they consumed it, whether it had to be verbatim, and what tools they tried. | Weeks 1–2, $0–300 in gift cards | ≥8 of 15 face ≥2 must-know long documents a week; ≥5 of 15 have tried or paid for a TTS tool; recruiting 15 takes ≤10 days | <5 of 15 have weekly frequency, **or** most say a summary (NotebookLM or Gemini) is enough. The "verbatim" elephant is real. |
| 3 | **Concierge MVP, no app.** Participants email or share documents. The founder cleans them (Mistral OCR plus an LLM pass) and renders audio (Kokoro or Chirp 3 HD) into a **private podcast feed** (the Audioread pattern: the podcast app handles resume, sync and offline). After two weeks, run the Sean Ellis survey and a real payment ask ($9/mo or $69/yr, via a Stripe link). | Weeks 2–4, ~$50 in API costs | ≥60% submit a second document unprompted within 7 days; ≥40% submit ≥3 documents in 2 weeks; **≥40% "very disappointed"**; **≥25% pay** | <15% pay **or** <25% "very disappointed" **or** <30% submit a second document |
| 4 | **Positioning smoke test.** Two landing pages: A "Private briefing reader: hear only the substance of long PDFs, never lose your place" vs B "Read anything aloud with AI voices." Run $600–1,000 of ads (Reddit or Google, long-tail keywords). The call to action is a waitlist plus an optional $29 founding deposit. | Weeks 1–3, $600–1,000 | Variant A: CTR ≥1.0%; landing-to-waitlist ≥15%; ≥5% of the waitlist pays a deposit; **implied cost per paying customer ≤$30** | Cost per paying customer >$60 **and** organic channels in Exp. 2 are weak. That means no affordable acquisition path. |
| 5 | **Platform check.** Run the Exp. 1 corpus through iOS 27 (Accessibility Reader, Siri "read a document") and Google Docs on iOS. | Day 2, $0 | The OS fails ≥30% of documents on completion, resume or structure | The OS scores within 20% of the best third-party app. Apple has closed the window. |
| 6 | **Cleanup and voice technical spike.** Build only the parsing pipeline plus Kokoro on-device. Test on 30 real PDFs. Run a blind A/B with 10+ listeners against ElevenReader on the *same* messy documents. | Week 1–2, ~$30 | ≥95% of pages have no header, footer or page-number leakage; listeners prefer our output ≥65% of the time on structured documents; Kokoro accepted for ≥30-minute listening by ≥50% of listeners | Can't beat ElevenReader in the blind test on structured documents. You have no product advantage. |
| 7 | **"Why you" memo.** Write one paragraph naming the vertical the founder can reach, the first 100 users by name or channel, and the unfair edge. | Day 1, $0 | A concrete channel with ≥100 reachable target users | No vertical access, and paid CAC (Exp. 4) fails. |

**Overall kill rule:** Stop, or pivot to an Android-first "read anything" product or a B2B firm tool, if Exp. 3 fails its pay or very-disappointed threshold, **or** if two of Exp. 1, 5 and 6 hit their kill thresholds.
**Build rule:** Build a narrow iOS MVP only if Exp. 2 and 3 pass and at least two of Exp. 1, 4 and 6 pass. The MVP would be PDF and Share Sheet import, cleanup, pre-rendered on-device audio, exact resume, and a `drive.file` Picker. It would *not* include read-anywhere, OCR of texts, or voice cloning.

---

## 12. Pricing Implication (WTP through a JTBD lens)

- **The value comes from reducing functional energy** (no babysitting, no garbage audio) **and emotional energy** (confidentiality, no billing traps). It does not come from voice quality, which is commoditized by ElevenReader's free tier.
- If the build rule passes, start at **$8.99/mo or $69/yr**. Include an **unlimited on-device** tier and **metered cloud "studio" hours** (5–8 h/mo at ≤$30 per 1M characters, about $1.60–2.50 in cost of goods). Offer a 14–30 day trial with **no card required** and reminder emails; this is the counter-position against Speechify.
- Apply for Apple's Small Business Program (15%) from day one. Test US web checkout as upside only.
- Never offer "unlimited premium cloud voice." It has negative gross margin above about 4–5 h/mo.
- Explore a firm or team plan (for example, $15–25 per seat per month, with on-device processing as the compliance story) only if Exp. 2 surfaces unprompted confidentiality concerns.

---

## Framework Summary

| Framework | Key Finding | Confidence | Action Implication |
|---|---|---|---|
| JTBD | The job with evidence is "finish a long doc by ear without failures" (accessibility users). The professional "briefing" job is unevidenced, episodic, and competes with "give me the gist." | Med | Run Exp. 2 and 3 before any code. |
| Four Forces | Push is strong only against free built-ins. Habit and anxiety (summaries, confidentiality, billing distrust) dominate. | Med | Demo reliability before install; no-card trial; on-device by default. |
| Positioning | "Text to speech" is an owned category. "Briefing reader for confidential work documents" is open. | Med | Test positioning A vs B (Exp. 4). |
| Porter's Five Forces | Four forces are high or very high. Profit pools sit with model owners and ad machines. | Med–High | Enter only through a specialized pocket; don't fight head-on. |
| Why now / you / not them | The window is 6–12 months. "Why you" is unanswered. Google neutralizes the Google Docs angle. | Med | Drop Google Docs as the headline; write the "why you" memo. |
| 7 Powers / Counter-positioning | Only thin counter-positioning (on-device privacy, honest billing) and process power (cleanup) are available. | Med | Invest in the cleanup evaluation set plus on-device; pursue B2B for real switching costs. |
| TAM/SAM/SOM | TAM ~$55M US spend; wedge SAM $5–16M; SOM ~$50–110K year 1 and $0.35–0.7M ARR year 3 | Low–Med | Decide indie vs venture ambition now. |
| Pre-mortem | The top elephant is professionals wanting summaries rather than verbatim audio. The top tiger is an Apple iOS 27.x upgrade. | Med | Exp. 2, 3 and 5 are gating. |
| PMF | The category has PMF (owned by incumbents). This product: weak or insufficient data. | Med / Low | 40% very-disappointed and 25% pay thresholds in the concierge test. |

---

## Frameworks Not Applied

- **Growth Loops.** There is no viral or content loop in single-player listening. The only loop visible is a paid loop, and it is dominated by Speechify. Revisit if a team or shared-library feature emerges.
- **Activation Metrics.** There is no product data yet. The likely aha moment to instrument later is "finished a first document of 20+ pages without intervention."
- **Opportunity Solution Tree.** Implicitly covered by the experiment table. A full tree is premature until Exp. 2 identifies which opportunity is real.
- **Strategic Narrative.** The shift ("robotic to human voices") was already claimed by ElevenLabs and Speechify. No new world-shift is available to this entrant beyond "private, on-device AI," which should be tested (Exp. 4) before it becomes a narrative.

---

## Sources

All evidence is drawn from:
- Voice Miner findings: `research/audio-anywhere/raw/voice-quotes.md`
- Competitor Profiler findings: `research/audio-anywhere/raw/competitor-data.md`
- Pricing Intel findings: `research/audio-anywhere/raw/pricing-data.md`
- Trend Detector findings: `research/audio-anywhere/raw/trends-data.md`
- Community Mapper: `research/audio-anywhere/raw/communities-found.md`
- Local/Platform context: `research/audio-anywhere/raw/local-context.md`
- Brief: `research/audio-anywhere/brief.md`

Assumptions marked [A] in section 9 are the analyst's and are not sourced in the raw data. Verify them with BLS occupational data and a short survey before using them in any deck.
