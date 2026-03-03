# Predicting Ridership at the Chicago Transit Authority’s ‘L’ Stations

## Contributors

* **Maria Benjamin** ([mariageb@umich.edu](mailto:mariageb@umich.edu))
* **Alexander Cao** ([azcao@umich.edu](mailto:azcao@umich.edu))
* **Frankie Pike** ([frankiep@umich.edu](mailto:frankiep@umich.edu))

---

## Project Overview

This project leverages supervised and unsupervised machine learning to 1) forecast daily ridership for the Chicago Transit Authority's 'L' train system by station and 2) identify latent station profiles. Using a dataset spanning from 2001 to 2026, we explore how spatial factors (zoning, line proximity), temporal shifts (the COVID-19 pandemic), and environmental variables (weather) influence urban mobility.

## Repository Structure

* `ridership.ipynb`: Full data processing, modeling, and visualization pipeline.
* `download_data.ipynb`: Script to download a fresh copy of ridership, system information, and zoning data.
* `weather_data_compilation.ipynb`: Script to vertically concatenate and perform basic cleaning on the various weather CSV files located in resources/weather.
* `Written Report.pdf`: Final comprehensive analysis and explanation.

---

## Getting Started

1. **Clone the repo:**
```bash
git clone https://github.com/azcao95/cta-ridership-w2026-mads-milestone-2.git

```


2. **Install dependencies:**
```bash
pip install pandas numpy scikit-learn matplotlib seaborn statsmodels geopandas

```


3. **Run the analysis:**
Run `ridership.ipynb` to reproduce the results.


4. **If you are having trouble with the source data, use the other notebooks to get new copies:**
Run `download_data.ipynb` and `weather_data_compilation.ipynb`.


---

## Technical Workflow

### 1. Supervised Learning (Forecasting)

We compared three model families to predict ridership volume:

* **Baseline:** Ordinary Least-Squares (OLS) Linear Regression
* **Robust:** Huber Regression, robust to ridership outliers during major city events like the Chicago Marathon
* **Tree-Based Models:** Decision Tree and Random Forest Regressors, which captured non-linear "cliffs" such as extreme winter temperatures and the pandemic shutdown
* **Result:** Our optimized Decision Tree achieved an **$R^2$ of 0.847**, successfully identifying "Downtown Core" proximity as the most significant predictor.

### 2. Unsupervised Learning (Clustering & Dimensionality Reduction)

* **PCA:** Reduced 100+ high-dimensional zoning and spatial features into **3 Principal Components** that retained nearly 85% of predictive power.
* **K-Means:** Grouped stations into 3-5 distinct clusters (e.g., "High-Traffic Downtown Hubs," "Residential Local Stops," etc.).

---

## Key Findings

* **The Root Split:** The primary driver of ridership is a binary boundary: is the station within a mile of the **Downtown Core**?
* **The Post-Pandemic Shift:** Pre-2020 ridership patterns have not fully returned.

---
