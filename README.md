# B2B AI Onboarding Optimization: A Simulation Case Study

### Overview

This repository models onboarding failure patterns in early-stage B2B AI startups using a theoretically grounded generative simulation. The goal is to move beyond anecdotal observation and quantify how specific operational variables — ownership clarity, documentation coverage, and scope governance — drive activation delays and client satisfaction outcomes.

This is a composite case study based on observed patterns across early-stage B2B AI implementations. It does not claim empirical discovery. It quantifies the sensitivity of operational outcomes to parameter changes under a defined generative model.

---

### The Problem

Early-stage startups frequently encounter a specific class of onboarding failure during the transition from early sales to repeatable delivery:

- **Undefined ownership:** Onboarding execution depends on individual availability rather than process, causing inconsistent Time-to-First-Value (TTFV) across clients.
- **Verbal-only knowledge transfer:** Critical configuration steps and technical constraints are communicated in meetings but never documented, leading to high repeat inquiry rates.
- **Sparse documentation:** Clients without a centralized reference point generate disproportionate support load, particularly those with lower technical proficiency.
- **Late scope definition:** Technical constraints introduced after onboarding begins apply a measurable delay multiplier to activation timelines.

---

### Objectives

1. Synthesize a simulation dataset that encodes the conditional relationships between operational inputs and client activation outcomes.
2. Validate that the generative model accurately reflects the intended systemic behaviors through inferential testing.
3. Identify the client segments most exposed to activation risk and quantify the marginal impact of each intervention.
4. Produce a prescriptive brief with an interactive sensitivity tool that projects outcome changes under different operational scenarios.

---

### Methodology

**Data synthesis:** 1,000 client observations generated using truncated normal distributions (NumPy/SciPy) to represent continuous operational variables as membership functions. Key variables: `ownership_clarity`, `asset_depth`, `tech_literacy`, `scope_lock_day`.

**Generative logic:** Conditional interaction rules encode realistic dependencies — ownership clarity drives founder involvement probability via exponential decay; asset depth and literacy interact multiplicatively to determine repeat query rate; late scope lock (day > 14) applies a stochastic 1.3–1.5× multiplier to TTFV.

**Statistical audit:** Logistic regression (Audit 1), OLS with interaction term (Audit 2), and Pearson correlation (Audit 3) verify that model outputs match theoretical expectations before prescriptive analysis begins.

**Segmentation and simulation:** Clients are classified into four segments by literacy and ownership clarity. Counterfactual scenarios project the bandwidth and satisfaction impact of moving each lever to its recommended target.

---

### Repository Structure
```
documentation/
01_failure_taxonomy.md       — Categorization of observed failure modes
02_research_design.md        — Variable definitions, inference logic, hypotheses
notebooks/
01_data_engine.ipynb         — Generative model and dataset synthesis
02_statistical_audit.ipynb   — Inferential validation (Logit, OLS, Pearson r)
03_exploratory_analysis.ipynb — Segment classification and intervention sizing
04_strategic_brief.ipynb     — Prescriptive output with interactive simulator
data/
onboarding_data_v2.csv       — Version-controlled synthetic dataset
```
---

### Getting Started
```bash
git clone [URL]
pip install -r requirements.txt
```

Run `notebooks/01_data_engine.ipynb` first to generate the canonical dataset, then proceed through notebooks in order.
s