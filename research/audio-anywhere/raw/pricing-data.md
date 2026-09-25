# Pricing Intel — Audio Anywhere (AI TTS long-document reader, iOS-first)

**Date:** 2026-09-25 | **Agent:** Pricing Intel | **Depth:** Deep dive (constrained — see Method Limits)

## Method Limits (read first)
- The sandbox egress proxy blocked direct fetches of most primary pages (reddit.com, applevis.com, elevenlabs.io, elevenreader.io, aws.amazon.com, platform.openai.com, revenuecat.com, speechcentral.net). All figures below come from **search-result snippets** of official pages and 2026 third-party pricing trackers. Prices that could only be confirmed by a tracker are marked *(tracker)*. **Verify every API rate on the vendor page before building a financial model.**
- Reddit was not searchable (domain blocked), so the voice-of-customer quotes come from review aggregators, AppleVis/Perkins (accessibility community) and review blogs. The quote base is thinner than a deep dive should have; a manual Reddit pass (r/dyslexia, r/ADHD, r/Blind, r/productivity, r/speechify) is recommended.

---

## Competitor Pricing Landscape (US, consumer)

| Competitor | Offering | Price (USD) | Model | Includes / Limits |
|---|---|---|---|---|
| **Speechify** Premium | TTS reader (docs, PDF, web, OCR) | **$139/yr** (~$11.58/mo) or **$29/mo** | Sub; 3-day trial auto-converts to annual | Premium voices, OCR, speed up to 4.5x+, Chrome ext. Studio tier ~$288/yr. 50% student discount |
| **ElevenReader** Ultra | TTS reader + audiobooks catalog | **$11/mo or $99/yr** (cut ~50% in Feb 2026) | Freemium sub | **Free = 10 hrs/month** of ElevenLabs-quality audio; Ultra = unlimited TTS on imported files, offline, custom voices; free for students/educators for 1 yr |
| **NaturalReader** (personal) | TTS reader, web + apps | Lite $79/yr ($13.90/mo); Plus $119/yr ($20.90/mo); Pro $159/yr ($25.90/mo) | Freemium sub | Free: unlimited basic voices, ~20 min/day premium, ~5 min/day AI voices; Plus 500K chars/day |
| **Voice Dream Reader** | Accessibility-first TTS reader | $59.99/yr (reports of $79.99/yr now) | Sub (formerly one-time purchase) | Legacy buyers kept features after 2024 backlash |
| **Readwise Reader** | Read-it-later + TTS | $9.99/mo annual ($119.88/yr), $12.99/mo monthly | Sub | TTS is a feature within a broader reading/highlighting tool |
| **Instapaper Premium** | Read-it-later + TTS | $5.99/mo / $59.99/yr (doubled Dec 2023 from $2.99) | Freemium sub | Unlimited TTS playlists, permanent archive |
| **Matter** Premium | Read-it-later + HD TTS | $7.99/mo or $79.99/yr (App Store); $60/yr web | Freemium sub | HD TTS, highlights, integrations |
| **Audioread** | Web/email/PDF → podcast feed | $9.99/mo or $69.99/yr | Freemium sub | 100K words/conversion, 500K words/day |
| **Listening** (listening.com) | Academic papers → audio | ~$12–12.99/mo or $99/yr | Sub, 2-wk trial | Skips citations/footnotes for papers |
| **Pocket** | Read-it-later with TTS | **Shut down** July 8, 2025; export-only to Oct 8, 2025 | — | Orphaned users (large pool) migrated to Instapaper/Matter/Readwise |
| **Speech Central** | Budget TTS reader using system voices | ~$10 lifetime (per its own marketing) | One-time | Uses Apple/system voices |
| **Blinkist** (benchmark) | Book summaries (audio) | Premium ~$99.99/yr (intro $79.99); Pro ~$174.99/yr | Sub | Anchor for "audio learning" spend |
| **Audible** (benchmark) | Audiobooks | Premium Plus $14.95/mo; Standard $7.95–8.99/mo | Sub | Anchor for "audiobook-grade" expectations |
| Apple Spoken Content / Google Docs read-aloud | Built-in | Free | — | The status quo the founder finds inadequate |

