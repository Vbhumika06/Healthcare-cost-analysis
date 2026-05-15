#  Healthcare Cost Analysis

An end-to-end data analysis and predictive modelling project examining the factors that drive medical insurance charges. Using a real-world insurance dataset, the project applies exploratory data analysis, statistical correlation, patient segmentation, and a linear regression model to quantify the impact of lifestyle and demographic factors on healthcare expenditure — complemented by an interactive Power BI dashboard.

---

##  Project Structure

```
Healthcare_cost_analysis/
│
├── data/
│   ├── insurance.csv               # Raw dataset
│   └── insurance_cleaned.csv       # Cleaned and feature-engineered dataset
│
├── notebooks/
│   └── Healthcare_cost_analysis.ipynb  # Python analysis and ML notebook
│
├── dashboard/
│   └── healthcare_project.pbix     # Power BI dashboard
│
├── insights/
│   └── insights.md                 # Key findings and recommendations
│
└── README.md
```

---

##  Objectives

- Understand the distribution and skewness of medical insurance charges
- Quantify the impact of smoking on healthcare costs
- Analyse how BMI, age, and their interaction with smoking affect expenditure
- Segment patients by cost risk using data-driven thresholds
- Build and evaluate a regression model to predict medical charges
- Identify the most influential features driving healthcare costs

---

##  Dataset

**Source:** Medical Insurance Cost Dataset  
**Format:** CSV  
**Records:** 1,338 individuals  

**Features:**

| Column | Type | Description |
|---|---|---|
| age | Numeric | Age of the insured individual |
| sex | Categorical | Gender (male / female) |
| bmi | Numeric | Body Mass Index |
| children | Numeric | Number of dependents covered |
| smoker | Categorical | Smoking status (yes / no) |
| region | Categorical | Geographic region (northeast, northwest, southeast, southwest) |
| charges | Numeric | Annual medical insurance charges (target variable) |

---

##  Python Analysis — `Healthcare_cost_analysis.ipynb`

The notebook is structured in four phases:

### Phase 1 — Data Preparation
- Loading and inspecting the dataset
- Checking for nulls, duplicates, and data types
- Feature engineering: age groups (young / adult / middle-aged / senior) and BMI categories (underweight / normal / overweight / obese)

### Phase 2 — Exploratory Data Analysis
- Distribution of medical charges (histogram + KDE)
- Smoking status vs. charges (boxplot + group means)
- BMI vs. charges coloured by smoking status (scatter plot)
- Correlation matrix for numeric variables (age, BMI, children, charges)
- Regional average charges comparison
- Age group × smoking interaction analysis
- BMI category × smoking interaction analysis

### Phase 3 — Patient Segmentation
- Binary classification of patients as "high-cost" (above median charges)
- High-cost rate comparison between smokers and non-smokers

### Phase 4 — Predictive Modelling
- One-hot encoding of categorical variables
- Train/test split (80/20)
- Linear Regression model training
- Evaluation: R² score and Mean Absolute Error (MAE)
- Feature importance via regression coefficients

**Libraries used:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`

---

##  Power BI Dashboard — `healthcare_project.pbix`

The dashboard provides a visual summary of the key cost drivers:

| Visual | Type | Description |
|---|---|---|
| Average Medical Insurance Cost | Multi-Row Card | Top-level KPI summary |
| BMI vs Medical Charges by Smoking Status | Scatter Chart | Interaction of BMI and smoking on costs |
| Impact of Smoking on Medical Charges | Clustered Column Chart | Smoker vs. non-smoker cost comparison |
| Average Medical Charges by Region | Clustered Bar Chart | Regional cost breakdown |
| Medical Charges by Age Group | Column Chart | Age-stratified cost profile |

---

##  Key Insights

See [`insights/insights.md`](insights/insights.md) for the full write-up. Highlights:

- Medical charges are **right-skewed** — a small segment of high-cost patients drives a large share of total expenditure
- Smokers incur **~4× higher charges** than non-smokers (₹32,050 vs ₹8,434 on average)
- **100% of smokers** fall in the high-cost patient category vs. only 37% of non-smokers
- **Obese smokers** carry the highest average charges of any group: ~₹41,693
- The regression model achieves **R² = 0.81**, explaining 81% of cost variance
- Smoking status is the single largest cost predictor, adding approximately **$19,400** per patient in the model

---

##  Model Results

| Metric | Value |
|---|---|
| Algorithm | Linear Regression |
| R² Score | 0.81 |
| Mean Absolute Error | ~$4,108 |
| Train/Test Split | 80% / 20% |

**Top predictors by coefficient magnitude:**

| Feature | Cost Impact |
|---|---|
| Smoker (yes) | +$19,400 |
| BMI — Obese | +$6,000 |
| BMI — Overweight | +$2,700 |
| Age (per year) | +$187 |
| Sex, children, region | Minimal |

---

##  Getting Started

### Running the Notebook

1. Clone the repository
2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```
3. Place `insurance.csv` in the `data/` folder
4. Open and run `notebooks/Healthcare_cost_analysis.ipynb`

### Viewing the Dashboard

Open `dashboard/healthcare_project.pbix` in **Microsoft Power BI Desktop** (free download from [powerbi.microsoft.com](https://powerbi.microsoft.com)).

---

##  Tools & Technologies

- **Python 3.x** — Data analysis and machine learning
- **Pandas / NumPy** — Data manipulation
- **Matplotlib / Seaborn** — Visualisation
- **Scikit-learn** — Linear regression modelling
- **Microsoft Power BI** — Interactive dashboard
- **Jupyter Notebook** — Development environment

---

##  Future Enhancements

- Test non-linear models (Random Forest, Gradient Boosting) to improve prediction accuracy
- Apply SHAP values for more interpretable feature importance
- Add interaction terms (e.g., smoking × BMI, smoking × age) to the regression model
- Extend the dashboard with drill-down capability by region and demographic group
- Explore clustering (K-Means) to identify distinct patient risk archetypes
