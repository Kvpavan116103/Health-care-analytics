# Healthcare Analytics — Doctor Visit Utilisation Study
**Author:** KV Pavan Kumar  
**Dataset:** Healthcare Analytics for Doctor Visits (5,190 patients, 13 variables)  
**Status:** Complete · Portfolio-Ready · Reproducible

---

## Project Overview

This project delivers a full-lifecycle, professional data analytics study on a real-world healthcare dataset tracking GP (doctor) visit frequency across a population cohort. The analysis answers: *who visits, how often, and why?*

Key outcomes:
- 5 statistically-supported insights on visit drivers
- 6 actionable healthcare recommendations
- 14 professional visualisations saved to `figures/`
- A cleaned, feature-enriched dataset ready for modelling

---

## Dataset Description

| Column | Description |
|---|---|
| `visits` | Doctor visits in the past 2 weeks (target, 0–9) |
| `gender` | Patient biological sex (male/female) |
| `age` | Age scaled by 100 (×100 = approximate years, range 19–72) |
| `income` | Annual household income (scaled, 0–1.5) |
| `illness` | Number of illnesses/conditions in past 2 weeks (0–5) |
| `reduced` | Reduced activity days due to illness (0–14) |
| `health` | Self-reported health score — higher = worse (0–12) |
| `private` | Privately insured (yes/no) |
| `freepoor` | Low-income government health card (yes/no) |
| `freerepat` | Repatriation/veteran health card (yes/no) |
| `nchronic` | Non-limiting chronic condition (yes/no) |
| `lchronic` | Limiting chronic condition (yes/no) |

**Source:** Australian Health Survey microdata (Cameron & Trivedi, 1986) — widely used in econometrics / healthcare analytics literature.

---

## Key Findings

| Finding | Evidence |
|---|---|
| **79.8% zero-visit rate** — severe zero-inflation | 4,141 / 5,190 patients had 0 visits |
| **Illness count is the #1 visit predictor** | Spearman ρ ≈ 0.22, p < 0.001 |
| **Females visit significantly more** | Mann-Whitney p < 0.05 |
| **Limiting chronic conditions double visit rate** | 2–3× higher mean visits |
| **Insurance type significantly predicts access** | Chi-square p < 0.001 |
| **Top 3.5% (high-utilisers) drive ~20% of total visits** | Concentration analysis |

---

## Project Structure

```
├── Healthcare Analytics for Doctor Visits.csv   # Raw data
├── KVPavanKumar_HealthcareAnalytics.ipynb       # Main analysis notebook
├── KVPavanKumar_HealthcareAnalytics_ProjectReport.docx  # Full written report
├── requirements.txt                             # Python dependencies
├── README.md                                    # This file
├── healthcare_cleaned.csv                       # Cleaned + engineered dataset (generated)
└── figures/                                     # All 14 chart outputs (generated)
    ├── 01_visits_distribution.png
    ├── 02_continuous_distributions.png
    ├── 03_categorical_distributions.png
    ├── 04_visits_by_gender.png
    ├── 05_visits_by_age_band.png
    ├── 06_visits_by_insurance.png
    ├── 07_visits_vs_health_indicators.png
    ├── 08_visits_by_income.png
    ├── 09_chronic_conditions.png
    ├── 10_correlation_heatmap.png
    ├── 11_gender_insurance_visits.png
    ├── 12_spearman_correlations.png
    ├── 13_kpi_visit_rate.png
    └── 14_summary_dashboard.png
```

---

## How to Run

### 1. Clone the repository
```bash
git clone https://github.com/your-username/healthcare-analytics-doctor-visits.git
cd healthcare-analytics-doctor-visits
```

### 2. Set up Python environment
```bash
# Create virtual environment (recommended)
python -m venv venv
venv\Scripts\activate          # Windows
# source venv/bin/activate     # macOS/Linux

# Install dependencies
pip install -r requirements.txt
```

### 3. Launch Jupyter and run the notebook
```bash
jupyter lab
# Open KVPavanKumar_HealthcareAnalytics.ipynb
# Run All Cells (Kernel → Restart & Run All)
```

The notebook is self-contained — it reads the CSV from the same directory, performs all analysis, generates figures, and exports the cleaned dataset.

---

## Analysis Phases

| Phase | Description |
|---|---|
| **1 — Data Audit** | Schema review, missing values, duplicates, range checks, mutual exclusivity validation |
| **2 — Data Cleaning** | Binary encoding, age recovery, income flag, type conversions |
| **3 — Feature Engineering** | Visit flag, high-utiliser flag, insurance category, chronic burden, illness severity index, age band, income quartile |
| **4 — EDA** | 11 targeted visualisations covering distributions, cross-tabs, trends |
| **5 — Statistical Analysis** | Mann-Whitney U, Kruskal-Wallis, Spearman correlation, Chi-square, OLS proxy regression |
| **6 — Healthcare Insights** | 5 evidence-based insights with KPI benchmarks |
| **7 — Recommendations** | 6 actionable, data-supported recommendations |
| **8 — Summary** | Dashboard visualisation, cleaned data export |

---

## Technologies Used

- **Python 3.11+**
- **pandas** — data manipulation and aggregation
- **NumPy** — numerical operations
- **Matplotlib / Seaborn** — visualisation (14 charts)
- **SciPy** — statistical tests (Mann-Whitney U, Kruskal-Wallis, Chi-square, Spearman)
- **statsmodels** — OLS regression (optional, gracefully skipped if unavailable)
- **Jupyter Lab** — interactive notebook environment

---

## Author

**KV Pavan Kumar**  
 Data Analyst | Healthcare Analytics  
[LinkedIn](#) · [GitHub](#)

---

## License

This project is released for portfolio and educational purposes.  