**Price Range Summary**
- **Low end: $0–60/yr** — built-ins, Speech Central (lifetime ~$10), Instapaper $60, Voice Dream $60, ElevenReader free 10 h/mo.
- **Mid: $70–120/yr** — Audioread $70, NaturalReader Lite $79, Matter $80, ElevenReader $99, Listening $99, Readwise $120. **This is the dense band.**
- **Premium: $139–159/yr (monthly $20–29)** — Speechify, NaturalReader Plus/Pro. Justified by OCR, cross-platform, accessibility aids, and brand/ad spend.

**Key competitive fact:** ElevenLabs (which owns the best-regarded voice stack) prices its reader at $99/yr unlimited and gives away **10 hrs/month free**. A 20-page briefing is ~70 min, so a typical professional could process ~8 such docs/month free with ElevenReader. Any paid entrant must beat that free tier on *workflow* (Google Docs import, progress sync, long-doc reliability), not voice quality alone.

---

## Cost Side — TTS API Unit Costs (2025–2026)

Assumptions: 10,000 words ≈ 60,000 chars ≈ ~70 min audio (~857 chars/min). Heavy user = 20 h/mo = 1,200 min ≈ **1.03M chars/month**. Moderate user = 5 h/mo ≈ 0.26M chars.

| Provider / model | List price | Cost: 20-pg doc (60K chars / 70 min) | Cost: heavy user (20 h/mo) | Notes / source |
|---|---|---|---|---|
| **Apple AVSpeechSynthesizer** (enhanced/premium voices, Personal Voice) | $0 | $0 | $0 | On-device; premium voices need user download (100MB+ each); **Siri voices not available to 3rd-party apps**; iOS 26 regressions reported |
| **Kokoro-82M** on-device (CoreML/MLX) | $0 (Apache-2.0) | $0 | $0 | ~80MB INT8; ~3.3x real-time on iPhone 13 Pro; ANE build needs iOS 18+. Best open quality/size ratio for phones |
| Piper | $0 | $0 | $0 | No official iOS SDK; lower quality |
| Orpheus (150M–3B), Sesame CSM-1B | $0 (self-host GPU) | GPU cost | GPU cost | Server-class; not practical on-device for long-form in 2026 |
| Google Cloud Standard/WaveNet; Polly Standard | $4 / 1M chars | $0.24 | $4.12 | Robotic-ish — the quality users are fleeing |
| OpenAI **tts-1** | $15 / 1M | $0.90 | $15.45 | |
| Google **Neural2**; Polly **Neural**; Azure Neural | $15–16 / 1M | $0.96 | $16.48 | |
| **gpt-4o-mini-tts** (OpenAI) | ~$0.015/min audio (+$0.60/1M text tokens) | ~$1.06 | ~$18.00 | Steerable voice; billing by audio tokens |
| **Gemini 2.5 Flash TTS** | $10/1M output tokens @25 tok/s ≈ $0.015/min | ~$1.05 | ~$18.00 | Same effective rate as gpt-4o-mini-tts |
| **Azure Neural HD** | $22 / 1M (cut from $30, Mar 2026) | $1.32 | $22.66 | |
| OpenAI **tts-1-hd** | $30 / 1M | $1.80 | $30.90 | |
| Google **Chirp 3 HD**; Polly **Generative**; **Deepgram Aura-2** | $30 / 1M ($27 Aura-2 Growth) | $1.80 | $30.90 | Chirp 3 HD is the most "audiobook-like" of the hyperscalers |
| **Cartesia Sonic** | 1 credit/char; Scale $299/8M ≈ $37/1M; Pro $5/100K = $50/1M | $2.24–3.00 | $38–52 | *(tracker)* optimized for latency (agents) |
| **ElevenLabs Flash/Turbo v2.5** | ~$0.05/1K = $50/1M (PAYG API) | $3.00 | $51.50 | *(tracker)* |
| **ElevenLabs Multilingual v2 / v3** | ~$0.10/1K = $100/1M (Business overage ~$0.12/1K; Pro ~$0.24/1K) | $6.00 | $103 | *(tracker)*; best perceived quality |
| **Hume Octave** | ~$0.10/1K at Business ($900/mo for 10M chars ≈ $90/1M); one tracker claims $7.60/1M for Octave 2 (unverified) | ~$5.40–6.00 | ~$93–103 | *(tracker)*; conflicting data |
| Polly **Long-Form** | $100 / 1M | $6.00 | $103 | Designed for long-form narration |
| Google **Studio** | $160 / 1M | $9.60 | $165 | |
| **PlayHT** | — | — | — | **Dead.** Meta acqui-hired July 2025; API went dark ~July 26, 2025; fully shut Dec 31, 2025. Vendor-risk lesson |

