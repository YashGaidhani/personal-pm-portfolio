# Healthy You — Product Case Study

**Product Type:** AI-driven habit-formation health & wellness app (mobile-first)
**Stage:** Market sizing → Feature prioritisation → Prototype (Complete)
**Role:** Team Lead & Product Strategist (led group strategy, market analysis, and prototype)
**Timeline:** One Academic Term — XLRI PGDM Coursework (DPCC)
**Status:** Complete
**Prototype:** https://healthy-you-app-project.lovable.app

---

## The Problem

Indian urban professionals consistently start health and fitness routines but fail to sustain them. Most fitness apps optimise for one-time actions — logging a single workout, tracking one meal — rather than building lasting behavioural change. This creates a **consistency gap**: users churn once initial motivation fades, progress plateaus, and the novelty of tracking wears off.

Our market sizing quantified the scale of this opportunity. Within India's 1.43 billion population, we identified two core segments — professionals aged 25–45 (27% of population) and young adults aged 18–25 (16%) — together representing approximately **225.7 million fitness-active smartphone users**. Applying urban and semi-urban adjustments (~50%) narrowed this to a serviceable market of **112.9 million users**, with a five-year SOM target of 3.4 million active users at 3% penetration.

The deeper problem wasn't market size — it was product design. Generic fitness apps track metrics but don't address *why* users abandon them: lack of personalisation, absence of behavioural nudging, and no mechanism to break through plateaus once initial results stall.

## The Hypothesis

We believed users would sustain healthier habits longer if the product replaced static tracking with an **AI-driven behavioural loop** — one that converts logged data into personalised, context-aware nudges rather than passive dashboards.

**Core Hypothesis:** Users will build durable habits if the app closes the loop between data capture (food/activity logging), intelligence (AI-detected plateaus and patterns), action (habit-stacked routines and nudges), and feedback (visible progress) — rather than stopping at tracking alone.

**Differentiation Assumption:** Unlike generic fitness apps built around short-term metrics, a product addressing motivation loss and plateaus directly — through evidence-based habit formation — would retain users through the phase where most competitors lose them.

**Success Signal:** Strong perceived value on features that directly serve this loop, validated through structured feature-value research rather than assumption.

## Customer Discovery

### Research Design
We used a **quantitative, feature-value research design** centred on the Kano methodology. Rather than open-ended problem discovery, our research question was deliberately narrow at this stage: given a shortlisted set of candidate features (derived from a prior Value/Effort scoring exercise), which ones would drive genuine user satisfaction versus indifference or dissatisfaction if removed? This let us validate prioritisation decisions with real user input rather than internal team judgment alone.

### Recruitment Method
We surveyed **50 respondents** drawn primarily from our target demographic of urban professionals and young adults aged 18–45 — the same segments underpinning our TAM/SAM analysis. Respondents were recruited through our personal and academic networks to reach individuals already engaged with, or actively trying to sustain, health and fitness routines, ensuring the sample reflected real intent rather than casual interest.

### Synthesis Method
Each of the ten shortlisted features (pre-ranked by Value/Effort score) was run through Kano-style classification, and responses were plotted on a **Better–Worse graph** to separate performance attributes from delighters. We cross-referenced this against the original V/E scores to confirm that our effort-based shortlisting had correctly surfaced features respondents actually valued.

### Top 3 Findings
* **Finding 1: Low-effort, high-frequency features scored highest.** The Daily Win Journal returned the top normalised score (10.0/10) despite minimal build effort — confirming that lightweight, habit-reinforcing touchpoints matter more to users than complex functionality.
* **Finding 2: Localisation is a genuine performance driver, not a nice-to-have.** The Desi-Food Database (7.6/10) and Dynamic Calorie Adjustment (6.4/10) scored as clear performance attributes — their presence measurably improves satisfaction and their absence would cause real dissatisfaction, validating that generic global fitness databases underserve this market.
* **Finding 3: No feature tested as purely indifferent.** Every one of the ten shortlisted features fell into either performance or delight categories on the Better–Worse graph. This confirmed our earlier Value/Effort shortlisting process was sound — we weren't carrying dead weight into prioritisation.

## Product Decisions

### What We Built First — and Why

We defined the MVP around an unbroken **critical path**: the minimum sequence of features required to deliver data capture, AI-driven insight, habit structuring, and feedback without interruption. We scored the resulting shortlist using RICE to confirm build order.

| Feature | Reach | Impact | Confidence | Effort | RICE Score | Decision |
|---|---|---|---|---|---|---|
| Photo Food Scanner | 21 | 21 | 80% | 8 | 42.0 | BUILD |
| Plateau Breaker AI | 13 | 21 | 70% | 21 | 9.1 | BUILD |
| Daily Win Journal | 21 | 8 | 90% | 3 | 50.4 | BUILD |
| Habit Stacking Engine | 13 | 13 | 70% | 13 | 9.1 | BUILD |
| Personalised Push Nudges | 21 | 13 | 80% | 8 | 27.3 | BUILD |
| Visual Progress Timeline | 13 | 8 | 90% | 5 | 18.7 | BUILD |
| Desi-Food Database | 13 | 8 | 70% | 8 | 9.1 | BUILD |

