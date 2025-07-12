
# 🌍 Global Country Metrics Analysis (HDI, GDP, Population, Area, etc.)

This project analyzes global country-level indicators — including Human Development Index (HDI), GDP per capita, population, and land area — using data from the [Kaggle Global Country Metrics Dataset](https://www.kaggle.com/datasets/prashantdhanuk/global-country-metrics-2025-hdi-gdp-pop-area?resource=download).

---

## 🎯 Project Objective

- Explore the relationships between economic, demographic, and development indicators
- Identify key factors that influence HDI
- Perform regional comparisons of development levels
- Build predictive models to estimate HDI based on other variables

---

## 🧭 Project Workflow

## 🔧 1. Requirements

```bash
pip install opendatasets pandas seaborn matplotlib scikit-learn plotly
```

---

## 📥 2. Dataset Download

* Dataset was downloaded from Kaggle using `opendatasets`:

```python
import opendatasets as od
od.download("https://www.kaggle.com/datasets/prashantdhanuk/global-country-metrics-2025-hdi-gdp-pop-area")
```

---

## 📊 3. Loading and Initial Exploration

* CSV file was loaded using Pandas, and basic information was displayed.
* Missing values were removed.
* Data types were converted appropriately.

---

## 🧹 4. Data Cleaning and Transformation

### a) Extracting numeric values from non-numeric columns

```python
def toNumericSeries(el):
  ...
```

* Characters like `$`, `,`, and spaces were removed.
* Columns such as population, area, and GDP were converted to numeric format.

### b) Special cleaning of the population column

```python
def clean_population_column(df, column_name):
  ...
```

---

## 🧠 5. Feature Engineering

* **HDI categories** were created:

  * Low: HDI ≤ 0.549
  * Medium: 0.55–0.699
  * High: 0.7–0.799
  * Very High: ≥ 0.8

* New columns:

  * `population_density` (population per unit area)
  * `total_gdp` (PPP GDP per capita × population)

---

## 📈 6. Correlation and Distribution Analysis

* Correlation matrix was created.
* Numerical features were analyzed using boxplots and KDE (kernel density estimation).
* Log transformation was applied when necessary.

---

## 🧽 7. Outlier Treatment

* Outliers were capped using the IQR method.

```python
def fit_outliers(x, q1, q3):
  ...
```

---

## 🧮 8. Modeling

### Features Used:

* `numeric_population`
* `numeric_area`
* `numeric_gdp_per_capita`
* `numeric_nominal_gdp`
* `numeric_nominal_gross`
* `GINI`

### Models Used:

* Linear Regression
* Ridge Regression
* Lasso Regression
* Random Forest Regressor

### Model Comparison:

```text
Random Forest > Ridge ≈ Linear > Lasso
```

### Evaluation Metrics:

* R² (coefficient of determination)
* RMSE (Root Mean Squared Error)
* MAE (Mean Absolute Error)

```python
# Performance evaluation
mean_squared_error(), mean_absolute_error(), cross_val_score()
```

---

## 🌎 9. Map Visualization

* HDI distribution was visualized on a **world map** using Plotly:

```python
fig = px.choropleth(...)
```

---

## 🔍 10. Feature Importance Analysis

* Most important variables were identified using Random Forest.

```text
1. GDP Per Capita PPP (77.8%)
2. Nominal GDP Per Capita (13.9%)
3. GINI (3.4%)
```

---

## 📉 11. Extra: Bayesian Ridge 

After defining and training the Bayesian Ridge Regression model, the values were obtained by using the `return_std=True` parameter in the `predict` function. This allowed predictions and standard deviations to be successfully calculated, enabling the uncertainty interval to be plotted on the graph.


---

## 🛠 12.Tools & Technologies

### Tools and Libraries Used:

* **Python 3.11**: Primary programming language for data processing, analysis, and modeling
* **Pandas**: Used for loading, cleaning, transforming, and analyzing tabular data
* **NumPy**: Supports numerical operations and efficient array handling
* **Matplotlib & Seaborn**: Used for static data visualizations, including boxplots, KDE, and correlation heatmaps
* **Scikit-learn**: Provides machine learning models (Linear, Ridge, Lasso, Random Forest), preprocessing utilities, and evaluation metrics (R², RMSE, MAE)
* **Plotly Express**: Enables creation of interactive visualizations, including the choropleth HDI world map
* **OpenDatasets**: Simplifies the process of downloading datasets directly from Kaggle
* **Jupyter Notebook / Google Colab**: Interactive environments used for code development, testing, and documentation

---

## 📌 Summary

This project includes:

* Data cleaning and transformation
* Feature engineering
* Visualization and correlation analysis
* Outlier treatment
* HDI prediction using four different models
* Model comparison and cross-validation
* HDI map and feature importance analysis

---

## ✨ Conclusion

The Random Forest Regressor gave the most successful results with an **R² score of 97.5%**. This model was especially effective at predicting HDI based on **GDP per capita (PPP)**.

---
