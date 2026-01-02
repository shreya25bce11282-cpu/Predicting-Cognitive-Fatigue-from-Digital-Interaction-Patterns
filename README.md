#  Predicting Cognitive Fatigue from Digital Interaction Behavior

## Project Description
This project models **cognitive fatigue** as a measurable outcome of digital interaction behavior. Grounded in cognitive psychology and cognitive load theory, it demonstrates how sustained attention, task switching, and interface-driven stimulation contribute to mental exhaustion during prolonged digital sessions.

Using synthetic but psychologically grounded interaction data, the project translates abstract cognitive concepts—such as attentional depletion and extraneous cognitive load into quantifiable behavioral features. A regression based machine learning model is then used to predict user fatigue levels, allowing interpretability of how specific interaction patterns influence cognitive state.

The project bridges **psychology, behavior analysis, and machine learning**, highlighting how interface design choices can be evaluated through measurable cognitive outcomes rather than engagement metrics alone.

---

## Cognitive Motivation
Human attention and working memory are limited resources. Interfaces that demand sustained attention, frequent task switching, or high interaction density can overload these systems, leading to cognitive fatigue.

This project focuses on:
- Attentional fatigue from prolonged sessions  
- Extraneous cognitive load introduced by interface features  
- Behavioral signals of mental exhaustion  

Understanding these relationships enables more cognitively responsible interface design.

---

## Problem Formulation
- **Task:** Regression  
- **Goal:** Predict cognitive fatigue score from interaction behavior  

The model estimates how mentally fatigued a user becomes during a digital session based on observable interaction features.

---

## Dataset
A synthetic dataset was generated to reflect realistic interaction patterns inspired by social media and content-consumption platforms.

### Features
- `session_duration` — Length of the session (minutes)  
- `scroll_events` — Number of scrolling actions  
- `interaction_density` — Actions per minute  
- `late_night` — Binary indicator of late-night usage  
- `notifications` — Notification exposure count  
- `task_switches` — Number of task/context switches  

### Target Variable
- `fatigue_score` — Continuous cognitive fatigue score (0–10)

Synthetic data was used to maintain privacy while preserving theoretical validity.

---

## Exploratory Data Analysis
Exploratory analysis revealed:
- Higher interaction density and task switching correlate with increased fatigue  
- Late night usage significantly elevates fatigue scores  
- Notification exposure contributes to extraneous cognitive load  

These findings align with cognitive load theory and attentional resource limitations.

---

## Machine Learning Model

### Model Choice
**Linear Regression** was selected to prioritize interpretability over black box accuracy.  
This allows direct cognitive interpretation of how each behavioral feature contributes to fatigue.

### Evaluation Metrics
- **R² Score**
- **Mean Squared Error (MSE)**

---

## Results & Interpretation
The model achieved strong explanatory performance:

- **R² ≈ 0.93**
- **Low MSE**, indicating stable predictions

### Key Insights
- **Late-night usage** is the strongest predictor of fatigue  
- **Interaction density** significantly increases cognitive exhaustion  
- **Task switching** and notifications add extraneous cognitive load  

These results support cognitive load theory: fatigue emerges from sustained attention without recovery.

---

## Why This Matters
This project demonstrates how:
- Cognitive psychology can inform feature engineering  
- Behavioral data can serve as a proxy for internal mental states  
- Machine learning can be used as an explanatory tool, not just a predictor  

It provides a framework for evaluating digital systems based on **cognitive cost**, not engagement alone.

---

## Tech Stack
- Python  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- Scikit-learn  

---

## Future Extensions
- Replace synthetic data with real interaction logs (with consent)  
- Compare multiple model types for robustness  
- Integrate real time fatigue prediction into interface prototypes

---

## Methodological Note on Synthetic Data

Because the dataset is synthetically generated using psychologically motivated assumptions, the model’s performance reflects internal consistency rather than real world generalization. The goal of this project is not predictive deployment, but to demonstrate how cognitive theory can be operationalized into behavioral features and interpreted through an explanatory model.

