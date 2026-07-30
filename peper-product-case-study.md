# Peper — Product Case Study

**Product Type:** Social media platform (0-to-1, mobile-first)  
**Stage:** Customer discovery → MVP definition → Paused  
**Role:** Founder & Product Lead  
**Timeline:** September 2019 – May 2020  
**Status:** Paused — first unconstrained career decision after XLRI campus placement is PM  

---

## The Problem

Indian urban professionals aged 22–35 spend an average of 1.5 to 2.5 hours daily on social platforms designed to maximise engagement through content virality. This model structurally rewards polarisation, performative identity, and anxiety-inducing comparison, creating a severe authenticity and trust deficit that is deeply felt by Gen Z and early millennials.

Our initial market survey of 170+ users revealed a stark platform bifurcation. While 91% of users were active on WhatsApp and 65% on Instagram, their primary use cases fundamentally conflicted. Users relied on public platforms for discoverability but increasingly retreated to WhatsApp for meaningful connection. Strikingly, 67% of surveyed users cited a lack of trust and control over content authenticity—including unverified news and performative posting—as their primary frustration with public-feed networks.

This revealed a critical market gap: existing platforms enforce a strict binary. Communication is either entirely private (WhatsApp) or algorithmically public (Instagram, Twitter). There was no trusted, middle-layer platform designed for authentic, contextual sharing with verified real-world connections.

## The Hypothesis

We believed that our target demographic (aged 18–35) would engage more deeply with a social platform if we shifted the burden of content verification from a centralised algorithmic authority to a **hyper-localised, user-driven network**.

**Core Hypothesis:** Users will trust and engage with news and updates more if content is geofenced (a "Live Timeline" of local happenings), traceable to its original source, and subject to community voting for authenticity (Fake vs. Verified tags).

**Business Model Assumption:** We hypothesised we could monetise this localised engagement through a high-volume, low-ticket micro-ad model—targeting thousands of local neighbourhood vendors paying nominal fees, rather than a few enterprise advertisers paying premiums.

**Success Signal:** High daily active engagement on the geofenced Live Timeline and a positive willingness-to-pay signal from local SMB owners during B2B validation.

## Customer Discovery

### 4.1 Research Design
We prioritised in-person interviews (primarily in Pune) over purely digital surveys to capture non-verbal cues, understand the "why" behind user behaviours, and filter out low-intent responses.

To ensure high data quality, the research design incorporated two key principles:
* **Psychological Safety:** We made all personally identifiable information (including names) strictly optional. This reduced response friction and encouraged participants to speak candidly about sensitive topics like social comparison and misinformation.
* **Structured Guardrails:** The interview guide maintained a deliberate balance of closed-ended questions (to anchor the conversation) and open-ended questions (to explore core social media habits), preventing the discussion from drifting out of scope.

### 4.2 Recruitment Method
To efficiently reach our 170+ participant target within a bootstrapped environment, we deployed a location-based intercept interview strategy ("guerrilla research") across Pune.

* **Execution:** I led a four-person research team, deliberately leveraging the geographic knowledge of team members native to Pune. We conducted targeted weekend sprints, physically mapping different city zones to specific user personas.
* **Format:** 99% of the interviews were conducted in-person via direct field intercepts, with a negligible fraction (1–2 users) processed digitally. This physical intercept model ensured we were capturing real-world, localised demographics rather than a skewed online-only sample.

### 4.3 Segmentation
Our core target demographic was the 18–35 age group, which we subdivided into three distinct user segments. To efficiently source these segments, we aligned our recruitment locations with high-density physical hubs:
1. **College Students (18–22):** Intercepted primarily near major university campuses and educational hubs.
2. **Working Professionals (23–35):** Sourced near corporate tech parks and major commercial districts.
3. **General Young Adults/Commuters:** Captured at transit hubs (e.g., major bus stands) to ensure a diverse cross-section of daily social media users outside of strictly academic or corporate bubbles.

### 4.4 Synthesis Method
To process the raw data from 170+ interviews, we established a structured, manual synthesis pipeline. Interviewers logged responses directly into pre-formatted digital forms in the field (supplemented by audio recordings), which aggregated into a centralised spreadsheet for analysis.

