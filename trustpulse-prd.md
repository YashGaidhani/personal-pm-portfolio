# TrustPulse — Product Requirements Document

**Version:** 1.0 (MVP)  
**Author:** Yash Gaidhani  
**Date:** 2025  
**Status:** MVP Definition Complete  
**Product Type:** AI verification layer (B2C/B2B utility)  

---

## 1. Problem Statement

By 2025, the rapid explosion of Generative AI has made synthetic content, manipulated images, and AI-generated text virtually indistinguishable from human-created work. Students, researchers, and professionals frequently encounter misleading, manipulated, or AI-generated content on platforms like Instagram and WhatsApp, but lack a fast, reliable way to verify its authenticity[cite: 9]. 

Verification today is slow, manual, inconsistent, and stressful, leading to confusion, psychological discomfort, and severe reputational risk[cite: 9]. Existing fact-check tools require multiple steps, breaking the user's natural workflow[cite: 11]. Furthermore, enterprises face a massive operational bottleneck, unable to reliably verify if the text, credentials, or work samples they process are human-generated.

TrustPulse solves this by providing a one-click verification utility[cite: 9]. Built rapidly using Vibe coding on Lovable, the MVP leverages NLP and OCR to analyze content structure and instantly output an authenticity score. By functioning as a frictionless, single-player sandbox, users can instantly verify claims, images, and text without a complex onboarding process.

---

## 2. Target Personas

### Persona 1 — Aarav Mehta: "The Fast-Scrolling Student"[cite: 11]
**Role:** Undergraduate / MBA student consuming short-form content and WhatsApp forwards[cite: 11].  
**Goal:** Stay informed without being misled and avoid embarrassment from sharing fake news[cite: 11].  
**Current workaround:** Uses comments or Google to check misinformation, spending <1–2 minutes verifying anything[cite: 11].  
**Pain point:** No quick way to verify screenshots, reels, and images; fears being misled but lacks a tool inside his existing workflow[cite: 11].  
**Job to be done:** "When I encounter suspicious or emotionally charged online content, I want to verify its authenticity quickly so I feel confident before sharing or believing it."[cite: 8, 9]

### Persona 2 — Riya Sharma: "The Skeptical Verifier"[cite: 11]
**Role:** Graduate / MBA student / Researcher who manually cross-checks sources[cite: 11].  
**Goal:** Maintain reputation as "informed and credible" and avoid circulating misinformation[cite: 11].  
**Current workaround:** Googles suspicious content and cross-checks across multiple news sites[cite: 11].  
**Pain point:** Verifying news takes too long, and it is incredibly hard to validate screenshots and AI-generated text[cite: 11].  
**Job to be done:** "When I encounter suspicious content, I want a fast, consolidated fact-check and transparent credibility score so I can share confidently."[cite: 11]

### Persona 3 — The Enterprise Assessor (Talent Acquisition / Editor)
**Role:** Head of Talent Acquisition / Managing Editor at a digital publication.  
**Goal:** Verify that job applications, written assessments, and freelance submissions are genuinely human-created before investing time or publishing.  
**Current workaround:** Manual review, heuristic "gut instinct," and legacy plagiarism checkers.  
**Pain point:** Wasting costly interview hours or risking brand damage/SEO penalties on undisclosed AI-generated submissions.  
**Job to be done:** "When I receive a shortlisted application or article, I want to quickly verify its structural authenticity so I can prioritise genuine human effort."

---

## 3. Success Metrics

### North Star Metric
**Number of verifications per week per user[cite: 9]:** The total weekly volume of distinct content pieces processed through the TrustPulse engine.  
**Why this metric:** Because this MVP prioritizes zero time-to-value (TTV) without mandatory account creation, aggregate weekly scan volume is the purest proxy for market demand, repeated utility, and validation of the core pain point.

### Input Metrics
1. **Daily Active Verifications (DAV)[cite: 9]:** Measures the raw volume of verification requests.
2. **Extension activation rate[cite: 9]:** Measures adoption and integration into the user's daily browsing habit.
3. **Repeat usage within 48 hours[cite: 9]:** Acts as a proxy for retention in an auth-free environment.

### Guardrail Metrics
1. **Response time (Time-to-result)[cite: 9]:** Must deliver results in under 3 seconds for simple checks[cite: 9]. Speed is critical; a slow tool breaks the user's workflow.
2. **Accuracy feedback rating[cite: 9]:** False positive rates must remain low to preserve product credibility and user trust.

### Out-of-scope metrics 
- **Time spent on platform:** TrustPulse is a verification utility. A successful user journey is entering the site, getting a score in seconds, and leaving.
- **Behavior analysis of users[cite: 9]:** Explicitly deferred to minimize friction and respect privacy.

---

## 4. MVP Feature Set — MoSCoW Prioritisation

