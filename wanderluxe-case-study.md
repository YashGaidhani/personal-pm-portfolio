# WanderLuxe — Product Case Study

**Product Type:** AI-powered travel & hotel assistant chatbot (conversational, RAG-grounded)
**Stage:** Problem definition → System design → Prototype (Complete)
**Role:** Product Strategist / Architecture Lead
**Timeline:** One Academic Term — XLRI PGDM (GM) Coursework, 2025–26
**Status:** Complete
**Prototype:** https://wanderluxe-geo-guide.lovable.app

---

## The Problem

Travel planning and hotel selection are high-intent journeys made up of interconnected micro-decisions — destination suitability, budget, amenities, cancellation policies, location safety, and trust signals. Despite strong intent, users routinely abandon these journeys midway.

The root cause was structural, not motivational. Traditional travel search flows are **form-heavy and filter-intensive**: users must repeatedly adjust parameters — price, location, amenities — to converge on a decision, and each adjustment adds cognitive load. A user searching "hotels in Delhi under ₹5,000 with a pool" cannot express that intent naturally; they must translate it into a sequence of filter clicks.

This friction compounds with two deeper gaps. First, **policy opacity** — cancellation terms, refund conditions, and inclusions are buried in fine print, forcing users to hunt for answers instead of asking directly. Second, **generic recommendations** — without a mechanism to understand individual context and preferences, existing platforms return the same ranked list to every user regardless of stated needs.

WanderLuxe was scoped to remove this friction by replacing filter-based search with a conversational interface capable of understanding natural-language intent, asking clarifying questions, and grounding every recommendation in verified data rather than generated guesses.

## The Hypothesis

We believed that replacing structured search with a **conversational, context-aware interface** would reduce the cognitive load driving journey abandonment, provided the system could be trusted not to hallucinate.

**Core Hypothesis:** If users can express travel intent in natural language and receive multi-turn, clarifying dialogue instead of static filters, they will complete more of the decision-making journey — destination selection, budgeting, and hotel comparison — in a single continuous interaction.

**Trust Assumption:** Conversational convenience alone would not be sufficient. Because hotel and policy details carry real financial consequences, responses needed to be **grounded in retrieved, verified data** (via Retrieval-Augmented Generation) rather than purely generative output, to avoid the credibility damage caused by hallucinated recommendations.

**Success Signal:** Users completing multi-step journeys (destination → budget → itinerary → hotel recommendation) within a single conversation, without dropping off to search elsewhere for policy clarification.

## Customer Discovery

### Research Design
Given the project's technical scope and academic timeline, we ran **structured usability testing** rather than open-ended interviews. We defined two representative task scenarios — planning a trip to Udaipur and a trip to Goa — and observed how test users navigated the conversational interface end-to-end, from initial destination query through to hotel recommendation.

### Recruitment Method
Test sessions were run informally with peers and prospective travellers within our academic network, selected for genuine near-term travel planning intent rather than casual interest. This kept the sessions grounded in realistic task motivation rather than artificial prompts.

### Synthesis Method
We reviewed session transcripts turn-by-turn against our defined use cases (destination discovery, budget guidance, itinerary customisation, hotel comparison, travel tips) to identify where users stalled, rephrased queries, or asked for information outside the system's scope. These friction points were cross-referenced against our evaluation metrics — fallback rate and average turns to completion — to separate genuine usability gaps from expected clarification turns.

### Top 3 Findings
* **Finding 1: Natural-language queries collapse multiple filter steps into one.** Users who typed compound requests (destination + budget + amenity in a single message) completed the discovery phase in fewer turns than a filter-based flow would require — directly validating the core hypothesis behind replacing structured search.
* **Finding 2: Policy and trust questions surface mid-journey, not just at booking.** Users asked about cancellation terms and destination safety *while still exploring options*, not only once a hotel was shortlisted — confirming that RAG-grounded policy retrieval needed to be available throughout the conversation, not gated behind a later step.
* **Finding 3: Budget guidance was the highest-friction step without prior context.** When users asked for budget ranges before specifying travel style, responses felt generic; providing budget guidance worked far better once the system had already captured destination and preference context — reinforcing the need for slot filling to precede recommendation generation.

## Product Decisions

### What We Built First — and Why

We prioritised the components required to deliver one unbroken loop: understand intent, retrieve grounded information, and respond without hallucination.

| Feature | Reach | Impact | Confidence | Effort | RICE Score | Decision |
|---|---|---|---|---|---|---|
| NLU Layer (Intent + Entity Extraction) | 21 | 21 | 80% | 13 | 27.1 | BUILD |
| Dialogue Management (Slot Filling) | 21 | 21 | 70% | 13 | 23.7 | BUILD |
| RAG Retrieval Pipeline | 21 | 21 | 80% | 21 | 16.8 | BUILD |
| Domain Datasets (Hotels, Policy, FAQ) | 13 | 21 | 90% | 13 | 18.9 | BUILD |
| Conversation Logging & Monitoring | 13 | 8 | 90% | 5 | 18.7 | BUILD |
| Deployable Prototype Interface | 13 | 13 | 90% | 8 | 19.0 | BUILD |