We manually coded the data to prevent automated tools from missing the contextual nuance of in-person interactions. This process yielded 10 distinct themes, segmented into three categories:
1. **Core Value Drivers:** Communication, entertainment, information gathering, and content sharing.
2. **Critical Unmet Needs:** Fake news/content proliferation, privacy and security gaps, and general UX friction.
3. **Feature Requests:** Functional enhancements like status downloads and dislike buttons.

Viewed through the Ansoff Matrix, the synthesis confirmed a clear "Product Development" opportunity: introducing a new, highly regulated product to an existing market whose fundamental needs (trust and authenticity) were no longer being met. We mapped our eventual feature set directly to four of the top five recurring themes from this synthesis.

### 4.5 Top 3 Findings
Our analysis revealed three critical findings that ultimately dictated our product roadmap:

* **Finding 1: Communication remains the foundational baseline.**
  When asked about the primary value of social media, 30.1% of interviewees cited communication and staying connected. Despite the rise of algorithmic feeds, the fundamental utility of connecting with real networks remained the most heavily weighted user need.
* **Finding 2: Entertainment is a massive, but separate, motivation.**
  Approximately 27.2% of users cited entertainment (video, music, trends) as their core motivation. This validated that while users wanted connection, any new platform still needed to support rich media consumption without conflating private communication with public broadcasting.
* **Finding 3: The Fake News Deficit is the primary market vulnerability.**
  Over 60% of interviewees explicitly or implicitly cited the unchecked circulation of fake news and unverified content as a major point of friction. Because this demographic relies heavily on social media for daily information consumption, the absence of self-regulating features or authenticity checks created a severe trust deficit. This insight became the foundation for our hyper-localised verification hypothesis.

## Product Decisions

### 5.1 What We Built First — and Why

We prioritised the MVP feature set using a strict RICE framework, utilising the Fibonacci sequence for scoring to force distinct trade-offs and avoid artificial inflation of impact. We also evaluated and discarded several feature requests sourced directly from our initial user surveys (e.g., AI moderation, complex calling features)[cite: 2, 7].

| Feature | Reach | Impact | Confidence | Effort | RICE Score | Decision |
|---|---|---|---|---|---|---|
| Absolute Source Tracking | 21 | 13 | 70% | 5 | 38.2 | BUILD |
| Human-Driven Verification Meter | 13 | 21 | 80% | 8 | 27.3 | BUILD |
| Location-Based Live Timeline | 13 | 21 | 80% | 13 | 16.8 | BUILD |
| Manual Post Categorisation | 21 | 8 | 50% | 5 | 16.8 | BUILD |
| Localised Trending Topics | 21 | 13 | 70% | 21 | 9.1 | BUILD |
| Dark/Black Theme UI | 21 | 5 | 90% | 13 | 7.2 | DEFER |
| AI Adult Content Filter | 21 | 13 | 40% | 34 | 3.2 | CUT |
| In-App Media Editing Tools | 13 | 8 | 50% | 21 | 2.4 | CUT |
| Advanced Video Playback | 13 | 5 | 30% | 13 | 1.5 | CUT |
| Conference Video Calling | 13 | 8 | 50% | 34 | 1.5 | CUT |
| Anonymous View/Post Limits | 21 | 3 | 20% | 21 | 0.6 | CUT |
| Voice Recognition Features | 8 | 5 | 20% | 21 | 0.4 | CUT |

**Strategic Rationale:** We prioritised features that directly addressed our primary market finding: the fake news trust deficit. Absolute Source Tracking and the Verification Meter were low-effort, high-impact mechanisms to enforce accountability. We paired these with the Live Timeline to test our hyper-local distribution hypothesis. Manual Categorisation was built to ensure the verification meter was only applied to news/information, preventing friction on purely personal posts.

### 5.2 What We Explicitly Did NOT Build — and Why

Great product strategy requires deliberate omission. We explicitly cut several features that detracted from our core hypothesis:

