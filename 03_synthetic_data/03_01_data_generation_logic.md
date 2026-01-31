# Synthetic Data Generation Logic

## Purpose of This Document

This document explains how synthetic data is generated for this case study and what assumptions guide its construction.

The intent is not to recreate historical events, but to produce a **plausible operational dataset** that reflects common onboarding behaviors and failure patterns observed in early-stage software environments.

---

## Why Synthetic Data Is Used

Real client onboarding data is often:
- Confidential
- Fragmented across tools
- Inconsistent or undocumented

Using synthetic data allows this case study to:
- Preserve confidentiality
- Maintain analytical transparency
- Explicitly document assumptions instead of hiding them

Synthetic data is treated as a modeling tool, not a substitute for reality.

---

## Core Assumptions

The synthetic dataset is generated based on the following assumptions:

1. Clients vary significantly in technical familiarity  
2. Onboarding outcomes are influenced more by process design than by client intent  
3. Missing enablement artifacts increase onboarding friction  
4. Early expectation-setting reduces downstream scope changes  
5. Founder involvement compensates for missing systems but does not scale

These assumptions are grounded in observed patterns, not theoretical optimization.

---

## Data Generation Strategy

### Unit of Analysis

- Each row represents one client onboarding instance
- All clients are independent
- No time-series dependencies are assumed

---

### Variable Generation Logic

#### Client Characteristics
- `client_technical_level` is sampled categorically (Low, Medium, High)
- Lower technical levels increase likelihood of friction indicators
- Client size mildly correlates with onboarding complexity

#### Onboarding Structure
- `onboarding_owner_defined` is randomly assigned with bias toward "No"
- `founder_involved` is more likely when ownership is undefined
- More onboarding calls correlate with longer onboarding duration

#### Communication and Enablement
- Documentation and recordings are probabilistic, not guaranteed
- Presence of enablement artifacts reduces repeated questions
- Single source of truth is rare in early-stage settings

#### Expectation and Negotiation
- Solution options are inconsistently presented
- Early scope discussion reduces probability of post-onboarding changes
- Scope changes increase support requests

#### Outcomes and Friction
- `repeat_questions_count` increases when documentation is missing
- `time_to_first_value_days` increases with higher friction
- Onboarding satisfaction is inversely related to friction indicators
- `onboarding_status` is derived from combined friction signals

---

## Controlled Relationships

The synthetic data intentionally encodes the following relationships:

- Missing documentation → higher repeat questions  
- No onboarding owner → founder dependency  
- No scope negotiation → post-onboarding scope changes  
- Higher friction → delayed time to value  

These relationships are deterministic at the logic level but probabilistic in values.

---

## What This Data Can and Cannot Show

### Can Show
- Directional trends
- Tradeoffs between process choices
- Relative impact of enablement practices

### Cannot Show
- Exact causal strength
- Financial impact
- Generalized industry benchmarks

---

## Validation Philosophy

Synthetic data is validated by:
- Logical consistency checks
- Boundary conditions (no impossible values)
- Alignment with real-world intuition

Statistical rigor is secondary to narrative and decision clarity.

---

## Summary

This synthetic dataset is designed to support reasoning about onboarding systems, not to prove definitive truths. Its value lies in making assumptions explicit and analyzable.
