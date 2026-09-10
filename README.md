# Bike-Sharing Demand Analysis & Forecasting

A research-style, end-to-end analysis of the UCI Bike Sharing dataset
(17,379 hourly records, 2011–2012): from behavioral EDA to an
operational forecasting pipeline with business recommendations.

## What's inside

1. **Data understanding** — quality checks (missing, duplicates, invalid hours).
2. **Hypothesis-driven EDA** — commuting vs leisure behavior of registered vs casual users.
3. **Forecasting with honest evaluation** — chronological split; baselines → linear → tree → random forest.
4. **Temporal feature experiment** — adding yr/mnth recovers the growth trend (R² 0.70 → 0.87).
5. **Mini-research** — which user type is easier to predict? (WAPE-based fair comparison, per-target importance, research memo).
6. **Operational reliability** — peak-hour shortage risk, safety buffers, business recommendations.

## Key findings

- Demand grew strongly from 2011 to 2012; a random split hides this and inflates performance.
- Registered users commute (peaks at 8 and 17–18); casual users ride for leisure (midday, weekends, weather-sensitive).
- Casual demand is the hardest to predict (WAPE 0.315 vs 0.213 for total demand).
- Even with R² ≈ 0.87, the model under-predicts the evening peak on ~82% of test days; hour-specific safety buffers (e.g., +195 bikes at 5 PM) turn predictions into reliable dispatch decisions.

## How to run

    python -m venv venv
    venv\Scripts\activate
    pip install -r requirements.txt
    jupyter lab

## Repository structure

- `bike_sharing_project.ipynb` — the full analysis
- `data/hour.csv` — hourly bike-sharing data (UCI)
- `requirements.txt` — Python dependencies

## Data source

Fanaee-T, H. & Gama, J. (2013). Bike Sharing Dataset.
UCI Machine Learning Repository.