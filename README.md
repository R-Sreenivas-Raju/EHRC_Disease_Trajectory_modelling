# Delphi: Mental Health Trajectories Analysis

## Overview
Delphi-2M is a GPT-2-based transformer trained on 400K patient health trajectories from the UK Biobank. It models sequences of ICD-10 coded diagnoses over a patient's lifetime, alongside demographic and lifestyle factors, to forecast future disease events and simulate complete health trajectories across more than 1,000 conditions.

This notebook applies Delphi-2M specifically to mental health (ICD-10 Chapter V), conditioning on each patient's history up to age 60 and generating synthetic future trajectories up to age 80. It produces a suite of visualisations to explore the timing, frequency, and co-occurrence of mental health conditions in the generated population

---

## Project Structure

```
├── delphi_mental_health_trajectories.ipynb   # Main analysis notebook
├── delphi_simulations.ipynb                  # Delphi Simulation notebook
├── results/                                  # Plots and Results
├── data/                                     # Input datasets
├── requirements.txt    
└── README.md
```

---

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/R-Sreenivas-Raju/EHRC_Disease_Trajectory_modelling.git
cd EHRC_Disease_trajectory_modelling
```

### 2. Install Dependencies
It is recommended to use a virtual environment.

```bash
pip install -r requirements.txt
```
---

## Key Parameters

| Parameter | Default | Description |
| :--- | :--- | :--- |
| `age` | `60` | **Conditioning age** — history up to this age is used as the input prompt. |
| `N_PATIENTS` | `500` | Number of patients to generate synthetic trajectories for. |
| `MAX_TOKENS` | `50` | Maximum number of new disease events to generate per patient. |
| `max_age` | `80 × 365.25` | Maximum age (in days) for the generated trajectory. |
| `no_repeat` | `True` | Prevents the exact same disease token from appearing twice in a patient's future timeline. |

---

## Model Details

| Property | Specification |
| :--- | :--- |
| **Architecture** | Modified GPT-2 (nanoGPT base) |
| **Parameters** | ~2.24M |
| **Layers / Heads** | 12 / 12 |
| **Vocabulary** | 1,270 tokens (ICD-10 diagnoses, sex, BMI, lifestyle, death) |
| **Training Data** | UK Biobank (~400K patients) |
| **Validation** | Danish national registries (~1.9M individuals) |
| **Input Format** | Sequences of `(age_in_days, token)` pairs |
| **Output** | Predicted `(age, token)` pairs for future health events |

---

## Outputs
All plots are saved to the results/ directory.
A summary is printed at the end of the notebook, including:

- Total patients generated
- Total events and mental health event count
- Number of unique MH conditions observed
- List of saved plot filenames
