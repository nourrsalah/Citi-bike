# 🚲 CitiBike NYC — Big Data Demand & Utilisation Pipeline

End-to-end data engineering and analytics project processing **1.3M+ Citi Bike trip records** using PySpark. Covers demand forecasting, station capacity analysis, asset maintenance scheduling, and user segmentation — with a 97% reduction in query response time and an interactive dashboard for real-time exploration.

---

## Overview

This project simulates a production-grade data pipeline for a bike-share operator. Given raw trip data, the goal is to answer operational questions: *When is demand highest? Which stations are overloaded? Which bikes need maintenance? Who are our riders?*

The pipeline runs entirely in PySpark for scalable distributed processing, with a Dash-based dashboard as the analytics layer.

---

## Features

- **ETL Pipeline** — Ingests, cleans, and validates raw CSV trip data; handles nulls, type coercion, and schema inconsistencies
- **Demand Forecasting** — Models hourly and seasonal ride volume to identify peak demand windows
- **Station Utilisation Analysis** — Ranks stations by trip volume; flags overutilised stations using mean + 2σ thresholds
- **Maintenance Scheduling** — Identifies bikes exceeding usage thresholds as candidates for inspection
- **User Segmentation** — Clusters riders by behaviour (trip duration, frequency, geography) distinguishing subscribers vs. casual customers
- **Interactive Dashboard** — Dash app with real-time filtering by date range, user type, and station
- **Data Quality Checks** — Automated anomaly detection and validation at each pipeline stage

---

## Tech Stack

| Layer | Tools |
|---|---|
| Distributed Processing | PySpark |
| Data Manipulation | Pandas, NumPy |
| Machine Learning | scikit-learn (clustering, classification) |
| Visualisation | Plotly Dash, Matplotlib, Seaborn |
| Storage | Parquet (intermediate), CSV (raw) |
| Environment | Python 3.10+, Jupyter Notebook |

---

## Project Structure

```
citibike-pipeline/
├── data/
│   ├── raw/                  # Raw CSV trip data
│   └── processed/            # Cleaned Parquet outputs
├── notebooks/
│   ├── 01_etl_pipeline.ipynb
│   ├── 02_demand_analysis.ipynb
│   ├── 03_station_utilisation.ipynb
│   ├── 04_user_segmentation.ipynb
│   └── 05_maintenance_flags.ipynb
├── dashboard/
│   └── app.py                # Dash interactive dashboard
├── src/
│   ├── pipeline.py           # PySpark ETL logic
│   ├── features.py           # Feature engineering
│   └── quality_checks.py     # Validation & anomaly detection
├── requirements.txt
└── README.md
```

---

## Key Results

| Metric | Result |
|---|---|
| Records processed | 1.3M+ trips |
| Query response time | 30s → <1s (97% reduction) |
| User segmentation accuracy | 61% |
| Peak demand window identified | 8–9 AM & 5–6 PM weekdays |
| High-utilisation stations flagged | Top 15 by mean + 2σ threshold |

---

## Getting Started

```bash
# Clone the repo
git clone https://github.com/nourrsalah/citibike-pipeline.git
cd citibike-pipeline

# Install dependencies
pip install -r requirements.txt

# Run the ETL pipeline
python src/pipeline.py

# Launch the dashboard
python dashboard/app.py
```

> **Data source:** [Citi Bike System Data](https://citibikenyc.com/system-data) — publicly available trip history files.

---

## Skills Demonstrated

- Large-scale distributed data processing with PySpark
- ETL pipeline design and data quality engineering
- Unsupervised learning and clustering (user segmentation)
- Feature engineering for demand forecasting
- Interactive data visualisation with Plotly Dash
- Analytical problem-solving on real-world operational data
