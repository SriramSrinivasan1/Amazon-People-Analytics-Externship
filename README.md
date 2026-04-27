# Amazon-People-Analytics-Externship

## Executive Summary

Amazon's fulfillment centers face a persistent, high-cost attrition problem driven by shift burnout and lack of career clarity. This project analyzed 290 employee reviews sourced from Glassdoor and YouTube to identify the highest-priority friction point affecting associate retention. Using NLP-based sentiment analysis, thematic coding, and root cause analysis, the project surfaced shift burnout as the dominant driver of early attrition — and proposed a specific, low-cost, team-led intervention (the PACE Check-In Protocol) to address it before it compounds into operational and financial damage.

## Business Problem

High turnover in Amazon FCs is not just an HR problem — it cascades into operational throughput, shift coverage, and compounding recruiting costs that remain invisible on the P&L until they reach critical mass.

**Three interconnected impact areas:**

- **Employee Experience:** Burnout and lack of career clarity reduce engagement, morale, and psychological safety on the floor.
- **Operational Speed:** Every early exit disrupts FC throughput and forces constant rehiring cycles.
- **Business Impact:** Recruiting, onboarding, and ramp-up costs compound silently and are often misattributed or untracked.

The central question: *How might we reduce the absence of a safe pace-reporting mechanism for Fulfillment Associates, so they no longer experience burnout as unavoidable — and Amazon avoids compounding attrition, injury, and invisible turnover costs?*

## Methodology

### 1. Data Collection & Source Strategy

Two distinct data sources were combined to capture both formal and informal employee voice:

- **Glassdoor Reviews (280 rows):** Pros and cons sections covering all associate segments. Cons sections were prioritized to reduce keyword noise from overly positive pro-framing.
- **YouTube Transcripts (10 excerpts):** Workers filming themselves mid-shift — raw, unfiltered voice captured in real time. This source was included specifically because it bypasses the social desirability bias present in formal review platforms.

**Total: 290 reviews cleaned and scored.**

### 2. Data Cleaning & NLP Pipeline

| Tool | Purpose |
|---|---|
| Regular Expressions | Removed whitespace, line breaks, and formatting artifacts from raw review text |
| NLTK / TextBlob | Calculated sentiment polarity and subjectivity scores for each review |

The cleaned dataset combined both sources into a single 290-row file with fields for `cleaned_text`, `sentiment_polarity`, `sentiment_subjectivity`, `sentiment_label`, `platform`, and `section`.

### 3. Sentiment Analysis & Visualization

Sentiment distributions were compared across Glassdoor Pros, Glassdoor Cons, and YouTube to identify where formal channels diverge from real-time worker voice.

**Key finding:** Formal feedback channels (Glassdoor) systematically mask distress. YouTube transcripts reveal a more mixed and emotionally raw tone — frustration that formal review structures tend to suppress.

