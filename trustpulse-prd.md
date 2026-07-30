# TrustPulse — Product Requirements Document

**Version:** 1.0 (MVP)  
**Author:** Yash Gaidhani  
**Date:** 2025  
**Status:** MVP Definition Complete  
**Product Type:** AI verification layer (B2C/B2B utility)  

---

## 1. Problem Statement

By 2025, the rapid explosion of Generative AI has made synthetic content, manipulated images, and AI-generated text virtually indistinguishable from human-created work. Students, researchers, and professionals frequently encounter misleading, manipulated, or AI-generated content on platforms like Instagram and WhatsApp, but lack a fast, reliable way to verify its authenticity. 

Verification today is slow, manual, inconsistent, and stressful, leading to confusion, psychological discomfort, and severe reputational risk. Existing fact-check tools require multiple steps, breaking the user's natural workflow. Furthermore, enterprises face a massive operational bottleneck, unable to reliably verify if the text, credentials, or work samples they process are human-generated.

TrustPulse solves this by providing a one-click verification utility. Built rapidly using Vibe coding on Lovable, the MVP leverages NLP and OCR to analyze content structure and instantly output an authenticity score. By functioning as a frictionless, single-player sandbox, users can instantly verify claims, images, and text without a complex onboarding process.

---

## 2. Target Personas

### Persona 1 — Aarav Mehta: "The Fast-Scrolling Student"
**Role:** Undergraduate / MBA student consuming short-form content and WhatsApp forwards.  
**Goal:** Stay informed without being misled and avoid embarrassment from sharing fake news.  
**Current workaround:** Uses comments or Google to check misinformation, spending <1–2 minutes verifying anything.  
**Pain point:** No quick way to verify screenshots, reels, and images; fears being misled but lacks a tool inside his existing workflow.  
**Job to be done:** "When I encounter suspicious or emotionally charged online content, I want to verify its authenticity quickly so I feel confident before sharing or believing it."

### Persona 2 — Riya Sharma: "The Skeptical Verifier"
**Role:** Graduate / MBA student / Researcher who manually cross-checks sources.  
**Goal:** Maintain reputation as "informed and credible" and avoid circulating misinformation.  
**Current workaround:** Googles suspicious content and cross-checks across multiple news sites.  
**Pain point:** Verifying news takes too long, and it is incredibly hard to validate screenshots and AI-generated text.  
**Job to be done:** "When I encounter suspicious content, I want a fast, consolidated fact-check and transparent credibility score so I can share confidently."

### Persona 3 — The Enterprise Assessor (Talent Acquisition / Editor)
**Role:** Head of Talent Acquisition / Managing Editor at a digital publication.  
**Goal:** Verify that job applications, written assessments, and freelance submissions are genuinely human-created before investing time or publishing.  
**Current workaround:** Manual review, heuristic "gut instinct," and legacy plagiarism checkers.  
**Pain point:** Wasting costly interview hours or risking brand damage/SEO penalties on undisclosed AI-generated submissions.  
**Job to be done:** "When I receive a shortlisted application or article, I want to quickly verify its structural authenticity so I can prioritise genuine human effort."

---

## 3. Success Metrics

### North Star Metric
**Number of verifications per week per user:** The total weekly volume of distinct content pieces processed through the TrustPulse engine.  
**Why this metric:** Because this MVP prioritizes zero time-to-value (TTV) without mandatory account creation, aggregate weekly scan volume is the purest proxy for market demand, repeated utility, and validation of the core pain point.

### Input Metrics
1. **Daily Active Verifications (DAV):** Measures the raw volume of verification requests.
2. **Extension activation rate:** Measures adoption and integration into the user's daily browsing habit.
3. **Repeat usage within 48 hours:** Acts as a proxy for retention in an auth-free environment.

### Guardrail Metrics
1. **Response time (Time-to-result):** Must deliver results in under 3 seconds for simple checks. Speed is critical; a slow tool breaks the user's workflow.
2. **Accuracy feedback rating:** False positive rates must remain low to preserve product credibility and user trust.

### Out-of-scope metrics 
- **Time spent on platform:** TrustPulse is a verification utility. A successful user journey is entering the site, getting a score in seconds, and leaving.
- **Behavior analysis of users:** Explicitly deferred to minimize friction and respect privacy.

