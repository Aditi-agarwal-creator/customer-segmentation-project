# Customer Segmentation Project

Segmenting customers based on **behavior and demographics** using K-Means clustering — built as part of a customer analytics internship task.

## Overview

This project analyzes customer data (age, income, spending behavior, purchase frequency, recency, and category preference) and groups customers into distinct, actionable segments using unsupervised machine learning. The goal: turn raw customer data into a story a marketing or business team can act on.

## What's Inside

| File | Description |
|---|---|
| `Customer_Segmentation_Analysis.ipynb` | Full analysis notebook — EDA, feature scaling, cluster selection (Elbow + Silhouette), K-Means clustering, PCA visualization, segment profiling and naming |
| `customer_data.csv` | Raw input dataset (515 customers) |
| `customer_segments_output.csv` | Output dataset with each customer's assigned segment |
| `plots/` | All charts generated during the analysis |

## Methodology

1. **Exploratory Data Analysis** — distributions, correlations, and initial scatter plots to understand the data
2. **Feature Scaling** — standardized Age, Income, Spending Score, Purchase Frequency, and Recency using `StandardScaler` (required since K-Means is distance-based)
3. **Optimal Cluster Selection** — used both the **Elbow Method** (inertia) and **Silhouette Score** to choose the right number of segments objectively, instead of guessing
4. **K-Means Clustering** — fit the final model and assigned each customer to a segment
5. **Visualization** — PCA-based 2D projection to visualize clusters, plus direct feature scatter plots and bar charts of segment characteristics
6. **Segment Profiling & Naming** — translated cluster averages into business-friendly segment names (e.g. "Premium Loyalists", "Price-Sensitive / At Risk")

## Segments Identified

| Segment | Characteristics |
|---|---|
| **Premium Loyalists** | High income, high spending, frequent, recent purchases |
| **Affluent Disengaged** | High income, low spending, long time since last purchase |
| **Budget Enthusiasts** | Lower income, high spending score, frequent buyers |
| **Price-Sensitive / At Risk** | Low income, low frequency, high recency (inactive) |
| **Steady Regulars** | Moderate across all metrics |

*(Exact composition may vary slightly if the notebook is re-run, since K-Means has some randomness controlled via a fixed seed for reproducibility.)*

## Tools & Libraries

- Python — `pandas`, `numpy`
- `scikit-learn` — `StandardScaler`, `KMeans`, `PCA`, `silhouette_score`
- `matplotlib`, `seaborn` — visualization

## How to Run

```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
jupyter notebook Customer_Segmentation_Analysis.ipynb
```

Run all cells top to bottom. To use your own data, replace `customer_data.csv` with your dataset (keep the same column structure) and re-run.

## Key Learnings

- Applying unsupervised learning (K-Means) to real-world business problems
- Choosing the right number of clusters using statistical validation (Elbow + Silhouette), not guesswork
- Communicating technical clustering results as business-relevant customer segments
- End-to-end customer analytics workflow: data → model → insight → recommendation

---
*Built as part of the "Customer Segmentation Project" internship task.*