Free tiers (useful for prototyping only): Google 1M chars/mo on Neural2/Chirp 3 HD/Studio (4M Standard); Polly 12-month free tier; Cartesia 20K credits.

---

## Unit Economics — Gross Margin After Apple

**Net revenue per subscriber per month**
| Plan | Apple 30% (yr-1 sub, >$1M proceeds) | Apple 15% (Small Business Program or yr-2+) |
|---|---|---|
| $9.99/mo | $6.99 | $8.49 |
| $99/yr | $5.78/mo | $7.01/mo |
| $49/yr | $2.86/mo | $3.47/mo |

(US link-out to web payment: currently no Apple commission pending a court-set fee per 2025–26 Epic rulings; reports conflict — treat as upside, not base case.)

**Gross margin by usage × voice cost (at $9.99/mo, 15% cut → $8.49 net)**
| Voice cost | Light 2 h/mo (0.10M chars) | Moderate 5 h/mo (0.26M) | Heavy 20 h/mo (1.03M) |
|---|---|---|---|
| On-device (Apple/Kokoro) $0 | ~100% | ~100% | ~100% |
| $4/1M (Standard) | 95% | 88% | 51% |
| $16/1M (Neural2/Polly Neural) | 81% | 51% | **−94%** |
| $18/1M-eq (gpt-4o-mini-tts / Gemini Flash TTS) | 78% | 45% | **−112%** |
| $30/1M (Chirp 3 HD / tts-1-hd / Aura-2) | 64% | 8% | **−264%** |
| $50/1M (ElevenLabs Flash) | 39% | **−53%** | **−507%** |
| $100/1M (ElevenLabs v2/v3, Polly Long-Form) | **−21%** | **−206%** | **−1,113%** |

**At $49/yr (net ~$3.47/mo at 15%)** the break-even usage for a $30/1M voice is only ~0.12M chars ≈ **2.2 h/month** — about two 20-page docs. At $99/yr (net ~$7.01) break-even for $30/1M ≈ 4.5 h/month; for ElevenLabs v3 ≈ 1.4 h/month.

**Implications**
1. **"Unlimited" + premium cloud voice is not viable at $49–139/yr** for anyone listening >4–5 h/month. ElevenReader can offer $99/yr unlimited only because it owns the model (marginal cost well below list API rates). Speechify likewise runs its own voices.
2. **Viable architectures:** (a) **on-device default** (Kokoro-82M/Apple premium voices) with unlimited use + **metered cloud "studio" hours** (e.g., 5–10 h/mo included, top-ups); (b) cloud mid-tier ($15–30/1M) with a monthly hour cap; (c) cache/generate once per document and reuse (re-listens are free; progress-saving makes re-listens common).
3. **Vendor risk:** PlayHT's sudden death means abstraction over ≥2 providers is required.
4. The API price curve is falling (Azure HD −27% in 2026, ElevenReader −50%, Gemini/OpenAI at ~$0.015/min), so cost will ease — but so will incumbents' prices.

---

## Economic Context (US subscription app benchmarks)