> Sentiment Dashboard → [View Interactive Artifact](https://claude.ai/public/artifacts/2db7f3a0-8572-4256-9e63-862e31c86318)

### 4. Thematic Coding & Root Cause Analysis

Three primary themes were identified and ranked by sentiment negativity rate and business risk:

| Theme | Key Data Signal | Business Implication |
|---|---|---|
| 🔴 **Shift Burnout** | YouTube excerpts: employees filming mid-shift exhaustion, counting down hours | Accelerates early attrition, increases injury risk, reduces productivity |
| 🟡 **Workplace Surveillance** | Sentiment split: 26.3% positive / 42.1% neutral / 31.6% negative | Inconsistent management practices; same policy feels supportive to some, punitive to others |
| 🟡 **Pay vs. Physical Cost** | 11.1% negative Glassdoor vs. 50% negative YouTube | Compensation may temporarily offset dissatisfaction; long-term physical strain erodes retention |

**Shift Burnout registered the highest negative sentiment rate at 34.3%**, confirming it as the highest-priority, most controllable friction point.

> Root Cause Tree → [View Interactive Artifact](https://claude.ai/public/artifacts/65a2a83f-e1dc-4e7f-a92c-185e186afb94)

## Intervention Design: PACE Check-In Protocol

A people-and-process intervention targeting shift burnout directly — with zero new technology and zero corporate budget required.

### How It Works

1. Associates flag physical unsustainability to their Learning Ambassador (LA) during the shift.
2. The LA aggregates patterns across the shift without individual attribution.
3. A weekly 10-minute stand-up surfaces patterns to the floor manager.
4. The manager exercises discretion to adjust station rotation or offer breaks.

### Why This Approach

- **Addresses Root Cause #1:** Creates a reporting channel outside ADAPT (Amazon's AI-automated productivity monitoring system), removing the barrier where associates feel unable to raise concerns without triggering automated performance consequences.
- **Real-world precedent:** A Harvard HaWC study validated formal voice channels across e-commerce fulfillment centers as effective in reducing distress without disrupting operations.
- **No policy change needed:** Uses the Learning Ambassador role already present on the floor. No new org structure or headcount required.
- **Reversible 60-day pilot:** Test on one shift. If it works, scale. If not, stop. No organizational commitment required.

**Evaluation criteria: ✓ Low Cost · ✓ High Impact · ✓ Measurable · ✓ Team-Led**

## Pilot Design & Success Signals

**Pilot Scope:**
- Who: Learning Ambassadors on the night shift at one FC
- Where: Inbound + Stowing departments · 2–3 LAs
- Duration: 60 days

**Timeline:**

| Phase | Activities |
|---|---|
| Week 1–2 | Orient LAs · Baseline attrition logged |
| Week 3–8 | Protocol runs · Weekly stand-ups held |
| Week 9–10 | Exit rate review · Go/No-go decision |

**Success Signals:**
- 30-day exit rate vs. control shift (tracked weekly)
- Check-in utilization rate (near real-time)

## Longer-Term Business Recommendations

**Recommendation #1 — Revise Onboarding**
Reflect actual shift intensity, rate expectations, and mandatory overtime in onboarding materials. Reduces early attrition driven by unmet physical expectations set before Day 1.

**Recommendation #2 — Retention on Manager Scorecards**
Include 30/90-day retention rates as a floor manager performance metric. Connects operational decisions to their people costs and closes the Ops–HR silo that currently makes turnover costs invisible.

## Skills Demonstrated

- Unstructured data collection and NLP pipeline design (Glassdoor scraping, YouTube transcript extraction)
- Sentiment analysis and polarity scoring (TextBlob, NLTK)
- Thematic coding and qualitative synthesis across 290 data points
- Root cause analysis applied to workforce and operations problems
- People analytics intervention design with measurability and reversibility built in
- Business case framing connecting employee experience to operational and financial outcomes
- Pilot design methodology with defined success signals and go/no-go criteria

## Limitations & Next Steps

### Current Limitations

**Data scope:** The 290 reviews represent public-facing and self-published sentiment. Associates with the most severe burnout may be underrepresented — those who left silently are not captured in Glassdoor or YouTube data.

**YouTube sample size:** Only 10 transcripts were available. While qualitatively rich, the YouTube signal is not statistically representative and should be treated as directional rather than conclusive.

**No internal HR data:** The analysis is grounded in external review data. Access to Amazon's internal exit interview data, tenure distributions, or ADAPT performance records would significantly strengthen the root cause analysis.

**Pilot not yet run:** The PACE Check-In Protocol is a proposed intervention, not a validated one. Results remain hypothetical until piloted.

### Next Steps

- **Run the 60-day pilot** on one night shift, tracking exit rate delta vs. a control shift and check-in utilization weekly.
- **Integrate internal data:** Pair the external sentiment analysis with internal HR and attrition data to quantify the cost of burnout-driven turnover per FC per quarter.
- **Expand theme analysis:** Workplace surveillance and pay-vs-physical-cost themes warrant their own targeted interventions if PACE Check-In shows signal.
- **Scale Learning Ambassador program:** If the pilot validates the LA as an effective voice channel, formalize the role's scope to include structured psychological safety functions beyond the current onboarding focus.
