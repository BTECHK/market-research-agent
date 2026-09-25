# Source Verification Report

**Report verified:** Audio Anywhere: Is There a Viable Market for an AI Long-Document Reader on iOS? (`2026-09-25-audio-anywhere-market-analysis.md`)
**Verification date:** 2026-09-25
**Overall confidence:** MEDIUM–HIGH (HIGH for the facts behind the recommendations; Low–Medium for sizing, as the report already says)

## Summary

WebFetch was blocked, so no URL was opened directly. Verification used two methods:

1. **Nine WebSearch spot-checks** on the highest-stakes claims. All nine matched what the report says.
2. **Tracing every quote, figure and citation back to the seven raw files**, then recomputing all of the report's arithmetic: the TAM, SAM and SOM, the gross-margin table, the CAC ceiling, the renewal sensitivity and the COGS figures.

Result: one material arithmetic error, which came from the raw pricing file and had been carried into the report. It is now fixed. There were also three smaller labeling or precision fixes. No invented numbers and no misattributed quotes were found.

## Verification statistics (~80 discrete claims checked)

| Status | Count | % | Basis |
|---|---|---|---|
| ✅ Verified | 12 | 15% | Confirmed by a live web search, or by pure arithmetic |
| ⚠️ Partially verified | 60 | 75% | Traced faithfully to a raw file and its cited URL; the URL was not opened (the raw files themselves come from search snippets) |
| 🔍 Unverifiable | 7 | 9% | Third-party estimates, plus paraphrased [P] quotes and assumption-driven items |
| ❓ Source not found | 0 | 0% | |
| ❌ Unsupported | 1 → 0 | 1% | COGS for 5–8 studio hours (fixed) |

## Critical issues (fixed in the report)

### Issue 1: Cloud "studio hours" COGS understated about 5x
- **Location:** Section 7, the "So what" architecture paragraph; Section 9, MVP scope table. Originates in `raw/pricing-data.md` and `raw/pm-analysis.md`.
- **Claim:** "5–8 metered 'studio' cloud hours a month at ≤$30/1M characters (~$1.60–2.50 COGS)."
- **Problem:** The report uses 857 characters per minute, so one hour is about 51.4K characters. At $30/1M, 5–8 hours cost **$7.70–12.30**, not $1.60–2.50. That exceeds the ~$7.64 net revenue from an $8.99/mo plan after Apple's 15%. The report's own margin table agrees: moderate use (5 h) at $30/1M gives an 8% margin.
- **Fix applied:** Changed the allowance to 1–2 hours (~$1.50–3.10 COGS), added a correction note, and updated the MVP scope row. The report's overall conclusion (on-device by default, metered cloud) still holds.

## Minor fixes applied
- **"$53–106K gross bookings"** (Executive Summary Q3 and the SOM table): the figure is calculated *after* Apple's 0.85 factor. It is now labeled "net of Apple's 15%". Section 7 already said this correctly.
- **"roughly two-thirds of it Speechify":** Speechify's $36–48M is about 51–100% of the $45–70M TAM at the range ends, and about 76% at the midpoint. Changed to "two-thirds to three-quarters."
- **Speechify $29/mo:** now confirmed by several 2026 trackers (costbench, texttolab, fluxnote), so "possible $29/mo" became "$29/mo" and the data-conflict note was updated.

## Warnings (not changed)
- **Nearly all evidence comes from search-result snippets.** The report says so plainly in its Research Limitations. Sensor Tower's ~$2M/month for Speechify comes from a single snippet with no month stated.
- **AppleVis "will not pay $60 a year"** is a [P] paraphrase in `voice-quotes.md`, but the report shows it in quotation marks. Recheck it before any external use.
- **The SOM "(~3–6% of SAM)"** is measured against the SAM midpoint (~$10.5M). Against the full $5–16M range it is 2–14%.
- **Fish Audio "$52M seed":** the TechCrunch URL slug says "$50M". The report follows the raw trend file.
- **"Reverse within days"** (Voice Dream/Applause): the reversal itself is confirmed. The exact timing is not.
- **Audeus $19/mo or $119/yr** comes from a search snippet. The vendor pricing page itself was not seen.
- **The TAM/SAM/SOM rest on analyst assumptions [A]**, and the report labels them Low–Medium confidence. This is correct.

## Arithmetic checks (all pass unless noted)
| Item | Check | Result |
|---|---|---|
| TAM | 24 + (12–24) + 4 + (5–20) = $45–72M | ✅ (~$45–70M) |
| ElevenReader US | 5M × 2.6% × $80 × 40% = $4.16M | ✅ |
| SAM | 1.3+1+0.4+0.5+3.5 = 6.7M → ×10–20% → ×57% → ×20–30% = 76K–229K → ×$69 = $5.2–15.8M | ✅ |
| SOM year 1 | 30K × 3–6% = 900–1,800 payers × $69 × 0.85 = $52.8–105.6K | ✅ (label fixed) |
| SOM year 3 | 5–10K × $69 = $345–690K | ✅ |
| Renewal sensitivity | 1,800 / 0.77 ≈ 2,338 payers × $69 × 0.85 ≈ $137K | ✅ (~$135K) |
| Gross margin at $8.49 net | $16/1M × 1.03M = $16.48 → −94%; $30 → −264%; $100 → −1,113%; light (0.103M) at $100 → −21% | ✅ |
| CAC ceiling | $32–50 × 3–6% = $0.96–3.00 per install | ✅ |
| ElevenReader free tier | 600 min / 70 min ≈ 8.6 documents | ✅ (~8) |
| PDF cleanup cost | Mistral $1–2 per 1K pages = $0.001–0.002 per page | ✅ |
| Studio hours COGS | 5–8 h × 51.4K × $30/1M = $7.70–12.30 | ❌ → fixed |

