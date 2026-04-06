# Taxonomy of Onboarding Operational Debt
**A Study of Failure Modes in Early-Stage B2B AI Deployments**

## Overview
This document categorizes recurring failure modes observed in the transition from MVP to Scale within high-touch AI startups. These patterns represent "Operational Debt" which refers to as the short-term shortcuts that create long-term bottlenecks in client activation.

---

## Risk Factor 1: Personality-Driven Accountability
**Definition:** The absence of a standardized Onboarding Owner, leading to a reliance on founder-led or developer-led delivery.

* **Pattern:** Founders act as the primary bridge for technical requirements; developers handle client-facing logistics to "save budget."
* **The Scaling Failure:** Onboarding quality becomes a function of individual bandwidth rather than process efficiency. 
* **Metric Impact:** High "Founder Tax" (hours spent per client) and inconsistent Time-to-First-Value (TTFV).

## Risk Factor 2: High-Entropy Communication (Verbal-Only)
**Definition:** Persistent reliance on synchronous, verbal knowledge transfer without durable asynchronous artifacts.

* **Pattern:** Critical technical constraints and configuration steps are discussed in meetings but never codified.
* **The Scaling Failure:** Information decays immediately after a call. Clients suffer from support cost overrun or gross margin erosion leading to repetitive support cycles.
* **Metric Impact:** Increased `repeat_questions_count` and reduced Client Satisfaction (CSAT).

## Risk Factor 3: Asset Scarcity & Self-Service Friction
**Definition:** Lack of centralized, accessible "Enablement Artifacts" (recordings, SSOT documentation, configuration guides).

* **Pattern:** Clients rely on ad-hoc chat messages (Slack/WhatsApp) or one-off emails for technical troubleshooting.
* **The Scaling Failure:** The internal team becomes a human "FAQ engine," preventing them from focusing on new deployments.
* **Metric Impact:** Correlation between "Low Technical Literacy" clients and exponential onboarding delays.

## Risk Factor 4: Scope Elasticity & Constraint Lag
**Definition:** Failure to negotiate technical trade-offs and solution framing during the initial 30 days.

* **Pattern:** Technical limitations are introduced late in the cycle; clients assume infinite feature flexibility.
* **The Scaling Failure:** Mid-onboarding "pivots" lead to developer burnout and broken delivery timelines.
* **Metric Impact:** High `scope_changes_post_onboarding` frequency.

## Epistemological Scope: Simulation vs. Discovery
This repository does not claim to discover new empirical truths from raw market data. Instead, it functions as a **Composite Simulation Study**. 

**What this study claims:**
* It quantifies the **sensitivity** of operational outcomes (TTFV, Satisfaction) to specific parameter changes (Ownership, Asset Depth).
* It uses a **theoretically-grounded generative model** to simulate "The Founder-Led Trap" common in B2B AI startups.
* The "Statistical Audit" is an internal validation step to ensure the generative engine accurately reflects the intended systemic behaviors before prescriptive analysis begins.

*Note: This is a composite case study based on observed patterns across early-stage B2B AI implementations.*