* **Anonymous Viewing/Posting without Account Creation:** Despite initial assumptions regarding privacy, this feature yielded a very low confidence score (20%). More importantly, allowing anonymous posting actively contradicted our core mission of building a trusted, accountable local network.
* **AI Content Filtering & Conference Calling:** While requested in surveys, building AI moderation models and complex video infrastructure required massive engineering effort (Fibonacci 34) and distracted from our core differentiator[cite: 2, 7].
* **In-App Media Editing & Advanced Video Playback:** We deliberately chose not to compete on rich-media tooling. Building filters and YouTube-style playback required significant effort but delivered minimal impact on our core problem of content authenticity.

## North Star Metric and Measurement Plan

**North Star Metric:** Average Daily Interactions Per Post — the total daily post interactions (likes, comments, verifications, shares) divided by the total daily posts generated.

**Why:** This directly measures whether our hyper-localised, verification-first model actually drives meaningful engagement compared to standard algorithmic feeds. Engagement without trust is the problem we are solving, not replicating.

**Input Metrics:**
1. Total daily post interactions (measures whether content generates genuine exchange)
2. Total daily posts generated (measures supply-side platform health)

**Guardrail Metric:** The Authenticity Delta — the week-over-week difference in (Fake Reports / Total Posts) minus (Verified Reports / Total Posts). If this delta increases positively, it signals our platform is accelerating misinformation rather than solving it, triggering an immediate product review.

## The Distribution Challenge

**The Cold Start Problem:** We launched our Alpha testing phase on the Google Play Store, initially seeding the platform with close friends and relatives to simulate a localised network. We quickly discovered that a social product's value is directly tied to its network density. An attractive feature set is irrelevant if a new user logs into an empty timeline.

**CAC vs. Organic Growth:** In social networks, Customer Acquisition Cost (CAC) extends all the way through retention. If you fail to rapidly build the network effect, early adopters churn, and your CAC effectively resets to zero. Paid acquisition could inflate vanity metrics, but it failed to generate the genuine interaction required for retention. Organic, high-velocity growth was mandatory.

**The Retention Reality (Velocity over Perfection):** Our most fatal product decision was optimising for a flawless, bug-free application at the expense of shipping velocity. Perfection became the enemy of success. The delays incurred to ensure high quality stalled our acquisition pace. In a network-effects business, a slow rollout causes the initial seeded network to decay before critical mass is achieved.

## What I Would Do Differently

**Validate the Business Model Upfront:** I would validate the revenue engine concurrently with the MVP. We built the platform assuming local vendors would pay for micro-targeted ads. Post-launch validation revealed this B2B assumption was structurally flawed: local retail shops operate on goodwill, service quality, and word-of-mouth. They have effectively zero marketing spend. Understanding the stakeholder's actual business model earlier would have forced a necessary pivot before we wrote a single line of code.

**Pace of Acquisition:** I would launch a bare-bones MVP to a hyper-concentrated cohort and aggressively ramp up acquisition to sustain the initial network effect. I would accept technical debt and minor UI bugs in exchange for the momentum required to keep early adopters engaged.

## What This Taught Me About PM Craft

**Agile principles dictate market timing, not just engineering.** Demands evolve rapidly. Delivering a "perfect" product too late is far more dangerous than shipping a functional MVP on time. Iteration requires live users; you cannot iterate in a vacuum.

**Validate the solution, not just the problem.** We anchored deeply on a validated user problem (the authenticity deficit) but failed to rigorously validate our proposed solution's business model (vendor willingness-to-pay) until the product was already built.

**Users own the problem; the PM owns the solution.** Users rarely know what features they actually need. Asking them for solutions leads to feature creep. A PM's job is to extract the underlying pain points, prioritise ruthlessly against limited resources, and build the solution that serves the core metric.

---

*This case study was written as part of my PM portfolio. Peper remains paused — 
the learnings from this experience directly inform how I approach product work 
professionally. I am happy to walk through any section of this in detail.*

*— Yash Gaidhani | XLRI 2026 | www.linkedin.com/in/yash-gaidhani-xlri*
