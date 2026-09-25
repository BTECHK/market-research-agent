# Business Models, Cost Stack, Self-Hosting & Ads — Audio Anywhere

**Date:** 2026-09-25 | **Agent:** Business-model follow-up | **Depth:** Thorough (constrained)
**Builds on:** `pricing-data.md` (API unit costs, Apple-cut margin tables) and `competitor-data.md` (Speechify, Speech Central, Voice Dream profiles). Numbers already there are not re-derived.

## Method limits (read first)
- WebFetch was blocked for most primary sites (docs.digitalocean.com, reddit, revenuecat etc.). Most figures come from **search-result snippets**. Two primary pages were fetched in full: the Kokoro v1 benchmark gist and the obole-ia CPU benchmark repo.
- Labels used below: **[V]** = seen on the vendor/primary page or its snippet. **[T]** = third-party tracker or blog. **[A]** = my assumption or derivation. **[U]** = unverified or conflicting.
- Conversion constant (from pricing-data.md): ~857 chars/min, so **1 hour of audio ≈ 51,400 chars** and **1M chars ≈ 19.5 hours of audio**.
- **API cost per audio hour:** $15/1M ≈ **$0.77/h**, $30/1M ≈ **$1.54/h**, ElevenLabs $50–100/1M ≈ **$2.57–5.14/h**.

---

## 1. Why $80–160/yr when Speech Central is $9.99 one-time?

### Cost stack of a Speechify-style $139/yr subscriber [A unless marked]

| Line item | $/payer/yr | Basis |
|---|---|---|
| Apple/Google fee | $20.85 (15%) to $41.70 (30%) | 30% in year 1 for developers with more than $1M in proceeds. 15% under the Small Business Program or from year 2 of a subscription. US link-out commission is still unresolved: Apple's plan charged 27%, the 9th Circuit said "some commission" is allowed, and the Supreme Court granted cert on 30 Jun 2026 [V] |
| Refunds | ~$3–7 (2–5%) | Subscription average ~4%. Utilities ~2.1%, education 3.8–5.1% [T] |
| TTS inference (own models) | ~$15 for a 5 h/mo user; ~$60 for a 20 h/mo user | Speechify says its inference cost is "single-digit dollars per million chars" [V, CEO claim]. I used $5/1M. Usage levels are [A] |
| Paid acquisition (CAC per payer) | **$50–300** one-time | US iOS CPI is $4.06 (Apple Ads, Oct 2025) to $5.84 (Q1 2026, all channels) [T]. Install-to-paid is a 1.7% median, or 6–20% with an optimized hard paywall [T]. So $5 ÷ 0.10 = $50 per payer, and $5 ÷ 0.017 = $294 |
| Creative production (Speechify) | $6M/yr fixed | Speechify spends $500K/mo on creative testing, tests about 1,300 AI ads/day, and produces about 8,000 human-made creatives/month [V, CEO on 20VC]. **Media spend is not disclosed** |
| Staff | ~$24M/yr fixed [U] | About 160 employees × an assumed $150K loaded cost |
| Servers/storage | Small next to inference | [A] |

**Reading it:**
- **Acquisition is the dominant variable cost, not TTS.** RevenueCat puts the North America median first-year realized LTV at **$32 per payer**. At a CAC of $50–300, a median-priced app cannot pay for paid UA. High sticker prices ($139) combined with annual-only prepay, 3-day trials that auto-convert, and hard paywalls are what make Meta/TikTok ROAS work.
- Rules of thumb for consumer apps: growth-phase apps spend 30–60% of revenue on marketing and mature apps 15–25% [T, low-quality blogs]. Duolingo is a counterexample: it relies on organic/brand growth and spent **12.1% of revenue on S&M in 2025** ($125.7M of $1.04B) [V, 10-K].
- **Speechify's revenue is inconsistent across sources.** Latka's $17.6M ARR [T] cannot cover 160 staff plus $6M/yr of creative and still be "profitable for 4.5 years." That supports the $30–100M+ estimate in competitor-data.md. Creative alone is therefore 6–34% of revenue, depending on which revenue figure is right [A].
- **Price is set by value and anchoring, not by cost.** For a 5 h/mo user, TTS inference is about 10% of the $139 sticker price. Evidence of price discrimination: a 50% student discount, heavy discounts offered only when a user tries to cancel, and an F rating at the BBB with 80+ billing complaints (competitor/pricing-data). The institutional anchors are high: Read&Write individual **$170/yr**, Kurzweil 3000 **$500/yr individual** and **$4,000/site** [T]. UK DSA-funded buyers are not price-sensitive: 86,000+ ClaroRead licences went through DSA/ATW [V, Everway]. Caveat: the DfE has **proposed stripping most assistive software out of DSA** [V, Wonkhe], which is a risk to that channel.

