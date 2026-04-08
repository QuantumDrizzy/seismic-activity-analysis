# Global Seismic Activity Analysis
## USGS + NOAA Real Data Edition

**Seismic data:** USGS Earthquake Catalog — M≥5.0 · 1900–2026  
**Tsunami data:** NOAA/NCEI Global Historical Tsunami Database  
**Tools:** Python · Pandas · NumPy · Matplotlib · Seaborn · Folium · Scikit-learn · SQLite

---

## Overview

Analysis of 106,358 real earthquakes (M≥5.0) from the USGS catalog, enriched with validated tsunami labels from the NOAA Global Historical Tsunami Database. Tsunami events were cross-referenced by geographic proximity (±0.5 degrees lat/lon) and temporal window (same year and month), filtered to validated events with confirmed seismic origin.

**Central questions:**
1. Where are the most seismically active zones on Earth?
2. Has global seismic activity changed over 1900–2026?
3. Can we predict tsunami generation from pre-event seismic parameters?
4. What does the prediction performance tell us about earthquake forecasting?

---

## Dataset

| Source | Description |
|--------|-------------|
| USGS Earthquake Catalog | 106,358 M≥5.0 earthquakes, 1900–2026 |
| NOAA/NCEI Tsunami Database | Validated tsunami events, seismic origin confirmed |

**Cross-reference methodology:** spatial match within ±0.5° lat/lon + same year/month window. Only tsunamis with validity ≥3 (definite event) and cause code 1 (seismic origin) were used.

---

## Key Findings

| Finding | Result |
|---------|--------|
| Gutenberg-Richter b-value | 0.93 (confirmed on real data) |
| Shallow tsunami rate (≤70km) | ~7% |
| Deep tsunami rate (>70km) | ~0.5% |
| Shallow/deep tsunami ratio | ×14 (p < 0.001) |
| Magnitude trend 1900–2026 | Not increasing (reflects improved detection) |
| Best model AUC (pre-event only) | 0.725 (Gradient Boosting) |

**Important methodological note on the ML results:** only pre-event features were used (depth, magnitude, measurement errors). Post-event features like felt reports or significance scores were deliberately excluded to avoid data leakage. AUC of 0.725 is the honest result — better than random but insufficient for reliable prediction.

---

## Structure

```
seismic-activity-analysis/
├── seismic_analysis_real.ipynb     — main analysis notebook
├── usgs_earthquakes_real.csv       — USGS catalog + NOAA tsunami labels
├── requirements.txt
└── outputs/
    ├── fig1_overview.png           — magnitude distribution + timeline
    ├── fig2_depth_tsunami.png      — depth analysis + regional tsunami counts
    ├── fig3_timeseries.png         — time series analysis
    ├── fig4_model_evaluation.png   — ML model comparison
    ├── map1_global_heatmap.html    — interactive global heatmap
    ├── map2_major_earthquakes.html — interactive M≥7.0 markers
    └── map3_tsunami_risk.html      — interactive tsunami risk map
```

---

## Setup

```bash
pip install pandas numpy matplotlib seaborn folium scikit-learn scipy jupyter
jupyter notebook seismic_analysis_real.ipynb
```

---

## Data Sources

- **USGS Earthquake Hazards Program:** https://earthquake.usgs.gov
- **NOAA/NCEI Global Historical Tsunami Database:** https://www.ngdc.noaa.gov

Both sources are public and freely available.

---

*Part of a series of data science explorations on public geophysical datasets.*  
*Previous: Quantum navigation and magnetic disruption in the Levant corridor.*
