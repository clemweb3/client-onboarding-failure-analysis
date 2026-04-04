# 02: Research Design & Synthetic Logic
**Analytical Framework for B2B AI Onboarding Optimization**

---

## 1. Study Objective
This study uses a **Fuzzy-Inference-Model** to quantify the impact of operational variables on client activation. The goal is to move beyond binary outcomes to identify the specific gradients of friction caused by documentation gaps and undefined ownership structures.

## 2. Variable Taxonomy
Data is generated as **Membership Functions (0.0 to 1.0)** to simulate non-linear human behavior and professional competency levels.

### A. Predictor Variables (Inputs)
| Variable | Range | Statistical Definition |
| :--- | :--- | :--- |
| `client_tech_literacy` | `[0, 1]` | Cumulative distribution of client technical proficiency. |
| `asset_depth` | `[0, 1]` | Quantified availability of asynchronous enablement artifacts (SSOT). |
| `ownership_clarity` | `[0, 1]` | Probability of process-driven vs. personality-driven execution. |

### B. Outcome Metrics (KPIs)
| Variable | Range | Operational Significance |
| :--- | :--- | :--- |
| `repeat_query_rate` | `[0, 1]` | Metric for information retention and communication efficiency. |
| `ttfv_days` | `[10, 90]` | Time-to-First-Value. Primary indicator of onboarding velocity. |
| `cx_satisfaction` | `[1, 5]` | Composite score of perceived value relative to effort. |

---

## 3. Inference Logic & Interaction Effects
The Data Engine (`01_data_engine.ipynb`) enforces specific conditional logic to ensure the dataset reflects realistic operational constraints:

### Logic 1: Literacy-Asset Interaction
The relationship between documentation and query rates is non-linear.
* **Mechanism:** As `client_tech_literacy` decreases, the sensitivity to `asset_depth` increases. High-literacy clients maintain lower query rates even in low-asset environments due to self-correction capabilities.

### Logic 2: Resource Allocation & Bottlenecking
Founder involvement is modeled as a response to low `ownership_clarity`.
* **Mechanism:** In the absence of a defined owner, the probability of founder intervention increases to 0.85, introducing a single-point-of-failure that increases `ttfv_days`.

### Logic 3: Technical Constraint Negotiation (Scope Lock)
The impact of early vs. late scope definition on project timelines.
* **Mechanism:** Failure to lock scope within the first 14 days applies a stochastic multiplier (1.3x to 1.5x) to `ttfv_days` to simulate mid-project refactoring.

---

## 4. Validation Hypotheses
The 1,000-row dataset (`onboarding_data_v2.csv`) is generated to test three specific hypotheses:

1. **Resilience Variance:** `asset_depth` accounts for a higher percentage of variance in `ttfv_days` for low-literacy segments than for expert segments.
2. **Accountability Scaling:** Increasing `ownership_clarity` reduces `founder_involved` frequency without degrading `cx_satisfaction`.
3. **Communication Entropy:** `repeat_query_rate` serves as a leading indicator for onboarding delays and lower long-term satisfaction.

---

## 5. Technical Implementation Note
This design serves as the technical specification for the Python-based data synthesis. It ensures the resulting analysis is grounded in conditional probabilities and interaction terms rather than independent random variables.