#  Predicting Cognitive Fatigue from Digital Interaction Behavior

## Project Description
This project models **cognitive fatigue** as a measurable outcome of digital interaction behavior. Grounded in cognitive psychology and cognitive load theory, it demonstrates how sustained attention, task switching, and interface-driven stimulation contribute to mental exhaustion during prolonged digital sessions.

Using interaction-level behavioral data, the project translates abstract cognitive concepts — such as attentional depletion and extraneous cognitive load — into quantifiable behavioral features, then uses regression models to predict and interpret fatigue-related outcomes.

---

## Data Sources

This project uses **two datasets**, and it's important to be explicit about what each one is and isn't:

1. **Synthetic (self-generated)** — `data/raw/synthetic_fatigue_sessions.csv`. Built from explicit psychological assumptions (session duration, scroll events, interaction density, late-night usage, notifications, task switches → fatigue score). Used to test whether cognitive load theory could be operationalized into behavioral features and produce an interpretable model at all.

2. **Independently simulated (external)** — `data/raw/external_simulated_mobile_usage.csv`, sourced from the [Mobile Device Usage and User Behavior Dataset](https://www.kaggle.com/datasets/valakhorasani/mobile-device-usage-and-user-behavior-dataset) (Kaggle, 700 samples). This dataset is **also simulated** — its own documentation states it was generated from simulated user behavior — but it was built independently, with different assumptions and no fatigue label in mind. Used in `03_external_validation.ipynb` as a cross-check on whether the feature-selection *logic* transfers to a differently-constructed dataset, not as real-world validation.

**Neither dataset reflects real-world passive-sensing data.** That remains the central limitation of this project. Genuine validation requires real behavioral data collected under proper research ethics oversight (e.g. IRB approval) — noted throughout as future work, and the natural next step for this project within a supervised research setting.

---

## Cognitive Motivation
Human attention and working memory are limited resources. Interfaces that demand sustained attention, frequent task switching, or high interaction density can overload these systems, leading to cognitive fatigue.

This project focuses on:
- Attentional fatigue from prolonged sessions  
- Extraneous cognitive load introduced by interface features  
- Behavioral signals of mental exhaustion  

---

## Notebooks

| Notebook | Purpose |
|---|---|
| `01_data_generation.ipynb` | Generates the synthetic fatigue dataset from psychologically-motivated assumptions |
| `02_eda_ml_cognitive_fatigue.ipynb` | EDA and linear regression on the synthetic dataset (R² ≈ 0.93) |
| `03_external_validation.ipynb` | Cross-checks the feature-selection logic against the independent simulated dataset, with an honest accounting of where results agree, diverge, and what a suspiciously high R² actually implies |

---

## Problem Formulation
- **Task:** Regression  
- **Goal:** Predict cognitive fatigue / engagement-intensity outcomes from interaction behavior  

---

## Key Findings Across Both Datasets

**Synthetic dataset (Notebook 02):**
- Late-night usage and interaction density were the strongest predictors of fatigue (R² ≈ 0.93)

**External dataset (Notebook 03):**
- Number of Apps Installed (a task-switching proxy) and Battery Drain were the strongest predictors of behavioral intensity
- Model fit was extremely high (R² ≈ 0.98) — flagged in the notebook as likely evidence of a near-deterministic synthetic label, not a validated real-world relationship
- The *divergence* in which feature dominates across the two datasets is treated as a genuine, informative result — it shows single-dataset findings can be an artifact of that dataset's specific generation assumptions

---

## Why This Matters
This project demonstrates how:
- Cognitive psychology can inform feature engineering  
- Behavioral data can serve as a proxy for internal mental states, with clearly stated limits on what that proxy can support  
- Machine learning can be used as an explanatory tool, not just a predictor — including using unexpectedly clean results as a diagnostic signal rather than a success metric

---

## Tech Stack
- Python  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- Scikit-learn  

---

## Future Extensions
- Replace both synthetic and independently-simulated data with real interaction logs, collected with informed consent and ideally IRB oversight
- Extend the feature set to include notification exposure and late-night usage in a real dataset, since neither was testable in the external dataset used here
- Integrate real-time fatigue prediction into interface prototypes (see the companion project, *Designing Cognitive-Load-Aware Interfaces*)

---

## Methodological Note

Because both datasets used here are synthetic, model performance in this project reflects internal consistency and cross-simulator agreement/divergence rather than real-world generalization. The goal is not predictive deployment, but to demonstrate how cognitive theory can be operationalized into behavioral features, tested for robustness across independently-constructed data, and interpreted honestly — including reporting a result (the 0.98 R²) that looks good on the surface but should not be taken at face value.
