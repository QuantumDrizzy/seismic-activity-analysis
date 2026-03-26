# 🌍 Global Seismic Activity Analysis
## IBM Data Science Professional Certificate — Capstone Project

[![Python](https://img.shields.io/badge/Python-3.10-blue)](https://python.org)
[![IBM](https://img.shields.io/badge/IBM-Data%20Science-054ADA)](https://www.ibm.com)
[![Folium](https://img.shields.io/badge/Folium-Maps-green)](https://python-visualization.github.io/folium/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

---

## Overview

Analysis of 10,500+ significant earthquakes (M≥5.0) from 1900 to 2024 using the USGS Earthquake Catalog. Covers geospatial visualization, time series analysis, statistical hypothesis testing, SQL queries, and machine learning classification.

**Central question:** *Can we predict earthquake magnitude class from observable seismic parameters — and which zones face the highest tsunami risk?*

---

## Dataset

**Source:** U.S. Geological Survey — Earthquake Hazards Program  
**URL:** https://earthquake.usgs.gov/earthquakes/search/  
**Coverage:** Global M≥5.0 earthquakes, 1900–2024

| Statistic | Value |
|-----------|-------|
| Total earthquakes | 10,506 |
| Period | 1900–2024 |
| M≥7.0 (Major) | 116 |
| M≥8.0 (Great) | 8 |
| Tsunami events | 143 |
| Seismic zones | 18 |

---

## Structure

```
seismic-activity-analysis/
│
├── seismic_analysis.ipynb          # Main analysis notebook
├── usgs_earthquakes.csv            # Dataset
├── README.md
└── outputs/
    ├── fig1_overview.png
    ├── fig2_depth_alert_tsunami.png
    ├── fig3_timeseries.png
    ├── fig4_model_evaluation.png
    ├── map1_global_heatmap.html     # Interactive heatmap
    ├── map2_major_earthquakes.html  # Interactive M≥7.0 markers
    └── map3_tsunami_risk.html       # Interactive tsunami zones
```

---

## Key Results

| Finding | Result |
|---------|--------|
| Gutenberg-Richter b-value | ~1.0 (confirmed) |
| Tsunami rate — shallow (<70km) | 1.3% |
| Tsunami rate — deep (>70km) | 0.4% |
| Depth/tsunami relationship | p < 0.001 (significant) |
| Magnitude trend (1900–2024) | Not significant (p > 0.05) |
| Best classifier AUC | >0.99 (Gradient Boosting) |

---

## Techniques Applied

- **Data Wrangling:** pandas, datetime parsing, missing value handling
- **SQL Analysis:** SQLite queries for aggregation and filtering
- **EDA:** Gutenberg-Richter law, magnitude distributions, temporal trends
- **Geospatial:** Folium interactive maps (HeatMap, MarkerCluster, CircleMarker)
- **Statistics:** Chi-square test, point-biserial correlation, linear trend analysis
- **ML:** Logistic Regression, Random Forest, Gradient Boosting with ROC/AUC

---

## Setup

```bash
pip install pandas numpy matplotlib seaborn folium scikit-learn scipy jupyter
jupyter notebook seismic_analysis.ipynb
```

---

## References

- USGS Earthquake Hazards Program: https://earthquake.usgs.gov
- Gutenberg & Richter (1944). Frequency of earthquakes in California. *BSSA*, 34(4), 185–188
- NOAA National Centers for Environmental Information: https://www.ngdc.noaa.gov

---

*Part of the IBM Data Science Professional Certificate portfolio*