**Strategic Rationale:** Photo Food Scanner and Daily Win Journal led on RICE score because they combine high reach with low build effort — both act as low-friction entry points into the habit loop. Plateau Breaker AI, despite higher effort, was non-negotiable: it is the decision-intelligence layer that differentiates Healthy You from static tracking apps. Statutory features (Data Encryption, Medical Disclaimers, Consent Manager, Age Verification, Export Health Report) were built alongside the critical path as non-negotiable compliance requirements, not as RICE-scored trade-offs.

### What We Explicitly Did NOT Build — and Why

* **PMS/Cycle Syncing:** Scored lowest on normalised Kano value (1.0/10) among shortlisted features. Valuable for a subset of users but not central to the core habit loop for MVP scope.
* **Intermittent Fasting Timer:** Also scored 1.0/10 — a specialised feature serving a narrower behavioural pattern than the general habit-formation problem we were solving for.
* **Interactive Habit Map:** Higher build effort (Fibonacci 3) relative to its normalised value (1.6/10) made it a poor early trade-off against the core critical-path features.
* **Smart Grocery List:** Similarly effort-heavy relative to value; a logical extension once the Photo Food Scanner and Desi-Food Database were validated, not a launch requirement.

## North Star Metric and Measurement Plan

**North Star Metric:** Weekly Habit Completion Rate — the percentage of AI-recommended nudges (from the Habit Stacking Engine) that users mark complete within the week they were issued.

**Why:** This metric directly tests our core hypothesis — that closing the data-to-feedback loop drives sustained behaviour change, not just app opens or logs. A high logging rate with a low completion rate would mean we built a tracker, not a habit-formation product.

**Input Metrics:**
1. Daily food/activity logs via Photo Food Scanner (measures data capture health)
2. Nudges issued by Personalised Push Nudges (measures AI engagement supply)

**Guardrail Metric:** Consent and Disclosure Compliance Rate — the percentage of active users with complete, valid consent records and acknowledged medical disclaimers. Any decline triggers an immediate compliance review before further feature rollout.

## The Distribution Challenge

**Category Saturation:** Health and fitness is one of the most crowded app categories in India, meaning organic discovery is structurally difficult. Standing out required leading with the specific wedge — plateau-breaking and localisation — rather than competing on general fitness tracking, where incumbents have years of data and brand trust.

**The Habit-Formation Cold Start:** Unlike a social product, Healthy You's value doesn't depend on network density, but it does depend on sustained early engagement. A user who doesn't complete their first few AI-recommended nudges will churn before the habit loop has a chance to prove itself, making the first-week experience disproportionately important to long-term retention.

**Trust as a Distribution Lever:** Because the product handles sensitive health data and issues AI-generated recommendations, statutory features like Consent Manager and Medical Disclaimers aren't just compliance overhead — they're a trust signal that affects willingness to adopt in a category where users are increasingly wary of unverified health advice.

## What I Would Do Differently

**Pair Kano Data With Qualitative Discovery:** Our research design validated feature value quantitatively but didn't capture the *why* behind user responses. I would run a smaller round of follow-up interviews with a subset of the 50 respondents to understand the reasoning behind top-scoring features like the Daily Win Journal, before locking build priority.

**Test the Plateau Breaker AI Assumption Earlier:** This feature carries the highest effort in our RICE table and is the product's core differentiator, yet it was validated indirectly through the broader Kano survey rather than tested standalone. I would prototype a lightweight version of this specific capability early to de-risk the assumption before committing full build effort.

**Sequence Statutory Features Deliberately:** We treated compliance features as parallel-track builds. In hindsight, sequencing Consent Manager and Data Encryption ahead of the Photo Food Scanner would have let us collect real usage data under a fully compliant framework from day one, rather than retrofitting consent flows onto an already-active data pipeline.

## What This Taught Me About PM Craft

**Effort-adjusted prioritisation only works if effort estimates are honest.** Our V/E and RICE scores were only as useful as our willingness to score genuinely high-value features as high-effort when they were — the Plateau Breaker AI's low RICE score relative to its strategic importance was a signal to manage, not to ignore.

**Statutory features are product decisions, not just legal checkboxes.** Treating compliance as a design constraint from the outset — rather than an afterthought — shapes what the MVP can safely support and when.

**Quantitative validation narrows uncertainty; it doesn't eliminate it.** The Kano survey told us *what* users valued, but not *why* — a gap I'd close with lighter, faster qualitative follow-ups in any future prioritisation cycle.

---

*This case study was written as part of my PM portfolio. Healthy You was completed as an
academic team project — the market analysis, prototype, and product strategy were led from
my side. I am happy to walk through any section of this in detail.*

*— Yash Gaidhani | XLRI 2026 | www.linkedin.com/in/yash-gaidhani-xlri*
