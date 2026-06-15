# Toughest Sports Analysis

A data analysis and machine learning project that explores and ranks sports by difficulty using multi-attribute scoring across physical and psychological skill categories.

## Overview

This notebook analyzes a dataset of sports rated across 10 attributes to determine which sports are objectively the most challenging. It combines exploratory data analysis, rich visualizations, and predictive modeling to uncover patterns in what makes a sport difficult.

## Dataset

**File:** `sample_data/toughestsport.csv`

Each sport is scored (0–10) across the following attributes:

| Category | Attributes |
|---|---|
| Physical | Endurance, Strength, Power, Speed, Agility, Flexibility, Durability, Hand-eye Coordination |
| Psychological | Nerve, Analytical Aptitude |

Additional columns: `SPORT`, `Total` (aggregate score), `Rank`

## Project Structure

```
Final.ipynb         # Main analysis notebook
sample_data/
  toughestsport.csv # Sports difficulty dataset
```

## Analysis & Visualizations

The notebook covers:

- **Top 5 Sports by Speed** — tabular ranking filtered by a single metric
- **Top 10 Comparison by Skills** — line chart comparing all 10 attributes across the hardest sports
- **Top 10 by Overall Rating** — bar chart of total difficulty scores
- **Strength, Speed & Flexibility Comparison** — grouped bar chart for the top 10 sports
- **Per-Metric Rankings** — full-dataset bar charts for Power, Speed, and Flexibility (via seaborn)
- **Attribute Correlation Matrix** — heatmap showing how skills correlate with each other
- **Physical vs. Psychological Averages** — grouped bar chart comparing mean physical and mental scores per sport

## Machine Learning

Two models are trained to predict a sport's `Total` difficulty score from its 10 skill attributes:

**Linear Regression**
- Features: all 10 skill attributes
- Metrics reported: MAE, MSE, R²
- Visualization: scatter plot with fitted line for Power vs. Total

**K-Nearest Neighbors Regressor (KNN)**
- Hyperparameter tuning via `GridSearchCV` over k = 1–10
- Cross-validated (5-fold) using R² scoring
- Outputs the best `k` and corresponding score

## Requirements

```
pandas
matplotlib
seaborn
scikit-learn
numpy
```

Install with:

```bash
pip install pandas matplotlib seaborn scikit-learn numpy
```

## Usage

1. Open `Final.ipynb` in Jupyter or [Google Colab](https://colab.research.google.com/)
2. Ensure `sample_data/toughestsport.csv` is in the working directory
3. Run all cells in order

## Key Findings

The notebook identifies the top 10 most demanding sports by total score and explores which physical and mental attributes contribute most to overall difficulty. The correlation matrix reveals relationships between skills, and the linear model quantifies how well individual attributes (such as Power) predict overall sport difficulty.