**RevenueCat State of Subscription Apps 2026** (115K+ apps, $16B revenue):
- Trial conversion: trials 17–32 days convert at median **42.5%**; trials <4 days at **25.5%**. 55% of 3-day-trial cancellations happen on Day 0.
- North America median Day-35 **download-to-paid 2.6%**.
- Hard paywall vs freemium (education): **10.7% vs 2.1%** conversion, but 1-year retention nearly identical.
- **Productivity: lowest median annual renewal rate of any category, ~23%** (top categories ~40%). Median productivity annual price ~$24.95; education ~$22.82.
- Median realized LTV per payer after year 1: **$32 North America**, $23 global.
- 57.7% of new apps never reach $1,000 total revenue; growth concentrating in top apps. AI-powered apps show weaker long-term retention (TechCrunch, Mar 2026).
- 2025 report (prior year) showed similar patterns; 2026 figures supersede.

**Takeaway:** Plan for ~2–3% install-to-paid, 25–45% trial conversion, and heavy annual churn (productivity renewals ~23%). A $99/yr sub realistically yields ~$32 LTV per payer in year 1 in NA median terms — CAC must be well below that.

### Payment Infrastructure
| Method | Adoption | Notes |
|---|---|---|
| Apple IAP subscriptions | High (default on iOS) | 30% yr-1 / 15% yr-2+ or SBP (<$1M proceeds) |
| US web checkout via link-out | Growing | Commission currently 0% pending court fee; conversion friction vs IAP |
| Education/institutional licenses | Med | Speechify & ElevenReader use student discounts; DSA/accessibility budgets exist in schools |

---

## Price Sensitivity Analysis

