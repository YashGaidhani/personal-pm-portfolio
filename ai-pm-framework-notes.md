# AI PM Framework Notes

**Author:** Yash Gaidhani  
**Context:** Synthesised from building AI products, studying enterprise AI deployments, and applying classical PM frameworks to AI-specific challenges.  
**Purpose:** Personal working notes — how standard PM frameworks change when the product is AI-powered.

---

## 1. Jobs to Be Done (JTBD) — How It Changes for AI Products

**Standard JTBD:** Users "hire" a product to get a specific job done. The PM understands the job and builds the tool (the features) for the user to solve it.

**The AI twist:** With AI products, the "job" has mutated from *enablement* to *execution*.

Historically, software functioned as a tool. If the user's job was "restock weekly groceries," classical PMs built intuitive interfaces that enabled the user to execute that job faster. With the emergence of AI, software functions as an agent. The user's expectation has shifted from wanting a tool that saves them time, to wanting a system that executes the workflow autonomously (e.g., predicting the basket and placing the order). 

The PM's role is no longer just designing features for users to click; it is designing the embedded workflows, guardrails, and delegations required for the AI to execute the job on the user's behalf. The execution itself is now an inherent part of the Job To Be Done. Furthermore, enterprise AI introduces a complex, role-centric JTBD structure where the economic buyer, the champion, and the end-user often have conflicting jobs that the PM must navigate simultaneously.

---

## 2. Kano Model — How It Changes for AI Products

**Standard Kano:** Features are categorized into Basic (must-have), Performance (more is better), or Delighter (unexpected joy). Historically, these three curves were distinct, and features moved between them slowly.

**The AI twist:** AI products experience extreme category decay, compressing the Kano curve entirely.

With traditional software, user expectations evolve linearly. With AI, expectations are accelerating exponentially. A feature that was a pure Delighter just 12 months ago—such as NLP-based text summarization—has already degraded into a Basic expectation. The gap between what delights a user and what a user simply expects as a baseline is shrinking rapidly.

While the fundamental Kano framework remains valid, the velocity of movement across its categories has multiplied. Consequently, PMs can no longer rely on simply adding generic "AI capabilities" to delight users. Because the underlying technology is no longer the differentiator, finding true Delighters now requires significantly deeper design thinking and creative problem-solving, focusing on novel, end-to-end workflow transformations.

---

## 3. North Star Metric — How It Changes for AI Products

**Standard North Star:** Historically, engagement was the ultimate proxy for value. Maximizing "time spent on platform" was the goal, signaling product stickiness.

**The AI twist:** AI fundamentally flips this paradigm. For AI-driven utility products, high time on platform is often a counter-metric indicating a flawed AI strategy.

Because the core objective of AI is to take over the execution layer, its primary value proposition is radically reducing the user's time and effort. If a user is spending significant time managing, correcting, or interacting with an AI agent to complete a task, the AI is creating friction rather than removing it. Consequently, traditional engagement metrics are rapidly losing their relevance.

The true North Star Metric (NSM) for an AI product must measure the actual value delivered via time and effort reduction (e.g., "Autonomous Task Completion Rate"). Furthermore, NSMs must explicitly evaluate the health and accuracy of the underlying AI agent, shifting PMs toward a composite measurement strategy: a primary NSM focused on user effort reduction, supported by metrics that track the AI agent's execution accuracy.

---

## 4. The Framework I Found Missing — The 3-Phase AI Lifecycle Framework

Standard product development lifecycles fail to account for the unique implementation risks of AI. Through deploying AI solutions, I found that success is dictated by a **70/20/10 ratio**: 70% Change Management, 20% Data Readiness, and only 10% Technical Feasibility. To manage this, PMs must evaluate AI features through a sequenced, 3-phase framework:

### Phase 1: Pre-Deployment (Foundational Readiness)
*   **Change Management & Process Evaluation (The 70%):** Tech is just an enabler. If you deploy AI into a broken organizational process, it will only amplify those flaws and accelerate failure. Assessing the firm's capacity for change management and ensuring well-defined processes must happen *before* writing any code. Good processes + change management yield amplified ROI.
*   **Data Readiness (The 20%):** Data is the backbone of any AI agent. PMs must verify data alignment, processing pipelines, and the infrastructure required for continuous iteration.
*   **Tech Feasibility (The 10%):** While technical capabilities are growing rapidly and rarely act as the primary bottleneck anymore, establishing baseline feasibility remains a necessary check.

### Phase 2: Deployment (Execution & Trust)
*   **AI Explainability & Confidence:** These two factors are deeply interlinked. High explainability directly yields high user confidence. Because the AI acts as the enabler, designing UI patterns that clearly explain *why* an AI made a decision is critical for enterprise adoption and mitigating brand risk during launch.

### Phase 3: Post-Deployment (Continuous Optimization)
*   **AI Model Evaluation:** Unlike traditional software that remains static until updated, AI products drift. PMs must continuously evaluate the deployed agents against the pre-defined business problem, tracking metrics like accuracy, latency, bias, and data drift. This governs the continuous improvement cycle, ensuring the model's experience curve trends upward.

---

*These are working notes, updated as I build and study AI products. Last updated: 2025.*  
*— Yash Gaidhani | XLRI 2026 | linkedin.com/in/yashgaidhani*
