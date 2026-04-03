# 02: Research Design & Synthetic Logic
**Modeling High-Entropy Onboarding in B2B AI Ecosystems**

---

## 1. Study Objective
This study adopts a **Fuzzy-Inference-Modeling** approach to quantify "Operational Debt" in early-stage startup onboarding. We aim to move beyond binary "Success/Failure" metrics to understand the **Gradient of Friction** created by poor documentation and undefined ownership.

## 2. The Fuzzy Variable Taxonomy
To simulate realistic human behavior, we represent client and process traits as **Membership Functions (0.0 to 1.0)** rather than static categories.

### A. Inputs (The Predictors)
| Variable | Range | Definition |
| :--- | :--- | :--- |
| `client_tech_literacy` | `[0, 1]` | **Fuzzy Set:** {Novice, Competent, Expert}. Dictates the "Support Floor." |
| `asset_depth` | `[0, 1]` | **Fuzzy Set:** {Sparse, Standard, Comprehensive}. Measures documentation/SSOT availability. |
| `ownership_clarity` | `[0, 1]` | **Fuzzy Set:** {Ambiguous, Defined}. Probability of founder interference vs. process autonomy. |

### B. Outputs (The Activation Metrics)
| Variable | Range | Strategic Significance |
| :--- | :--- | :--- |
| `repeat_query_rate` | `[0, 1]` | Proxy for **Information Decay**. High entropy = wasted internal bandwidth. |
| `ttfv_days` | `[10, 90]` | **Time-to-First-Value**. The ultimate lagging indicator of onboarding health. |
| `cx_satisfaction` | `[1, 5]` | Weighted sentiment score based on "Perceived Value" vs. "Effort Expended." |

---

## 3. The "Fuzzy" Rule Base (Inference Logic)
The Data Engine (`01_data_engine.ipynb`) enforces the following behavioral laws to ensure the dataset is "Intelligent":

### Law 1: The Literacy-Asset Interaction
Friction is non-linear. Expert clients can "self-correct" in the absence of documentation; novices hit a total bottleneck.
* **Rule:** IF `tech_literacy` is **Novice** AND `asset_depth` is **Sparse**, THEN `repeat_query_rate` is **Extreme**.

### Law 2: The Founder Scaling Trap
Founder involvement provides high-quality help but creates a single-point-of-failure and discourages process autonomy.
* **Rule:** IF `ownership_clarity` is **Ambiguous**, THEN `founder_involvement` is **High** AND `ttfv_days` increases due to bottlenecking.

### Law 3: The "Scope Creep" Penalty
"Scope Elasticity" (failing to lock constraints early) looks fast in week 1 but leads to "Death Spirals" in week 4.
* **Rule:** IF `scope_lock_early` is **False**, THEN `ttfv_days` receives a **Stochastic Multiplier (1.3x - 1.5x)**.

---

## 4. Validation & Reproducibility
The resulting 1,000-row dataset (`onboarding_data_v2.csv`) is validated against three **Hypotheses**:

1. **The Resilience Hypothesis:** `asset_depth` has a significantly higher impact on `ttfv_days` for "Low Literacy" clients than for "Expert" clients.
2. **The Efficiency Hypothesis:** Defined `ownership_clarity` reduces `founder_involvement` without negatively impacting `cx_satisfaction`.
3. **The Activation Hypothesis:** High `repeat_query_rate` (Information Decay) is a stronger predictor of onboarding delays than initial client team size.

---

## 5. Intended Use
This research design serves as the **Technical Specification** for the Data Synthesis Engine. By encoding these human-centric rules into the data generation process, the resulting analysis reflects the complex trade-offs found in real-world B2B AI deployments.