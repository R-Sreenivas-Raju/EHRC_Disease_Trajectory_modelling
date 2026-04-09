# Delphi: Mental Health Trajectories Analysis

## Overview
This project analyzes mental health trajectories using time-series data and predictive modeling. It processes longitudinal signals, identifies anomalies, and evaluates how signal attenuation impacts anomaly detection.

The notebook explores:
- Signal visualization
- Statistical analysis of time-series data
- Anomaly detection behavior
- Effects of enforcement/attenuation on signals

---

## Project Structure

```
.
├── delphi_mental_health_trajectories.ipynb   # Main analysis notebook
├── results/
│   └── enforcer_outputs/                    # Processed signal outputs
├── data/                                    # Input datasets
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

If `requirements.txt` is not available, install manually:
```bash
pip install numpy pandas matplotlib seaborn jupyter
```

---

## Key Features

### 1. Signal Analysis
- Visualizes multiple input signals over time
- Computes:
  - Minimum and maximum values
  - Trends and variability

### 2. Enforcement Analysis
- Compares:
  - Original signals
  - Attenuated (enforced) signals
- Shows how signals are modified after anomaly thresholds

### 3. Anomaly Behavior
- Evaluates:
  - When anomalies occur
  - Whether attenuation prevents them

---

## Outputs

- Time-series plots for all signals
- Statistical summaries (min, max, distributions)
- Post-enforcement signal comparisons
- Anomaly prevention metrics

---

## Customization

You can modify:
- Number of signals analyzed
- Thresholds for anomaly detection
- Enforcement/attenuation rules
- Visualization styles

---

## Future Improvements

- Add synthetic data generation
- Integrate real-time anomaly detection
- Improve model evaluation metrics (Precision, Recall, F1)
- Deploy as a dashboard (Streamlit / Flask)

## 👤 Author
Kantheti Anish