## Web spot-checks (September 2026)
| Claim | Result | Source |
|---|---|---|
| ElevenReader: free 10 h/mo; Ultra $11/mo or $99/yr; students get a free year | ✅ | [elevenreader.io blog](https://elevenreader.io/blog/best-pricing-more-value), [X post](https://x.com/elevenreader/status/1996589050816315627) |
| Audeus markets "Read Aloud PDFs, Gdocs & more" and "automatically saves your place" | ✅ | [audeus.com](https://www.audeus.com/) |
| Audeus Pro $19/mo or $119/yr | ✅ (snippet) | [GetApp](https://www.getapp.com/all-software/a/audeus/pricing/) |
| Google Docs "Listen to this tab" (Gemini), web only, rolling out Aug 2025 | ✅ | [Workspace Updates](https://workspaceupdates.googleblog.com/2025/08/listen-to-documents-using-gemini-google-docs.html), [9to5Google](https://9to5google.com/2025/08/18/google-docs-audio-gemini/) |
| Docs audio summaries (Feb 2026) | ✅ | [Business Standard](https://www.business-standard.com/technology/tech-news/gemini-powered-summaries-in-google-docs-how-it-works-126021300723_1.html) |
| iOS 26 Accessibility Reader is system-wide and works in any app | ✅ | [Apple Support](https://support.apple.com/guide/iphone/read-listen-text-apps-accessibility-reader-iph406a46ab8/ios), [AFB](https://afb.org/blog/entry/ios-26-accessibility-features) |
| ElevenLabs $500M Series D led by Sequoia at $11B (Feb 2026) | ✅ | [TechCrunch](https://techcrunch.com/2026/02/04/elevenlabs-raises-500m-from-sequioia-at-a-11-billion-valuation/), [ElevenLabs](https://elevenlabs.io/blog/series-d) |
| Speechify $139/yr or $29/mo | ✅ | [costbench](https://costbench.com/software/ai-voice-tools/speechify/), [texttolab](https://texttolab.com/blog/speechify-pricing) |
| Voice Dream moved to $59.99/yr, then reversed; legacy buyers keep their features | ✅ | [Perkins](https://www.perkins.org/resource/voice-dream-reader-subscription-controversy/), [AppleVis](https://www.applevis.com/forum/ios-ipados/applause-has-backed-down-purchased-voice-dream-features-will-stay) |

## Full verification log (condensed by section)

| Section | Claims | Status | Notes |
|---|---|---|---|
| Executive summary | ~20 | ✅ / ⚠️ | Key facts web-verified; the rest trace to the raw files. The SOM label is fixed. |
| Methodology and conflicts | ~12 | ⚠️ | The conflicts table matches the raw files. The Speechify monthly-plan conflict is resolved. |
| Market landscape | ~18 | ⚠️ | CDC, IDA, Edison, APA, Wispr and Pocket figures match the raw files exactly. |
| Customer deep dive | ~20 quotes | ⚠️ | All present in `voice-quotes.md` or `competitor-data.md` with matching URLs. One [P] paraphrase appears in quotation marks. |
| Competitive table | ~15 | ⚠️ / ✅ | Prices match the raw files. NaturalReader is shown as $79–159 (pricing file); the competitor file says $99.50–119. |
| TAM/SAM/SOM, unit economics | ~15 | ✅ arithmetic / 🔍 inputs | One critical error, now fixed. |

## Verified sources index (by type)
- **Primary / official:** Apple Support and Developer; Google Workspace Updates; Google developer docs; ElevenLabs and ElevenReader blogs; CDC MMWR and VEHSS; IDA; Federal Register; RevenueCat. The official claims were confirmed by search.
- **Secondary / press:** TechCrunch, 9to5Google, MacRumors, Publishers Weekly, Inside Radio/Edison. The ElevenLabs and Google claims were confirmed.
- **Trackers and aggregators (lower reliability):** costbench, texttolab, fahimai, appbrain, Similarweb, Sensor Tower snippet, Latka, justuseapp, speedreadinglounge, castreader.
- **Community:** Apple Community, AppleVis, Zotero, Adobe, Trustpilot, BBB, mjtsai, mosen.org. Traced to the raw files only.
- **Inaccessible in this environment:** every URL was accessed only through search, because WebFetch was blocked.

## Appendix A update for the main report
- **Fully verified ✅:** ElevenReader pricing and free tier; Audeus features and price; Google Docs Listen (Aug 2025, web); Docs audio summaries (Feb 2026); iOS 26 Accessibility Reader; ElevenLabs $11B Series D; Speechify $139/yr and $29/mo; Voice Dream subscription reversal.
- **Partially verified ⚠️:** all other cited figures and quotes (they trace faithfully to the raw research files, which rely on snippets).
- **Unverifiable 🔍:** Speechify revenue (Sensor Tower, Latka); App Store rating counts; TAM/SAM/SOM assumption inputs; [P] paraphrased quotes.
