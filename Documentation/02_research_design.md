# Research Design & Data Synthesis Framework
**Modeling Onboarding Friction in B2B AI Ecosystems**

## 1. Study Scope & Objectives
This study adopts a **Process-Oriented Exploratory** approach. We aim to model the relationship between internal enablement structures and external client activation metrics.

* **Primary Objective:** Quantify the "Invisible Tax" of poor documentation and undefined ownership.
* **Success Metric:** A synthetic dataset that demonstrates statistically significant friction patterns consistent with industry "Founder-Led" bottlenecks.

---

## 2. Variable Taxonomy & Data Dictionary
Each observation represents a **Unique Onboarding Lifecycle**.

### A. Contextual Predictors (Independent)
| Variable | Type | Strategic Significance |
| :--- | :--- | :--- |
| `client_tech_literacy` | Categorical | Dictates the "Support Floor." Low literacy requires higher asset density. |
| `onboarding_owner_assigned` | Boolean | Measures accountability. If False, `founder_involvement` probability increases. |
| `ssot_enabled` | Boolean | Represents the presence of a Single Source of Truth for project tracking. |

### B. Enablement Artifacts (Intervention)
| Variable | Type | Strategic Significance |
| :--- | :--- | :--- |
| `doc_asset_depth` | Integer (0-3) | Count of artifacts (Guides, Videos, FAQs) provided to the client. |
| `scope_lock_early` | Boolean | Whether technical constraints were negotiated in the first 14 days. |

### C. Friction & Activation Metrics (Outcome)
| Variable | Type | Strategic Significance |
| :--- | :--- | :--- |
| `repeat_query_rate` | Float | Proxy for information decay. High rate indicates "Verbal-Only" failure. |
| `ttfv_days` | Integer | Time-to-First-Value. The ultimate metric for onboarding efficiency. |
| `cx_satisfaction` | Float (1-5) | Client sentiment, modeled as a function of friction vs. value. |

---

## 3. Stochastic Generation Logic (The "Mental Model")
To ensure the data is "Interview-Proof," the generation engine follows these behavioral laws:

### Law 1: The Literacy-Documentation Interaction
Friction is not linear. A "High Tech" client can survive poor documentation. A "Low Tech" client cannot.
* **Logic:** `repeat_query_rate` is weighted by `(1 / tech_literacy) * (1 / doc_asset_depth)`.

### Law 2: The Founder Scalability Gap
Founder involvement (high-cost resource) should correlate with *undefined* ownership.
* **Logic:** `P(founder_involved | owner_assigned=False) = 0.85`.

### Law 3: The "Scope Creep" Penalty
Failure to "Scope Lock" early leads to mid-project pivots.
* **Logic:** If `scope_lock_early` is False, `ttfv_days` receives a +30% penalty and `cx_satisfaction` drops.

---

## 4. Validation & Reproducibility
The dataset is validated against **three "Business Truths"**:
1.  **Ownership Check:** Defined owners must result in lower founder hours.
2.  **Asset Check:** Increased `doc_asset_depth` must show a downward trend in `repeat_query_rate`.
3.  **Activation Check:** `ttfv_days` should show higher variance in "Low Structure" environments.