# Variables and Definitions

## Purpose of This Document

This document defines the variables used in the synthetic dataset for this case study. The variables are derived directly from observed onboarding failure points and are intended to represent **signals of onboarding friction**, not exact real-world measurements.

All variables are designed to be:
- Interpretable by non-technical stakeholders
- Actionable for process improvement
- Realistic within early-stage product environments

---

## Variable Design Principles

The variables in this case study follow three principles:

1. **Behavioral over technical**  
   Variables reflect client and team behavior rather than system internals.

2. **Observable in practice**  
   Each variable represents something a team could reasonably track.

3. **Directly tied to failure points**  
   No variable exists without a clear link to an onboarding issue.

---

## Core Entity: Client Onboarding Instance

Each row in the dataset represents a single client onboarding instance.

---

## Variable Definitions

### Client Characteristics

| Variable Name | Description |
|-------------|------------|
| `client_id` | Unique identifier for each client (synthetic) |
| `client_industry` | Industry category of the client |
| `client_technical_level` | Categorical indicator of client technical familiarity (Low, Medium, High) |
| `client_team_size` | Estimated size of the client’s internal team |

---

### Onboarding Structure Variables

| Variable Name | Description |
|-------------|------------|
| `onboarding_owner_defined` | Whether a single onboarding owner was clearly assigned (Yes/No) |
| `founder_involved` | Whether founders were directly involved in onboarding (Yes/No) |
| `number_of_onboarding_calls` | Total onboarding-related calls conducted |
| `onboarding_duration_days` | Days from kickoff to initial activation |

---

### Communication and Enablement Variables

| Variable Name | Description |
|-------------|------------|
| `documentation_provided` | Whether written documentation was provided (Yes/No) |
| `recorded_walkthrough_available` | Whether recorded walkthroughs were shared (Yes/No) |
| `enablement_artifact_count` | Number of onboarding artifacts provided |
| `single_source_of_truth` | Whether a central repository was used (Yes/No) |

---

### Expectation and Negotiation Variables

| Variable Name | Description |
|-------------|------------|
| `solution_options_presented` | Whether multiple solution options were presented (Yes/No) |
| `scope_constraints_discussed_early` | Whether limitations were discussed upfront (Yes/No) |
| `scope_changes_post_onboarding` | Whether scope changed after onboarding started (Yes/No) |

---

### Friction and Outcome Indicators

| Variable Name | Description |
|-------------|------------|
| `repeat_questions_count` | Number of repeated client questions |
| `support_requests_first_30_days` | Support requests within first 30 days |
| `time_to_first_value_days` | Days until client achieved initial value |
| `onboarding_satisfaction_score` | Client-reported satisfaction (1–5, synthetic) |
| `onboarding_status` | Outcome classification (Successful, Delayed, Friction-heavy) |

---

## Relationship to Failure Points

Each variable maps to one or more onboarding failure modes:

- Ownership ambiguity → `onboarding_owner_defined`, `founder_involved`
- Verbal-only transfer → `documentation_provided`, `repeat_questions_count`
- Missing enablement → `enablement_artifact_count`, `single_source_of_truth`
- Expectation misalignment → `solution_options_presented`, `scope_changes_post_onboarding`
- Lack of iteration → `support_requests_first_30_days`, `time_to_first_value_days`

---

## Notes on Interpretation

- These variables are proxies, not perfect measurements
- Directional trends are more meaningful than absolute values
- The intent is to support reasoning and discussion, not statistical certainty

---

## Summary

By explicitly defining these variables, this case study translates qualitative onboarding experiences into a structured framework that supports analysis, reflection, and decision-making.