---

## 4. MVP Feature Set — MoSCoW Prioritisation

### Must Have (MVP cannot ship without these)
- **Credibility Score (0–100):** Instant visual indicator based on source reliability, AI likelihood, and manipulation likelihood.
- **Chrome Extension (One-Click Verification):** Right-click auto-capture to display popup results without leaving the page.
- **Image Authenticity Checker:** Detects manipulation, runs reverse image search, and checks EXIF data.
- **AI Text Detection:** GPT-style classifier that highlights suspicious segments and returns AI likelihood.
- **Explainability:** Transparent reasoning outputting "Why this is fake" to build user trust.

### Should Have (high value, but MVP can ship without)
- **Screenshot Verification:** OCR text extraction with 95% accuracy and claim cross-checking.
- **Fact-Check Summary:** Scans search results and generates a summary identifying conflicting information.

### Could Have (nice to have, definitely Phase 2)
- **Video deepfake detection:** Deferred to V2 due to high engineering effort (10 person-weeks).
- **Mobile app:** Moving beyond the browser extension for on-the-go verification.

### Will Not Have (explicitly out of scope — and why)
- **User Login/Profile System:** Excluded to ensure zero time-to-value and minimize friction.
- **Report Misinformation Button & Bookmark/History:** Low reach and impact relative to the core verification job.
- **Multi-language support:** Deprioritized for MVP to focus strictly on English baseline accuracy.

---

## 5. RICE Prioritisation — Must-Have Features

| Feature | Reach (1–3) | Impact (1–3) | Confidence (0–1) | Effort (weeks) | RICE Score | Decision |
|---|---|---|---|---|---|---|
| Credibility Score (0–100) | 3 | 2 | 1.0 | 2 | **3.0** | BUILD |
| Chrome Extension (One-Click) | 3 | 3 | 0.8 | 3 | **2.4** | BUILD |
| Image Authenticity Checker | 3 | 3 | 0.9 | 4 | **2.02** | BUILD |
| AI Text Detection | 2 | 2 | 1.0 | 2 | **2.0** | BUILD |
| Explainability ("Why this is fake") | 3 | 2 | 0.7 | 3 | **1.4** | BUILD |

**RICE Formula:** (Reach × Impact × Confidence) ÷ Effort  
**Build order:** Credibility Score → Chrome Extension → Image Authenticity Checker → AI Text Detection → Explainability based on RICE scores.

---

## 6. Phased Roadmap

### Phase 1 — MVP (Weeks 1–8)
**Goal:** Provide a fast, one-click verification utility for text and images.  
**Deliverables:**
- Web Uploader Sandbox and Chrome Extension
- Image Authenticity & AI Text Detection classifiers
- Credibility Score (0-100) & Explainability UI  
**Success gate:** Maintain >99% uptime and deliver verification results in <3 seconds for simple checks.

### Phase 2 — Beta (Weeks 9–16)
**Goal:** Expand detection capabilities and platform accessibility.  
**Deliverables:**
- Video deepfake detection
- Multi-language support
- Mobile application  
**Success gate:** Achieve high confidence metrics on deepfake models and successfully onboard mobile beta testers.

### Phase 3 — GA (Weeks 17–24)
**Goal:** Integrate directly into social pipelines and enterprise workflows.  
**Deliverables:**
- Social media platform integrations
- WhatsApp deep-verification engine
- Enterprise fact-check API  
**Success gate:** Steady API volume growth and adoption by target enterprise personas.

---

## 7. Open Questions

Things that must be answered before or during development:
1. **Edge Cases:** How do we accurately classify and present mixed real+AI content, or satire that is easily mistaken for misinformation?
2. **Abuse Prevention:** What is the optimal rate-limiting strategy to mitigate misuse of the open API or web interface?
3. **Enterprise Accuracy Thresholds:** What detection accuracy rate is acceptable for enterprise customers before they trust the system to auto-reject an applicant?

---

## 8. Out of Scope for This Document
- Engineering architecture and technical implementation (e.g., Python/FastAPI backend, OCR model selection)
- Pricing model and commercial terms
- Legal and IP considerations around AI detection methods

---

*PRD Version 1.0. Subject to revision after user feedback in Phase 1 beta.*  
*Author: Yash Gaidhani | XLRI 2026*