**Strategic Rationale:** NLU and Dialogue Management led on RICE score because without accurate intent detection and slot filling, no downstream component — including RAG — has reliable input to work with. RAG Retrieval carried the highest effort (Fibonacci 21) but was non-negotiable: it is the mechanism that directly answers our trust hypothesis by grounding responses in verified hotel and policy data rather than generated text. Conversation logging was built early despite modest individual impact, since it fed directly into our evaluation metrics and usability synthesis.

### What We Explicitly Did NOT Build — and Why

* **Real-Time Travel API Integration:** Live inventory, pricing, and availability updates were deferred. The project scope prioritised validating the conversational and retrieval architecture over building live commercial integrations, which would have added engineering effort without testing the core hypothesis.
* **Multi-Lingual Support:** Deferred to focus dataset and NLU accuracy on a single-language baseline first, avoiding diluted model performance across languages before the core loop was validated.
* **Advanced Personalisation (Collaborative Filtering, Cross-Session Learning):** Excluded from MVP scope since it depends on accumulated user history the prototype hadn't yet generated; building it early would have meant optimising against synthetic, not real, usage data.
* **Automated Offline Evaluation Pipelines:** Standardised metrics like Inform and Success rate automation were deferred in favour of manual usability testing, which was sufficient at prototype scale and faster to act on.

## North Star Metric and Measurement Plan

**North Star Metric:** Task Success Rate — the percentage of user sessions in which the stated objective (e.g., finding a hotel meeting specified price, location, and amenity constraints) is successfully fulfilled.

**Why:** This metric directly tests whether the conversational model actually replaces filter-based search, rather than simply making search feel more novel. A high engagement rate with a low task success rate would mean the chatbot is conversational but not functionally useful.

**Input Metrics:**
1. Slot Completion Rate (percentage of required information slots correctly filled — measures whether the system captures what it needs to act)
2. Average Turns to Completion (lower values indicate reduced friction per completed task)

**Guardrail Metric:** Accuracy Rate — the percentage of responses that are factually correct and free of hallucination. If accuracy declines as task success rises, it signals the system is completing tasks by generating plausible-sounding but ungrounded answers, undermining the core trust hypothesis.

## The Distribution Challenge

**Category Trust Deficit:** Conversational AI in travel is a newer interaction pattern than search-and-filter, and users carry real financial risk in hotel and travel decisions. Any hallucinated response — even one — would disproportionately damage trust relative to the convenience gained, making accuracy a distribution lever as much as a technical requirement.

**Competing Against Familiar Mental Models:** Incumbent travel platforms have trained users to search and filter. A conversational-first product must overcome the habit cost of that existing behaviour, which is a harder distribution problem than simply offering a better feature — it requires the first few interactions to clearly outperform filtering, or users default back to what they know.

**No Live Inventory Layer:** Because real-time API integration was explicitly deferred, the prototype's recommendations aren't yet tied to live pricing or availability. This is an acceptable trade-off for validating the conversational architecture, but it means the current build cannot yet be distributed as a transaction-ready product — only as a decision-support layer.

## What I Would Do Differently

**Run Structured Usability Testing Earlier:** We validated the conversational hypothesis through informal peer sessions late in the build. I would run the Udaipur/Goa-style task scenarios against the NLU and slot-filling layers as soon as they were functional, rather than waiting for the full RAG pipeline to be in place — isolating which layer caused friction would have been faster.

**Sequence Accuracy Validation Before Scope Expansion:** With hallucination risk being central to the trust hypothesis, I would establish a formal accuracy benchmark against the domain datasets before layering in additional use cases like packing and safety suggestions, to avoid scaling an unverified retrieval pipeline.

**Treat Live Inventory as a Phase Boundary, Not an Afterthought:** Deferring real-time API integration was the right call for MVP scope, but I would define explicit success gates the prototype must clear (accuracy rate, task success rate thresholds) before greenlighting that integration, rather than leaving it as an open-ended future scope item.

## What This Taught Me About PM Craft

**Architecture decisions are product decisions.** Choosing RAG over pure generation wasn't a backend detail — it was the single design choice that determined whether the product could be trusted with financially consequential recommendations.

**Evaluation metrics must be defined before the build, not after.** Having Task Success Rate, Fallback Rate, and Accuracy Rate specified upfront meant usability testing had a clear lens for synthesis, rather than producing anecdotal impressions.

**Deferring scope is a form of prioritisation, not avoidance.** Explicitly excluding real-time inventory, multi-lingual support, and advanced personalisation kept the team focused on proving the core conversational-plus-grounding loop before adding complexity that would have diluted that validation.

---

*This case study was written as part of my PM portfolio. WanderLuxe was completed as an
academic team project — the product strategy and system architecture decisions were led
from my side. I am happy to walk through any section of this in detail.*

*— Yash Gaidhani | XLRI 2026 | www.linkedin.com/in/yash-gaidhani-xlri*