### "Too Expensive" Signals
> "The voices sound genuinely human, and the Chrome extension alone is worth it. That said, it's not cheap at $139/year, and the free version is too limited to be useful long-term."
> — Speechify user review, aggregated (https://computertech.co/speechify-review/ ; https://www.roborhythms.com/speechify-review-2026/)

> "It's not worth it especially given the asking price."
> — AppleVis user on Voice Dream Reader's $59.99/yr sub (https://www.applevis.com/comment/165288)

> Expects "considerably more than we get — and considerably more than just continuing to work" for £59 per year.
> — AppleVis user on Voice Dream renewal (https://www.applevis.com/forum/ios-ipados/voicedream-renew-or-not-renew)

> Reddit threads describe Speechify pricing as "expensive" and a "nightmare"; 3-day trial auto-converts to ~$139 annual; F rating at BBB with 80+ billing complaints; users report steep discounts only after trying to cancel.
> — Aggregated in https://costbench.com/software/ai-voice-tools/speechify/ and https://texttolab.com/blog/speechify-pricing

> Voice Dream's 2024 forced switch from paid-up-front to $79/yr triggered a backlash and a reversal; the user base "skews heavily toward folks who are blind, visually impaired, or have print disabilities."
> — Six Colors / Perkins (https://sixcolors.com/link/2024/04/another-app-switches-to-a-subscription-model/ ; https://www.perkins.org/resource/voice-dream-reader-subscription-controversy/)

> Speech Central markets "unlimited use for $10 lifetime" directly against ElevenReader's "$100/year subscription with strict limits."
> — https://speechcentral.net/2025/05/13/elevenreader-introduces-100-year-subscription-with-strict-limits-speech-central-offers-unlimited-use-for-10-lifetime/

### "Worth It" Signals
> "If you read a lot of digital content, it's worth every penny." / "The pricing is reasonable at $139 per year if you use it daily."
> — Speechify reviewers (https://www.fahimai.com/speechify ; https://www.voicepodai.com/guides/is-speechify-worth-it)

> Users with dyslexia and ADHD report transformative value that justifies the cost.
> — Speechify review aggregation (https://checkthat.ai/brands/speechify/reviews)

> "There are actually more expensive apps that do less. So pricing wise it is fair." / "It costs to keep an app going."
> — AppleVis users defending Voice Dream (https://www.applevis.com/comment/165288)

> "For voice quality that actually sounds human, ElevenReader (free for 10 hrs/month) blows Speechify away."
> — https://texttolab.com/blog/speechify-alternatives

### Price Anchors
- **Free built-ins** (iOS Spoken Content, Google Docs read-aloud) — the default comparison; users pay only when quality/reliability fails.
- **ElevenReader free 10 h / $99 unlimited** — the new quality anchor; it undercuts Speechify by ~30%.
- **Speechify $139/yr** — the "expensive" reference point.
- **Audible $14.95/mo, Blinkist ~$100/yr** — "audio learning" spend norms.
- **Instapaper $60/yr, Matter $80/yr** — read-it-later + TTS bundles.
- **One-time purchase** (legacy Voice Dream, Speech Central) — accessibility users strongly prefer ownership.

---

## Value Drivers
What justifies higher prices:
1. **Human-sounding voices for hour-plus listening** — the #1 cited reason to pay (Speechify, ElevenReader reviews).
2. **Accessibility necessity** (dyslexia/ADHD/low vision) — "transformative" language, highest WTP but also highest sensitivity to perceived exploitation.
3. **Workflow coverage** — OCR, cross-device, Chrome extension, cloud file import (Speechify "extension alone justifies").
4. **Specialized content handling** — Listening charges $99/yr for skipping citations in papers.

What destroys value perception:
1. **Dark-pattern billing** (auto-converting 3-day trials into annual, hard cancellation) — Speechify BBB F rating.
2. **Taking away paid-for functionality** — Voice Dream backlash.
3. **Hard usage caps presented as "unlimited"** — Speech Central attacks ElevenReader's limits.
4. **Audio locked in the app / no desktop** — ElevenReader complaints.

---

## WTP Estimate

**Recommended price range:** **$59–99/yr** (monthly $7.99–9.99), with a free tier driven by on-device voices.

**Rationale**
- Lower bound: Instapaper/Voice Dream at ~$60; below this, a solo app can't fund acquisition (NA median payer LTV ~$32 yr-1).
- Upper bound: ElevenReader Ultra $99/yr unlimited with the best voices. Pricing above $99 requires Speechify-level breadth (OCR, extension, desktop) that MVP1 won't have.
- **Sweet spot: ~$69–79/yr / $8.99 mo**, positioned under ElevenReader and Speechify, with a **long (14–30 day) trial** (RevenueCat: 42.5% conversion for 17–32 day trials).

**Pricing model recommendation:** Hybrid subscription — unlimited on-device voice (Kokoro/Apple premium) + a monthly allotment of cloud "studio" hours (e.g., 5–8 h/mo at ≤$30/1M-char vendors ≈ $1.60–2.50 COGS), with paid top-ups. Consider a one-time/lifetime tier for accessibility users (defuses the Voice Dream backlash dynamic) and a student discount (both incumbents offer one).

**Payment considerations**
- Enroll in Apple Small Business Program (15%) from day one.
- Offer US web checkout via link-out as the cost of IAP drops margin by ~15 pts.
- Transparent trial reminders — explicit anti-Speechify positioning on billing honesty is itself a differentiator.

**Adversarial note (H4):** WTP clearly exists (Speechify, NaturalReader, Readwise sustain $80–160/yr), but the premium-voice value prop has been **commoditized by ElevenReader's free 10 h/mo**, and productivity-app annual renewals (~23%) are the worst of any category. A paid long-doc reader must win on reliability/workflow, not voice, and cannot afford premium cloud voices on unlimited plans.

---

## Sources
- Speechify pricing: https://costbench.com/software/ai-voice-tools/speechify/ ; https://texttolab.com/blog/speechify-pricing ; https://fluxnote.io/guides/speechify-pricing-guide-2026
- ElevenReader: https://elevenreader.io/pricing ; https://elevenreader.io/blog/best-pricing-more-value ; https://help.elevenlabs.io/hc/en-us/articles/35971782968465-How-do-ElevenReader-hours-work ; https://x.com/elevenreader/status/1996589050816315627
- NaturalReader: https://help.naturalreaders.com/en/articles/8854700-plans-pricing-personal-version
- Voice Dream: https://sixcolors.com/link/2024/04/another-app-switches-to-a-subscription-model/ ; https://www.perkins.org/resource/voice-dream-reader-subscription-controversy/ ; https://www.applevis.com/comment/165288 ; https://www.applevis.com/forum/ios-ipados/voicedream-renew-or-not-renew ; https://mjtsai.com/blog/2024/04/08/voice-dream-reader-switches-to-subscriptions/
- Readwise Reader: https://readwise.io/pricing/reader
- Matter: https://gleamr.io/blog/matter-app-pricing-2026 ; https://www.getmatter.com/patron
- Instapaper: https://9to5mac.com/2023/12/05/instapaper-price-increase-new-features/ ; https://blog.instapaper.com/post/735784644474208256/permanent-archive-and-premium-price-change
- Pocket shutdown: https://techcrunch.com/2026/08/14/read-it-later-app-pocket-is-shutting-down-here-are-the-best-alternatives/ ; https://www.techradar.com/computing/websites-apps/mozilla-is-shutting-down-pocket-here-are-the-3-best-bookmarking-alternatives
- Audioread: https://audioread.com/pricing
- Listening: https://www.listening.com/pricing
- Blinkist / Audible: https://nibble-app.com/blog/blinkist-cost ; https://www.dealnews.com/features/audible/cost/
- Speech Central: https://speechcentral.net/2025/05/13/elevenreader-introduces-100-year-subscription-with-strict-limits-speech-central-offers-unlimited-use-for-10-lifetime/ ; https://speechcentral.net/2026/08/08/why-cant-third-party-apps-use-siri-voices-on-iphone-ipad-and-mac/
- Google Cloud TTS: https://cloud.google.com/text-to-speech/pricing ; https://texttolab.com/blog/google-cloud-tts-pricing
- OpenAI TTS: https://developers.openai.com/api/docs/models/gpt-4o-mini-tts ; https://costgoat.com/pricing/openai-tts ; https://community.openai.com/t/new-tts-api-pricing-and-gotchas/1150616
- Gemini TTS: https://ai.google.dev/gemini-api/docs/pricing ; https://mxchat.ai/gemini-tts-pricing-tokens-per-second/
- Amazon Polly: https://aws.amazon.com/polly/pricing/ ; https://costbench.com/software/ai-voice-tools/amazon-polly/
- Azure: https://azure.microsoft.com/en-gb/pricing/details/speech/ ; https://techcommunity.microsoft.com/blog/azure-ai-foundry-blog/azure-speech-%E2%80%93-neural-hd-text-to-speech-recent-voice-updates/4505380
- ElevenLabs API: https://elevenlabs.io/pricing/api ; https://flexprice.io/blog/elevenlabs-pricing-breakdown ; https://texttolab.com/blog/elevenlabs-pricing
- Cartesia: https://texttolab.com/blog/cartesia-pricing ; https://www.eesel.ai/blog/cartesia-sonic-3-pricing
- Deepgram: https://deepgram.com/pricing ; https://texttolab.com/blog/deepgram-pricing
- Hume: https://www.hume.ai/octave ; https://autogpt.net/hume-ai-pricing-every-plan-explained/
- PlayHT shutdown: https://texttolab.com/blog/play-ht-shutdown-alternatives ; https://inworld.ai/resources/migrate-from-playht
- On-device: https://github.com/mlalma/kokoro-ios ; https://huggingface.co/aufklarer/Kokoro-82M-CoreML ; https://huggingface.co/mattmireles/kokoro-coreml ; https://picovoice.ai/blog/on-device-tts/ ; https://developer.apple.com/documentation/avfaudio/avspeechsynthesisvoicequality/premium ; https://bendodson.com/weblog/2024/04/03/using-your-personal-voice-in-an-ios-app/ ; https://developer.apple.com/forums/thread/804648
- RevenueCat: https://www.revenuecat.com/state-of-subscription-apps ; https://www.revenuecat.com/blog/growth/subscription-app-trends-benchmarks-2026 ; https://www.revenuecat.com/state-of-subscription-apps-2026-productivity/ ; https://www.revenuecat.com/blog/growth/average-subscription-renewal-rates-by-app-category ; https://techcrunch.com/2026/03/10/ai-powered-apps-struggle-with-long-term-retention-new-report-shows
- Apple commission: https://developer.apple.com/app-store/small-business-program/ ; https://www.revenuecat.com/blog/engineering/small-business-program ; https://blog.funnelfox.com/apple-app-store-fees-2026-eu-dma/
