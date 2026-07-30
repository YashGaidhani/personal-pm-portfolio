# TrustPulse — Product Requirements Document

**Version:** 1.0  
**Author:** Yash Gaidhani  
**Date:** July 2026  
**Status:** MVP Definition Complete  
**Product Type:** AI verification layer (B2B SaaS, enterprise / creator economy)

---

## 1. Problem Statement

The proliferation of advanced Generative AI has eroded a fundamental pillar of digital ecosystems: content authenticity. As AI-generated text becomes increasingly indistinguishable from human-created content, platforms, publishers, and enterprises face a critical capability gap. They can no longer reliably verify whether the content, identities, work samples, or credentials they process are the product of human effort or algorithmic generation. 

This indistinguishability creates severe trust deficits and operational bottlenecks in high-stakes environments. Talent acquisition teams risk wasting expensive interview cycles on candidates using AI to fabricate assignments; media publications risk severe reputational damage by publishing AI-generated articles under human bylines; and educational institutions struggle to enforce academic integrity without overwhelming faculty with manual investigations. 

Current workarounds—such as legacy plagiarism checkers, manual review, and heuristic "gut instinct"—are fundamentally unequipped to detect probabilistic AI text generation. TrustPulse is designed to bridge this gap by providing a definitive, integrated AI verification layer that restores confidence in digital submissions across enterprise workflows.

---

## 2. Target Personas

### Persona 1 — Enterprise Talent Acquisition
**Role:** Head of Talent Acquisition at a mid-to-large enterprise  
**Goal:** Verify that job applications and submitted work samples are genuinely human-created before investing interview time.  
**Current workaround:** Manual review, gut instinct, and legacy plagiarism checkers that do not detect modern LLM generation.  
**Pain point:** Wasting costly engineering and management interview hours on candidates who artificially inflated their technical or written assessments using AI.  
**Job to be done:** "When I receive a shortlisted application, I want to quickly verify its authenticity so I can prioritise candidates who actually wrote their own materials."

### Persona 2 — Editorial & Publishing
**Role:** Content Editor at a digital media publication  
**Goal:** Verify that submitted articles and freelance pitches are not AI-generated before publishing them under a human byline.  
**Current workaround:** Searching for generic AI phrasing patterns manually and running copy through basic SEO duplicate-content checkers.  
**Pain point:** The risk of severe brand damage and SEO penalties if the publication is caught publishing undisclosed, hallucination-prone AI content.  
**Job to be done:** "When a freelancer submits an article, I want to verify it is genuinely their work so I can protect our editorial integrity."

### Persona 3 — Academic Integrity
**Role:** Academic Integrity Officer at a university  
**Goal:** Verify that student submissions are not AI-generated without burdening faculty with manual review and subjective accusations.  
**Current workaround:** Relying on professors to flag suspicious shifts in a student's writing style.  
**Pain point:** The lack of objective, standardized data to support academic misconduct proceedings, leading to messy disputes between students and faculty.  
**Job to be done:** "When a student submits an assignment, I want an automated signal on whether it is likely AI-generated so I can flag only the cases that warrant investigation."

---

## 3. Success Metrics

### North Star Metric
**Verified Submissions Processed per Week:** The total number of content submissions run through TrustPulse verification per week, weighted by the percentage that received a confidence score above 80%.  
**Why this metric:** This perfectly captures both volume (adoption and integration into daily workflows) and system efficacy. If the system frequently returns low-confidence scores, it isn't solving the core problem. A high volume of high-confidence scores proves the utility is working as intended.

### Input Metrics
1. **API Call Volume:** Measures the number of programmatic verification requests from enterprise HR/CMS integrations (indicating automated workflow adoption).
2. **Manual Upload Frequency per Active User:** Measures how often individual users (e.g., editors, professors) return to the web interface to verify single documents.

### Guardrail Metrics
1. **False Positive Rate (FPR):** We must not compromise human trust by incorrectly flagging genuinely human-written content as AI. A high FPR destroys product credibility.
2. **Average Processing Latency:** Verification must occur in under 3 seconds per standard document to ensure we are accelerating, not blocking, enterprise workflows.

### Out-of-scope metrics 
- Time spent on platform — TrustPulse is a utilitarian verification tool, not an engagement product. We want users to get their answer and leave quickly.

---

## 4. MVP Feature Set — MoSCoW Prioritisation

### Must Have (MVP cannot ship without these)
- **Document Upload Interface:** A clean web UI allowing drag-and-drop uploads for PDF, DOCX, and plain text formats.
- **AI Probability Scoring Engine:** An algorithm that returns an AI vs. human probability score alongside a clear, 3-tier confidence display (High/Medium/Low).
- **Sentence-Level Highlighting:** Visual UI overlays indicating exactly which specific sentences or paragraphs are most likely AI-generated to provide explainability.
- **Enterprise API Endpoint:** A REST API allowing seamless integration into existing Applicant Tracking Systems (ATS) and Content Management Systems (CMS).

