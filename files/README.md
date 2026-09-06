# 🌾 Seasonal Agriculture Performance Analysis

**VOIS AICTE Batch 1, 2026-2027 — Major Project**

A data analytics project investigating how agricultural performance
(yield, resource usage, and economic outcomes) varies across the three
Indian cropping seasons — **Kharif, Rabi and Zaid** — using exploratory
data analysis, statistical testing and visualization in Python.

---

## 📌 Problem Statement

Agricultural activities are influenced by seasonal variations in
environmental conditions, farming practices, resource availability and
market conditions. This project analyzes a seasonal agriculture dataset
to identify meaningful patterns, trends, relationships and variations in
agricultural performance across seasons, regions and crops — supporting
evidence-based agricultural planning.

The full original problem brief is available in [`docs/Problem_Statement.pdf`](docs/Problem_Statement.pdf).

## 🎯 Objective

- Explore and understand seasonal agricultural data
- Clean and prepare the data for analysis
- Examine how performance (yield, production, profit) varies across seasons
- Identify seasonal patterns, trends and relationships
- Compare regions, crops and irrigation methods within each season
- Apply statistical tests to validate observed differences
- Derive evidence-based insights and recommendations

## 🗂️ Repository Structure

```
├── data/
│   ├── generate_dataset.py                 # Script that generates the dataset
│   └── agriculture_seasonal_data.csv       # 3,000-record seasonal agriculture dataset
├── notebooks/
│   └── Seasonal_Agriculture_Performance_Analysis.ipynb   # Full analysis notebook
├── images/                                 # Exported charts (referenced by README & reports)
├── reports/
│   └── Key_Insights_and_Recommendations.md
├── docs/
│   └── Problem_Statement.pdf               # Original project brief
├── requirements.txt
└── README.md
```

## 📊 About the Dataset

Since no dataset was supplied with the project brief, a **synthetic but
realistic dataset** (`data/agriculture_seasonal_data.csv`, 3,000 records,
2019–2025) was generated using domain-informed rules — seasonal rainfall
and temperature profiles, crop-specific yield/price baselines, and
resource-cost relationships — so that seasonal patterns in the data are
representative of real agricultural behaviour. The generation logic is
fully transparent in [`data/generate_dataset.py`](data/generate_dataset.py).
If you have a real dataset, drop it into `data/` with the same column
names and the notebook will run unchanged.

**Columns include:** `Year`, `Season`, `Region`, `Crop_Type`, `Soil_Type`,
`Irrigation_Type`, `Area_Hectares`, `Rainfall_mm`, `Temperature_C`,
`Humidity_percent`, `Fertilizer_Used_kg`, `Pesticide_Used_kg`,
`Water_Usage_Liters`, `Labor_Hours`, `Yield_kg_per_hectare`,
`Production_kg`, `Market_Price_per_kg`, `Revenue_INR`,
`Cost_of_Cultivation_INR`, `Profit_INR`.

## 🔍 Analysis Workflow

The notebook (`notebooks/Seasonal_Agriculture_Performance_Analysis.ipynb`) follows this structure:

1. Introduction & Problem Statement
2. Data Loading
3. Data Cleaning & Preparation (missing values, duplicates, inconsistent text, feature engineering)
4. Exploratory Data Analysis — Univariate distributions
5. Seasonal Comparison — Bivariate analysis (boxplots, seasonal summary table)
6. Relationships & Correlations — Multivariate analysis (correlation heatmap, scatter plots)
7. Statistical Testing — One-way ANOVA & Pearson correlation
8. Regional & Crop-level Deep Dive — heatmaps, top crop–season combinations, irrigation efficiency, yearly trends
9. Key Insights
10. Recommendations
11. Conclusion

## 📈 Sample Visualizations

| Seasonal Yield Distribution | Region × Season Profit Heatmap |
|---|---|
| ![Seasonal boxplots](images/03_seasonal_boxplots.png) | ![Region season heatmap](images/07_region_season_heatmap.png) |

| Correlation Matrix | Yearly Yield Trend |
|---|---|
| ![Correlation heatmap](images/05_correlation_heatmap.png) | ![Yearly trend](images/10_yearly_trend.png) |

## 🧠 Headline Findings

- **Kharif** shows the highest yields and production volumes (monsoon-supported crops).
- **Rabi** shows the strongest profit margins due to lower irrigation dependence.
- **Zaid** has the lowest yield and highest cost-per-hectare, driven by irrigation dependence in hot, dry conditions.
- Seasonal differences in yield and profit-per-hectare are **statistically significant** (ANOVA, p < 0.05).
- **Drip/sprinkler irrigation** consistently shows higher water-use efficiency than canal/borewell across seasons.

Full findings and recommendations: [`reports/Key_Insights_and_Recommendations.md`](reports/Key_Insights_and_Recommendations.md)

## 🚀 How to Run

```bash
# 1. Clone the repository
git clone <your-repo-url>.git
cd seasonal-agriculture-performance-analysis

# 2. Create a virtual environment (recommended)
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. (Optional) Regenerate the dataset
cd data && python generate_dataset.py && cd ..

# 5. Launch Jupyter and open the notebook
jupyter notebook notebooks/Seasonal_Agriculture_Performance_Analysis.ipynb
```

## 🛠️ Tech Stack

`Python` · `pandas` · `numpy` · `matplotlib` · `seaborn` · `scipy` · `Jupyter Notebook`

## 📄 License

This project is released under the [MIT License](LICENSE).

---
*Submitted as part of the VOIS AICTE Batch 1, 2026-2027 Data Analytics program.*