### How Speech Central affords $9.99 one-time
- **$0 marginal voice cost.** It uses on-device system voices, so there is no cloud inference [V].
- **No subscription and no ads.** The free tier is limited by quantity, not quality [V, speechcentral.net snippet]. The Pro add-on is a one-time purchase.
- **Tiny team.** Labsii Ltd / Ivan Icin [V] (the brief said "Ilijasic"; the correct name is Icin). The app has existed for about 10 years on Android and iOS.
- **No evidence of paid UA** [U]. It grows through the accessibility community (AppleVis, Perkins), SEO blog posts attacking ElevenReader and Voice Dream, and a free-for-VoiceOver-users and free-in-schools policy that builds goodwill.
- **Net economics.** $9.99 × 0.85 = $8.49 once per payer. That is viable only with CAC close to $0 and costs that are almost entirely fixed. Revenue scale is unknown [U].
- **Lesson:** the $9.99 price is possible because of what the app does *not* have: no cloud voices, no paid acquisition, no large staff. It says nothing about what a cloud-voice app can charge.

---

## 2. Self-hosting TTS on cheap infrastructure

### Infrastructure prices (2026)

| Provider / SKU | Price | Source |
|---|---|---|
| DO GPU Droplet RTX 4000 Ada (20GB) | $0.76/GPU-h (~$555/mo always-on) | [T] computeprices; DO blog announced the SKU |
| DO RTX 6000 Ada / L40S (48GB) | $1.57/GPU-h each | [T] |
| DO H100 | $4.41/GPU-h (H200 $4.47). Reserved pricing $1.91–7.94 | [T] "as of Aug 1 2026". **[U]** DO earlier advertised a lower H100 rate, so check the vendor page |
| DO CPU-Optimized c-8 (8 dedicated vCPU / 16GB) | $168/mo (~$0.23/h). Per-second billing since 1 Jan 2026 | [T] |
| Hetzner GEX44 (RTX 4000 SFF Ada 20GB, dedicated) | €184/mo + €79 setup (~$215/mo) | [V] Hetzner press release |
| Hetzner CCX33 (8 dedicated vCPU/32GB) | €138.49/mo (€0.22/h) after the June 2026 increase, which raised some CCX plans up to +176% | [V] Hetzner docs / [T] |
| RunPod RTX 4090 | $0.34 (community) to $0.69 (secure) /h. L40S $0.79/h | [T] |
| Vast.ai RTX 4090 | from $0.29/h, typically $0.39/h (marketplace, variable reliability) | [T] |

### Model throughput and cost per unit

These are single-stream benchmarks unless noted. Batching raises GPU throughput. Cost per unit assumes **100% utilization**; real costs are 2–5× higher (see ops burden below).