### Must Have (MVP cannot ship without these)
- **Credibility Score (0–100)[cite: 10]:** Instant visual indicator based on source reliability, AI likelihood, and manipulation likelihood[cite: 9].
- **Chrome Extension (One-Click Verification)[cite: 10]:** Right-click auto-capture to display popup results without leaving the page[cite: 9].
- **Image Authenticity Checker[cite: 10]:** Detects manipulation, runs reverse image search, and checks EXIF data[cite: 9].
- **AI Text Detection[cite: 10]:** GPT-style classifier that highlights suspicious segments and returns AI likelihood[cite: 9].
- **Explainability[cite: 10]:** Transparent reasoning outputting "Why this is fake" to build user trust[cite: 9].

### Should Have (high value, but MVP can ship without)
- **Screenshot Verification[cite: 10]:** OCR text extraction with 95% accuracy and claim cross-checking[cite: 9].
- **Fact-Check Summary[cite: 10]:** Scans search results and generates a summary identifying conflicting information[cite: 9].

### Could Have (nice to have, definitely Phase 2)
- **Video deepfake detection[cite: 10]:** Deferred to V2 due to high engineering effort (10 person-weeks)[cite: 10].
- **Mobile app[cite: 9]:** Moving beyond the browser extension for on-the-go verification[cite: 9].

### Will Not Have (explicitly out of scope — and why)
- **User Login/Profile System[cite: 10]:** Excluded to ensure zero time-to-value and minimize friction[cite: 9].
- **Report Misinformation Button & Bookmark/History[cite: 10]:** Low reach and impact relative to the core verification job[cite: 10].
- **Multi-language support[cite: 10]:** Deprioritized for MVP to focus strictly on English baseline accuracy[cite: 9].

---

## 5. RICE Prioritisation — Must-Have Features

| Feature | Reach (1–3) | Impact (1–3) | Confidence (0–1) | Effort (weeks) | RICE Score | Decision |
|---|---|---|---|---|---|---|
| Credibility Score (0–100) | 3 | 2 | 1.0 | 2 | **3.0** | BUILD |
| Chrome Extension (One-Click) | 3 | 3 | 0.8 | 3 | **2.4** | BUILD |
| Image Authenticity Checker | 3 | 3 | 0.9 | 4 | **2.02** | BUILD |
| AI Text Detection | 2 | 2 | 1.0 | 2 | **2.0** | BUILD |
| Explainability ("Why this is fake") | 3 | 2 | 0.7 | 3 | **1.4** | BUILD |

**RICE Formula:** (Reach × Impact × Confidence) ÷ Effort[cite: 10]  
**Build order:** Credibility Score → Chrome Extension → Image Authenticity Checker → AI Text Detection → Explainability based on RICE scores.

---

## 6. Phased Roadmap

### Phase 1 — MVP (Weeks 1–8)
**Goal:** Provide a fast, one-click verification utility for text and images.  
**Deliverables:**
- Web Uploader Sandbox and Chrome Extension[cite: 9]
- Image Authenticity & AI Text Detection classifiers[cite: 9, 10]
- Credibility Score (0-100) & Explainability UI[cite: 9, 10]  
**Success gate:** Maintain >99% uptime and deliver verification results in <3 seconds for simple checks[cite: 9].

### Phase 2 — Beta (Weeks 9–16)
**Goal:** Expand detection capabilities and platform accessibility.  
**Deliverables:**
- Video deepfake detection[cite: 9]
- Multi-language support[cite: 9]
- Mobile application[cite: 9]  
**Success gate:** Achieve high confidence metrics on deepfake models and successfully onboard mobile beta testers.

### Phase 3 — GA (Weeks 17–24)
**Goal:** Integrate directly into social pipelines and enterprise workflows.  
**Deliverables:**
- Social media platform integrations[cite: 9]
- WhatsApp deep-verification engine[cite: 9]
- Enterprise fact-check API[cite: 9]  
**Success gate:** Steady API volume growth and adoption by target enterprise personas.

---

## 7. Open Questions

Things that must be answered before or during development:
1. **Edge Cases:** How do we accurately classify and present mixed real+AI content, or satire that is easily mistaken for misinformation[cite: 9]?
2. **Abuse Prevention:** What is the optimal rate-limiting strategy to mitigate misuse of the open API or web interface[cite: 9]?
3. **Enterprise Accuracy Thresholds:** What detection accuracy rate is acceptable for enterprise customers before they trust the system to auto-reject an applicant?

---

## 8. Out of Scope for This Document
- Engineering architecture and technical implementation (e.g., Python/FastAPI backend, OCR model selection)[cite: 9]
- Pricing model and commercial terms
- Legal and IP considerations around AI detection methods

---

*PRD Version 1.0. Subject to revision after user feedback in Phase 1 beta.*  
*Author: Yash Gaidhani | XLRI 2026*
