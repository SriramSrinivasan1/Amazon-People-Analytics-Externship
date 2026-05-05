# 🏭 Amazon People Analytics — Reducing Shift Burnout in Fulfillment Centers

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)
![NLTK](https://img.shields.io/badge/NLP-NLTK%20%2F%20TextBlob-4B8BBE)
![Pandas](https://img.shields.io/badge/Data-Pandas-150458?logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Viz-Matplotlib-11557C)
![Colab](https://img.shields.io/badge/Runtime-Google_Colab-F9AB00?logo=googlecolab&logoColor=white)
![License](https://img.shields.io/badge/License-Portfolio-lightgrey)

> **Amazon People Analytics Externship · Cohort: Feb 2026**  
> A data-driven intervention proposal grounded in 290 employee reviews across Glassdoor and YouTube — using NLP-based sentiment analysis and root cause analysis to identify shift burnout as the #1 controllable driver of early attrition in Amazon Fulfillment Centers.

---

## 📋 Table of Contents

- [Problem Statement](#-problem-statement)
- [What It Does](#-what-it-does)
- [Methodology](#-methodology)
- [Key Findings](#-key-findings)
- [Intervention Design](#-intervention-design-pace-check-in-protocol)
- [Pilot Design & Success Signals](#-pilot-design--success-signals)
- [Business Recommendations](#-longer-term-business-recommendations)
- [Skills Demonstrated](#-skills-demonstrated)
- [Limitations & Next Steps](#-limitations--next-steps)
- [Repository Structure](#-repository-structure)

---

## 🎯 Problem Statement

High turnover in Amazon fulfillment centers is not just an HR problem — it cascades into operational throughput, shift coverage, and compounding recruiting costs that remain invisible on the P&L until they reach critical mass.

| Impact Area | The Problem |
|---|---|
| 👤 **Employee Experience** | Burnout and lack of career clarity reduce engagement, morale, and psychological safety on the floor |
| ⚡ **Operational Speed** | High turnover forces constant rehiring; every early exit disrupts FC throughput and shift coverage |
| 💰 **Business Impact** | Recruiting, onboarding, and ramp-up costs compound silently — invisible on P&L until they reach critical mass |

**Central question:** *How might we reduce the absence of a safe pace-reporting mechanism for Fulfillment Associates, so they no longer experience burnout as unavoidable — and Amazon avoids compounding attrition, injury, and invisible turnover costs?*

---

## ✅ What It Does

1. **Collects** 290 employee reviews from Glassdoor (280) and YouTube transcripts (10) — capturing both formal and raw, unfiltered worker voice
2. **Cleans** raw text using regex pipelines to remove formatting artifacts, whitespace, and noise
3. **Scores** every review with TextBlob sentiment polarity and subjectivity
4. **Compares** sentiment distributions across Glassdoor Pros, Glassdoor Cons, and YouTube to surface where formal channels diverge from real-time voice
5. **Codes** themes across the corpus and ranks by negativity rate and business risk
6. **Proposes** a specific, low-cost, team-led intervention targeting the highest-priority friction point

---

## 🔬 Methodology

### 1. Data Collection & Source Strategy

Two distinct sources were combined to capture both formal and informal employee sentiment:

| Source | Volume | Why It Was Included |
|---|---|---|
| Glassdoor Reviews (Cons section) | 280 rows | Structured, cross-segment feedback; cons section prioritized to reduce positive-framing noise |
| YouTube Transcripts | 10 excerpts | Workers filming mid-shift — bypasses social desirability bias present in formal review platforms |

> **Focus:** Cons sections + YouTube excerpts only. Pros were excluded to avoid keyword noise.  
> **Total: 290 reviews cleaned and scored.**

### 2. Data Cleaning Pipeline

| Tool | Purpose |
|---|---|
| Regular Expressions | Removed whitespace, line breaks, and formatting artifacts from raw review text |
| NLTK / TextBlob | Calculated sentiment polarity and subjectivity scores for each review |

The cleaned dataset combined both sources into a single 290-row file:

```
Fields: review_id_total | review_id | cleaned_text | sentiment_polarity
        | sentiment_subjectivity | sentiment_label | platform | section
```

### 3. Sentiment Analysis & Visualization

Sentiment distributions were compared across Glassdoor Pros, Glassdoor Cons, and YouTube to identify divergence between formal channels and real-time worker voice.

> 📊 **Sentiment Dashboard →** [View Interactive Artifact](https://claude.ai/public/artifacts/2db7f3a0-8572-4256-9e63-862e31c86318)

**Key insight:** Formal feedback channels (Glassdoor) systematically mask distress. YouTube transcripts reveal a more mixed, emotionally raw tone — frustration that formal review structures suppress.

### 4. Thematic Coding & Root Cause Analysis

Three primary themes were identified and ranked by negativity rate and business risk:

| Priority | Theme | Key Data Signal | Business Risk |
|---|---|---|---|
| 🔴 #1 | **Shift Burnout** | YouTube: employees filming mid-shift exhaustion, counting down hours | Accelerates early attrition, increases injury risk, reduces productivity |
| 🟡 #2 | **Workplace Surveillance** | Sentiment split: 26.3% pos / 42.1% neutral / 31.6% neg | Inconsistent management; same policy feels supportive to some, punitive to others |
| 🟡 #3 | **Pay vs. Physical Cost** | 11.1% neg (Glassdoor) vs. 50% neg (YouTube) | Compensation may temporarily offset dissatisfaction; long-term strain erodes retention |

> 🌳 **Root Cause Tree →** [View Interactive Artifact](https://claude.ai/public/artifacts/65a2a83f-e1dc-4e7f-a92c-185e186afb94)

---

## 📊 Key Findings

**Shift Burnout registered the highest negative sentiment rate at 34.3%** — the single most controllable driver of early attrition across the 290-review corpus.

| Finding | Detail |
|---|---|
| Formal vs. informal voice gap | Glassdoor Cons show ~16% negative; YouTube shows ~21% negative — a 5-point suppression gap in formal channels |
| Pay-physical cost disconnect | Employees question whether pay compensates for physical strain; gap is 4× larger on YouTube vs. Glassdoor |
| Surveillance polarization | Nearly 1 in 3 associates experience monitoring as punitive pressure rather than neutral oversight |

---

## 🛠️ Intervention Design: PACE Check-In Protocol

A **people + process intervention** targeting shift burnout directly — with zero new technology and zero corporate budget required.

### How It Works

```
Associate flags physical unsustainability
              │
              ▼
Learning Ambassador (LA) collects patterns across shift
       (no individual attribution)
              │
              ▼
  Weekly 10-min stand-up with floor manager
              │
              ▼
 Manager adjusts station rotation or offers breaks
```

### Why This Approach

| Rationale | Detail |
|---|---|
| **Addresses Root Cause #1** | Creates a reporting channel outside ADAPT — the AI-automated productivity system that auto-generates writeups based on performance metrics, removing manager discretion as a barrier |
| **Real-world precedent** | Harvard HaWC study validated formal voice channels across e-commerce FCs as effective in reducing distress |
| **No policy change needed** | Uses the Learning Ambassador role already on the floor; no new org structure or headcount required |
| **Reversible 60-day pilot** | Test on one shift — if it works, scale; if not, stop. No organizational commitment required |

**✓ Low Cost · ✓ High Impact · ✓ Measurable · ✓ Team-Led**

---

## 📍 Pilot Design & Success Signals

**Scope:**
- **Who:** Learning Ambassadors on the night shift at one FC
- **Where:** Inbound + Stowing departments · 2–3 LAs
- **Duration:** 60 days

**Timeline:**

| Phase | Activities |
|---|---|
| Week 1–2 | Orient LAs · Baseline attrition logged |
| Week 3–8 | Protocol runs · Weekly stand-ups held |
| Week 9–10 | Exit rate review · Go/No-go decision |

**Success Signals:**
- 30-day exit rate vs. control shift (tracked weekly)
- Check-in utilization rate (near real-time)

---

## ✅ Longer-Term Business Recommendations

**Recommendation #1 — Revise Onboarding**  
Reflect actual shift intensity, rate expectations, and mandatory overtime in onboarding materials. Reduces early attrition driven by unmet physical expectations set before Day 1.

**Recommendation #2 — Retention on Manager Scorecards**  
Include 30/90-day retention rates as a floor manager performance metric. Connects operational decisions to their people costs and closes the Ops–HR silo that currently makes turnover costs invisible.

---

## 🎓 Skills Demonstrated

- Unstructured data collection and NLP pipeline design (Glassdoor scraping, YouTube transcript extraction)
- Sentiment analysis and polarity scoring (TextBlob, NLTK)
- Thematic coding and qualitative synthesis across 290 data points
- Root cause analysis applied to workforce and operations problems
- People analytics intervention design with measurability and reversibility built in
- Business case framing connecting employee experience to operational and financial outcomes
- Pilot design methodology with defined success signals and go/no-go criteria

---

## ⚠️ Limitations & Next Steps

### Current Limitations

| Limitation | Detail |
|---|---|
| **Data scope** | 290 reviews represent public-facing and self-published sentiment; associates who left silently are not captured in Glassdoor or YouTube data |
| **YouTube sample size** | Only 10 transcripts available — qualitatively rich but not statistically representative; treat as directional |
| **No internal HR data** | Analysis is grounded in external review data; access to Amazon's internal exit interview data or ADAPT performance records would significantly strengthen root cause analysis |
| **Pilot not yet run** | PACE Check-In Protocol is a proposed intervention; results remain hypothetical until piloted |

### Next Steps

| Timeline | Action |
|---|---|
| Short-term | Run the 60-day pilot on one night shift; track exit rate delta vs. control shift and check-in utilization weekly |
| Medium-term | Pair external sentiment analysis with internal HR and attrition data to quantify burnout-driven turnover cost per FC per quarter |
| Long-term | Expand theme analysis — Workplace Surveillance and Pay vs. Physical Cost warrant targeted interventions if PACE Check-In shows signal |
| Scale | Formalize the Learning Ambassador role's scope to include structured psychological safety functions if the pilot validates the voice channel |

---

## 📁 Repository Structure

```
Amazon-People-Analytics-Externship/
├── Amazon Reviews - Glassfoor Platform Data Cleaning.ipynb     
├── Amazon Reviews - YouTube Platform Data Cleaning.ipynb       
├── README.md                           # This file
└── presentation/
    └── Amazon_Pitch_Deck_Final.pdf     # Final stakeholder presentation deck
```

---

*Built during the Amazon People Analytics Externship · Cohort: Feb 2026*  
*Extern: Sriram Srinivasan*