| Model (license) | Hardware / RTF | $/audio-hour | $/1M chars | Notes |
|---|---|---|---|---|
| **Kokoro-82M** (Apache-2.0) GPU | T4 36×, A10G 96×, L4 81× real-time (PyTorch) [V, gist]. 4060Ti 35–50× [V, Kokoro-FastAPI] | ~$0.01 on DO RTX 4000 at ~80× [A: assumes L4-class] | **~$0.18** (about $0.37 at 50% utilization) | Hosted Kokoro APIs cost **$0.65 (Replicate) and $0.80 (DeepInfra) per 1M** [T], which is consistent |
| Kokoro-82M CPU | 2 ARM cores **0.87×** (slower than real time) [V, obole-ia]. 32-vCPU c6a.8xlarge **5×** [V, gist]. M3 Pro ~6× [T] | $0.07–0.19 on DO c-8 (~1.25–3.5×) [A] | **$1.4–3.7** | CPU costs about 10× more than GPU per character |
| **Piper** (code MIT; **each voice has its own license**) CPU | RTF 0.12–0.22 on 2 ARM threads (4.5–8× RT) [V, obole-ia]. ~0.19 on Colab [T] | ~$0.01 on c-8 (~18–32× with parallel processes) [A] | **~$0.15–0.27** | Lower quality. Some voices derive from the Blizzard/lessac dataset, which is **research-only**. Check each MODEL_CARD [V, piper discussion #271] |
| **Orpheus 3B** (code Apache-2.0; **weights under the Llama 3.2 Community License**) GPU | Half an H100 (MIG): 16–24 real-time streams, 128 concurrent non-real-time generations [V, Baseten]. A full H100 supports 25+ streams [T] | ~$0.05–0.11 on DO H100 (40–100× aggregate) [A] | **~$0.9–2.1** | The brief's "Orpheus Apache" is only half right: the Llama license adds attribution and a 700M-MAU clause |
| **Chatterbox** (MIT) GPU | ~6× RT; streaming RTF 0.499 on a 4090 [T] | $0.06–0.35 (RunPod 4090) / ~$0.26 (DO RTX 6000 Ada) | **~$1.1–6.7** | Good quality/license combination. No batch benchmarks found |
| **F5-TTS** GPU | RTF 0.15 on a 3090 [V, paper] | — | — | **Weights CC-BY-NC (Emilia dataset): not usable commercially** |
| **XTTS-v2** GPU | ~150–400 ms first audio [T] | — | — | **CPML, non-commercial only.** Coqui shut down in Jan 2024, so **a commercial license cannot be bought** [T, multiple] |

**Comparison per audio hour:**

| Option | $/audio-hour |
|---|---|
| On-device (Apple / Kokoro CoreML) | **$0** |
| Self-hosted Kokoro | ~$0.01–0.04 |
| Self-hosted Orpheus / Chatterbox | ~$0.05–0.35 |
| Mid-tier API ($15–30/1M) | $0.77–1.54 |
| ElevenLabs | $2.57–5.14 |

Self-hosting a premium-class open model comes out **about 5–30× cheaper than a mid-tier API**.

**Kokoro provenance caveat [V, HF card]:** part of Kokoro's training data is "synthetic audio generated by closed TTS models from large providers." That may conflict with those providers' terms of service. The legal risk is low but not zero.

### Ops burden (why the per-hour cost is misleading)
- **The idle floor dominates at small scale.** One always-on GPU costs $215/mo (Hetzner GEX44) to $555/mo (DO RTX 4000). At a realistic 20% utilization, one Kokoro GPU produces about 11,700 audio-h/mo, enough for about 2,300 users at 5 h/mo, or about $0.09–0.24 per user per month [A]. With only 100 users, the same box costs $2–5.50 per user per month, which is worse than an API.
- **Autoscaling GPUs is slow.** Cold starts are minutes long (Droplet boot plus model load). Scale-to-zero forces a choice: users wait in a queue on the first document, or you keep one warm node running.
- **Queueing latency.** Long documents should be pre-rendered in chunks with the first chunk streamed. Orpheus needs about 83 tokens/s per stream to keep up with real time [T].
- **Hetzner's 2026 price increases** (three rounds; CCX up to +176%) show that "cheap infrastructure" pricing can change [V/T].
- **Recommendation [A]:** start on hosted Kokoro/Orpheus APIs ($0.65–0.80/1M, no idle cost). Move to a dedicated GEX44-class box only when sustained load exceeds about 300–700 audio-h/day.

---

## 3. Business models

| Model | Who does it (evidence) | Pros | Cons / revenue implication |
|---|---|---|---|
| **One-time / lifetime** | Speech Central $9.99 Pro [V]. Voice Dream was originally about $9.99 one-time [T]; its 2024 forced move to $59.99→$79.99/yr caused a backlash and a partial reversal [V] | Trusted by accessibility users. No churn. A marketing weapon against subscriptions | No recurring revenue to pay cloud COGS or paid UA. Works only with on-device voices and organic growth. Lifetime purchases pull future revenue forward |
| **Freemium: free on-device tier + paid premium voices** | ElevenReader: free 10 h/mo, Ultra $11/mo or $99/yr. NaturalReader: free basic voices, limited AI minutes (pricing-data) | Free tier costs about $0 to serve. Upgrade path is clear | Freemium converts at a **2.1%** Day-35 median vs **10.7%** for hard paywalls [V, RevenueCat 2026]. Needs volume |
| **Usage credits / top-ups** | ReadBack (subscription or pay-as-you-go credits), SpeechGen, TTSReader, NaturalReader commercial credits [V]. ElevenLabs credits are 1 per character, but PAYG credits cannot be bought through an app-store subscription [V] | COGS matches revenue exactly. Suits irregular listeners (students at exam time) | Apple consumable IAP takes 15–30% of each top-up. "Meter anxiety" reduces listening. Revenue is lumpy |
| **Low-price subscription ($2.99–4.99/mo)** | **No direct TTS-reader example found [U].** Nearest: Voice Dream Mac $49.99/yr; Instapaper and Listening about $60/yr | Easy impulse purchase. Undercuts the $99–139 anchors | Net $2.10–4.24/mo. At a CAC of $50+, payback takes 12–24 months, so this **only works with organic growth**. Cloud break-even at $30/1M is about 2.2 h/mo (pricing-data) |
| **Bring your own API key** | Spoken AAC (ElevenLabs key) [V]. Common in desktop/open-source tools | Zero COGS. Power users get the best voices at cost | A niche (few consumers have API keys). Onboarding friction. Key custody and security issues. Low willingness to also pay for the app. App Review treatment is **[U]** |
| **Ad-supported free tier** | MWM Voice Aloud Reader (iOS, occasional ads + $9.99 subs + $1.99/800 scans) [T]. Hyperionics @Voice (Android, free with ads + premium) [T]. Easy Text to Speech Reader (ads; separate Pro app) [V] | Monetizes users who won't pay | See section 4: roughly $0.01–0.05 per listening hour. Hostile to accessibility users. Undermines privacy positioning |
| **B2B / edu site licenses** | Read&Write: individual $170/yr, K-12 group $17.25/license, **district $2.60 per enrolled student** [T]. Kurzweil 3000: $500/yr individual, $2,000/10 users, $4,000 site [T]. Speech Central is free when deployed as a managed app in schools [V] | Large contracts. Low churn. Funded budgets (IDEA/504, UK DSA) | Long sales cycles. Needs SSO/MDM, VPAT, and data-privacy agreements. DSA software funding is under threat [V] |
| **Family plans** | **Neither Speechify nor ElevenReader offers one.** ElevenReader bans account sharing [V]. Apple Family Sharing supports subscriptions if the developer opts in [A] | Clear differentiation for households (a dyslexic child plus parents). Nearly free with on-device voices | Cannibalizes individual subscriptions. Cloud COGS per account multiplies |

---

## 4. Ads: can they offset costs?

### Benchmarks (US, 2025–26)

| Ad type | eCPM / rate | Source |
|---|---|---|
| Banner | ~$0.50 US (the top country) | [T] |
| Interstitial | ~$13.60 iOS North America. $12.65 US across both platforms. iOS interstitial eCPMs fell in Q4 2025 | [T] Bidlogic/Maf |
| Rewarded video | $15–40 tier-1 (AppLovin publisher benchmarks via a blog) | [T/U] |
| Audio (advertiser price) | Spotify self-serve $15–25 CPM, range to $40. Podcasts $18–50 | [T] |
| Spotify ad load | ~2–3 min of ads per listening hour; a 15–30s spot every 15–20 min | [T] |
| Utility/productivity ARPDAU | $0.01–0.03 | [T] Perkox 2026 |
| Productivity revenue mix | ~10% ads / 90% subscription | [T] |
| ATT opt-in | ~25–27% overall. Utilities are "mid-tier". No clean category number found | [V] Adjust/IAPP, [U] |

### Ad revenue per listening hour [A]
- **Display (banner, interstitial, rewarded).** Listening happens with the screen locked, so display ads earn impressions only when the user opens the app. Assume one interstitial per document open plus about 20 banner impressions:
  - Interstitial: $13.60/1000 = $0.0136
  - Banners: 20 × $0.0005 = $0.01
  - Total ≈ **$0.01–0.03 per hour** (for a document that takes one hour to listen to).
- **Rewarded unlock** ("watch 30s to unlock 1 hour of premium voice"): $0.015–0.03 per view. This covers self-hosted Kokoro ($0.01–0.04/h) or Orpheus at best ($0.05+). It **does not cover a $15–30/1M API ($0.77–1.54/h) by 25–100×**.
- **Audio ads inserted between chunks.** About 5 × 30s spots per hour × $20 CPM = $0.10 gross. After fill rate (50–70%) and the network's take (30–50%), that is **~$0.03–0.05 net per hour** [A/U]. An indie app has no direct access to Spotify-grade audio demand; third-party audio SDKs exist, but their rates were not verified.
- **Conclusion:** ads can pay for **on-device or self-hosted-Kokoro** listening. They cannot pay for cloud premium voices. At a utility-class ARPDAU of $0.01–0.03, an ad-funded user earns **$0.30–0.90/mo**, versus about $3–8/mo net from a subscriber.

### Conflicts
- **Accessibility.** Interstitials break VoiceOver focus and navigation. Blind users are the core evangelists for this category, and the category leader in trust (Speech Central) is **free for VoiceOver users with no ads**. Showing ads to that segment would damage reputation [A, grounded in the Voice Dream backlash].
- **Privacy positioning.** With only ~25–27% ATT opt-in, most users get non-personalized, lower-eCPM ads anyway. Ad SDKs also mean App Privacy "tracking" labels, which contradict a "private, on-device" pitch.
- **Precedent.** The template-style "TTS reader" apps from studios (MWM and others) use ads plus subscriptions. Premium competitors (Speechify, ElevenReader, NaturalReader, Voice Dream, Speech Central) do **not** use ads, based on listings/snippets [T].

---

## Sources
- Speechify 20VC / ads: https://speechify.com/news/speechify-ceo-cliff-weitzman-20vc-podcast/ ; https://finance.biggo.com/news/82a0b4613f50dfa4 ; https://app.dealroom.co/news/note/1-000-ai-ads-a-day-and-tokens-over-salaries-inside-speechify-s-playbook-for-owning-the-voice-ai-market ; https://getlatka.com/companies/speechify.com
- UA/CPI: https://www.apptweak.com/en/aso-blog/apple-ads-benchmarks ; https://ideaequity.ai/blog/cost-per-install-benchmarks-2026 ; https://www.digitalapplied.com/blog/mobile-app-marketing-statistics-2026-install-data ; https://www.airbridge.io/en/blog/roas-for-subscription-apps ; https://semnexus.com/mobile-app-marketing-budget-benchmarks-by-vertical-2026 ; https://www.sec.gov/Archives/edgar/data/1562088/000162828026012494/duol-20251231.htm
- RevenueCat 2026: https://www.revenuecat.com/state-of-subscription-apps ; https://www.revenuecat.com/blog/growth/subscription-app-trends-benchmarks-2026
- Refunds: https://www.businessofapps.com/data/app-refund-rates/ ; https://adapty.io/blog/refund-rate-metrics-and-benchmarking/
- Apple link-out: https://www.sec.gov/Archives/edgar/data/0000320193/000032019326000020/aapl-20260627.htm ; https://www.fenwick.com/insights/publications/ninth-circuit-largely-upholds-ruling-in-epic-v-apple
- Speech Central: https://speechcentral.net/ ; https://speechcentral.net/2023/08/09/finding-a-premium-text-to-speech-app-with-no-subscription-is-it-possible/ ; https://www.perkins.org/resource/speech-central-update/
- Voice Dream: https://www.perkins.org/resource/voice-dream-reader-subscription-controversy/ ; https://applevis.com/forum/ios-ipados/voice-dream-reader-ios-now-5999year
- DO GPU: https://www.digitalocean.com/blog/now-available-nvidia-rtx4000-6000ada ; https://computeprices.com/providers/digitalocean ; https://www.digitalocean.com/pricing/droplets ; https://github.com/bvjhs91/digitalocean-cpu-optimized-droplets
- Hetzner: https://www.hetzner.com/pressroom/new-gpu-server/ ; https://docs.hetzner.com/general/infrastructure-and-availability/price-adjustment/ ; https://northflank.com/blog/hetzner-cloud-server-price-increases
- RunPod/Vast: https://www.runpod.io/gpu-models/rtx-4090 ; https://www.synpixcloud.com/blog/vast-ai-vs-runpod-rtx-4090-pricing ; https://tech-insider.org/runpod-vs-lambda-vs-vast-ai-2026/
- Kokoro: https://gist.github.com/efemaer/23d9a3b949b751dde315192b4dcf0653 ; https://github.com/obole-ia/tts-cpu-benchmark ; https://github.com/remsky/Kokoro-FastAPI ; https://huggingface.co/hexgrad/Kokoro-82M ; https://openrouter.ai/hexgrad/kokoro-82m ; https://deepinfra.com/hexgrad/Kokoro-82M
- Piper: https://github.com/rhasspy/piper/discussions/271 ; https://huggingface.co/rhasspy/piper-voices
- Orpheus: https://www.baseten.co/blog/canopy-labs-selects-baseten-as-preferred-inference-provider-for-orpheus-tts-model/ ; https://github.com/canopyai/Orpheus-TTS ; https://www.openspeech.dev/models/orpheus-tts
- Chatterbox: https://github.com/davidbrowne17/chatterbox-streaming ; https://www.resemble.ai/learn/models/chatterbox-turbo
- F5 / XTTS: https://github.com/swivid/f5-tts ; https://github.com/coqui-ai/TTS/issues/3490 ; https://localaimaster.com/blog/xtts-coqui-commercial-license
- Edu: https://www.everway.com/products/read-and-write-education/pricing/ ; https://speechify.com/blog/kurzweil-3000-pricing/ ; https://www.everway.com/en-gb/govt-grant-schemes/what-is-dsa/claroread/ ; https://wonkhe.com/blogs/dfe-proposes-to-strip-most-assistive-software-out-of-disabled-students-allowance/
- Credits/BYOK/family: https://apps.apple.com/us/app/readback-text-to-speech/id6747597136 ; https://speechgen.io/en/pricing/ ; https://help.elevenlabs.io/hc/en-us/articles/40263026676753-How-do-credits-work-on-the-ElevenLabs-iOS-or-Android-app ; https://spokenaac.com/help/how-to-get-elevenlabs-api-key/ ; https://elevenlabs.io/docs/help-center/product/mobile-apps/eleven-reader/can-i-share-my-eleven-reader-account-with-others
- Ads: https://bidlogic.io/2026/01/30/what-happened-to-mobile-app-ecpms-in-q4-2025/ ; https://maf.ad/en/blog/mobile-ads-ecpm/ ; https://coinis.com/glossary/rewarded-video ; https://www.stackmatix.com/blog/how-much-do-spotify-ads-cost ; https://freeyourmusic.com/blog/spotify-free-vs-premium ; https://blog.perkox.com/2026/08/arpdau-benchmarks-2026/ ; https://www.adjust.com/blog/att-opt-in-rates-2025/ ; https://iapp.org/news/b/report-att-opt-in-rates-at-25-overall ; https://mwm.ai/apps/voice-aloud-reader/1446876360 ; https://hyperionics.com/atVoice/ ; https://apps.apple.com/us/app/easy-text-to-speech-reader/id6746776224
