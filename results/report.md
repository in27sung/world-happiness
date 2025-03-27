# Project Report: Predicting Country-Level Happiness Scores

## 1. Project Overview
This project investigates the relationship between countries' happiness scores and key economic and social indicators. It aims to build a robust predictive model while addressing data quality challenges such as missing values and inconsistent formatting. The output includes complete data cleaning, exploratory data analysis (EDA), model development, evaluation, and interpretation.

---

## 2. Dataset Description
The dataset combines multiple global indicators for 131 countries, including:
- **Happiness Score** (target variable)
- **GDP per Capita**
- **Unemployment Rate**
- **Education Attainment (%)**
- **Life Expectancy (years)**
- **Year**

---

## 3. Data Preprocessing
### ✅ Cleaning Steps
- **Country Name Standardisation**: Converted to title case.
- **Education_Attainment**:
  - Missing values filled using **country-wise median**.
  - Remaining nulls filled with **overall median**.
- **Life_Expectancy**:
  - Applied **country-wise linear interpolation**.
  - Remaining missing values filled with **overall mean**.
- Final dataset contains **no missing values**.

---

## 4. Exploratory Data Analysis (EDA)
- **Strong positive correlation** observed between GDP per capita and Happiness Score.
- Life Expectancy and Education also show **positive linear relationships**.
- Some lower-GDP countries showed unexpectedly high happiness (outliers flagged).

---

## 5. Modelling
### 📌 Model: RandomForestRegressor
- Trained on cleaned dataset, using features from 2023 for final test.
- Feature Importance: GDP > Life Expectancy > Unemployment > Education

### ✅ Performance
| Metric | Validation | Test (2023) |
|--------|------------|-------------|
| **MAE** | 0.3418 | 0.4072 |
| **RMSE** | 0.4703 | 0.5424 |
| **R² Score** | 0.8286 | 0.7910 |

- **No overfitting observed**: Validation and Test performance are consistent.
- R² ~0.8 indicates **strong predictive power**.

---

## 6. Conclusion & Insights
- The model successfully predicts national happiness based on quantifiable indicators.
- Cleaned data greatly improved predictive performance (compared to R² ~0.6 on unoptimised data).
- Results suggest that **economic strength, education, and health indicators** are key drivers of national happiness.

---

## 7. Recommendations
- Extend model with qualitative or geopolitical indicators (e.g., governance, safety).
- Investigate cultural/subjective factors through survey augmentation.
- Explore time-series prediction or clustering for temporal happiness trends.

---

## 8. Artifacts
- ✅ Cleaned Dataset: `merged_interpolated.csv`
- ✅ Cleaning Summary: `1_data_cleaning.ipynb`
- ✅ Visualisation: Actual vs Predicted Plot (2023)
- ✅ Model: Trained `RandomForestRegressor`

