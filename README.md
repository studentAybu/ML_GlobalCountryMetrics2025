
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

### 1. Data Exploration & Cleaning
- Understand dataset structure
- Handle missing or inconsistent values
- Optionally integrate additional variables (e.g., education, health) from UNDP or [Our World in Data](https://ourworldindata.org/)

### 2. Exploratory Data Analysis (EDA)
- Generate descriptive statistics
- Visualize distributions and correlations
- Compare HDI and GDP across regions and income groups

### 3. Correlation Analysis
- Compute a correlation matrix for numerical variables
- Analyze the relationship between HDI and other key metrics (e.g., GDP per capita, life expectancy)

### 4. Regional Comparisons
- Group countries by continent or HDI level (high, medium, low)
- Use statistical tests (t-test, ANOVA) to compare group differences

### 5. Regression Modeling
- **Target variable**: HDI  
- **Features**: GDP per capita, population, land area, education, life expectancy
- Implement:
  - Simple linear regression (e.g., GDP → HDI)
  - Multiple linear regression (using several predictors)
- Evaluate models using R², RMSE, and MAE

### 6. Advanced Analysis: Clustering & PCA
- Use **K-Means Clustering** to group similar countries
- Apply **Principal Component Analysis (PCA)** to reduce dimensionality and visualize country profiles

### 7. Interpretation & Presentation
- Summarize statistical findings and model outputs
- Create impactful visualizations and geographic maps
- Prepare a clear presentation or report

### 8. Optional Extensions
- **Time-Series Analysis**: If longitudinal data is available
- **IHDI Analysis**: Inequality-adjusted HDI
- **Interactive Dashboard**: Build with Streamlit or Dash

---

## 🛠️ Tools & Technologies

- **Python**: pandas, numpy, matplotlib, seaborn, scikit-learn, geopandas
- **Jupyter Notebook**: for integrated code + analysis + visualization
- **Data Sources**: Kaggle, UNDP, Our World in Data
- **Version Control**: Git & GitHub

---