### Should Have (high value, but MVP can ship without)
- **Batch Processing Module:** Ability for high-volume users (e.g., HR teams reviewing 100+ applications) to upload and process multiple documents simultaneously.
- **Compliance Audit Trail:** A timestamped, immutable log of all verifications performed by an organization for legal and internal compliance purposes.

### Could Have (nice to have, definitely Phase 2)
- **Browser Extension:** Inline verification directly over web text (e.g., scanning LinkedIn posts or web-based CMS editors on the fly).

### Will Not Have (explicitly out of scope — and why)
- **Real-time detection during content creation:** Intercepting keystrokes is a fundamentally different, highly complex technical challenge reserved for Phase 2+.
- **Video/Audio Verification:** Analyzing deepfakes requires a completely different architectural stack and model training paradigm; MVP is strictly text-based.
- **User-generated training data contributions:** Using customer uploads to train our models introduces massive data privacy and legal risks for enterprise clients.

---

## 5. RICE Prioritisation — Must-Have Features

| Feature | Reach (1–10) | Impact (1–3) | Confidence (%) | Effort (weeks) | RICE Score | Decision |
|---|---|---|---|---|---|---|
| AI Probability Scoring Engine | 10 | 3 | 90% | 4 | **6.75** | BUILD |
| Document Upload Interface | 8 | 3 | 100% | 2 | **12.0** | BUILD |
| Enterprise API Endpoint | 6 | 3 | 90% | 3 | **5.4** | BUILD |
| Sentence-Level Highlighting | 10 | 2 | 70% | 4 | **3.5** | BUILD |
| Batch Processing Module | 5 | 2 | 80% | 3 | **2.6** | DEFER |
| Compliance Audit Trail | 4 | 1 | 90% | 2 | **1.8** | DEFER |

**RICE Formula:** (Reach × Impact × Confidence) ÷ Effort  
**Build order:** Document Upload Interface → AI Probability Scoring Engine → Enterprise API Endpoint → Sentence-Level Highlighting based on RICE scores and technical dependencies.

---

## 6. Phased Roadmap

### Phase 1 — MVP (Weeks 1–8)
**Goal:** Prove core detection accuracy and establish initial workflow integration.  
**Deliverables:**
- Foundational text classification model
- Single-document web upload interface (PDF, DOCX, TXT)
- High/Medium/Low confidence scoring UI
- V1 REST API for enterprise ATS/CMS integration  
**Success gate:** Achieve >90% accuracy on our internal benchmarking dataset and successfully onboard 3 enterprise design partners utilizing the API.

### Phase 2 — Beta (Weeks 9–16)
**Goal:** Scale processing volume and provide deeper explainability.  
**Deliverables:**
- Sentence-level highlighting engine for granular review
- Batch processing capabilities via UI and API
- Basic compliance audit logs  
**Success gate:** System processes >10,000 verified submissions per week with a False Positive Rate of less than 1%.

### Phase 3 — GA (Weeks 17–24)
**Goal:** Expand surface area and achieve self-serve product-led growth.  
**Deliverables:**
- Chrome browser extension for inline verification
- Self-serve developer portal and automated API key provisioning
- Native integrations with top 3 ATS platforms (e.g., Workday, Greenhouse)  
**Success gate:** 20% month-over-month growth in Weekly Active Connected Users and positive unit economics on API compute costs.

---

## 7. Open Questions

Things that must be answered before or during development:
1. **Accuracy Thresholds:** What detection accuracy rate is "good enough" for enterprise HR customers before they trust the system to auto-reject a candidate? What is the acceptable ratio of false positives to false negatives in each persona's context?
2. **Architecture:** Should we build a single-tenant or multi-tenant architecture in Phase 1, given the strict data privacy requirements of enterprise ATS systems?
3. **Adversarial Evasion:** How rapidly will we need to update our classification models to handle adversarial users utilizing tools explicitly designed to bypass AI detectors (e.g., prompt engineering for "burstiness" and "perplexity")?
4. **Data Retention:** What is our legal liability regarding the temporary storage of submitted documents, and what should our default data-purging cadence be?

---

## 8. Out of Scope for This Document
- Engineering architecture and technical implementation details
- Pricing model, tier structures, and commercial terms
- Legal, IP, and compliance considerations regarding AI detection methods

---

*PRD Version 1.0. Subject to revision after user feedback in Phase 1 beta.*  
*Author: Yash Gaidhani | XLRI 2026*
