# 📈 Sales Forecasting & Time Series Analysis: AdventureWorks Case Study

This project explores **sales forecasting** using both traditional and advanced time series models, delivering actionable insights for decision-makers.

We analyzed **two years of monthly and daily sales data** from AdventureWorks, built robust models, and evaluated their accuracy and adaptability — providing clear recommendations aligned with business realities.

---

## 🔗 Project Objectives

- Forecast future sales for **12 months** to support strategic planning.
- Compare **Multiple Regression**, **Holt-Winters (Exponential Smoothing)**, and **SARIMA** models.
- Evaluate **accuracy, explainability, and robustness** of each model.
- Identify business-relevant insights, weaknesses, and actionable recommendations.

---

## 📊 Models & Results

### 1️⃣ Multiple Regression Model (Excel, Monthly Data)

- Built with aggregated monthly sales & dummy variables.
- Forecast generated directly in Excel, with KPIs:

| Metric      | Value         |
|-------------|---------------|
| ✅ R²       | **88.95%**    |
| ✅ MAPE     | **11.17%**    |
| ✅ MAD      | **$315,040**  |
| ✅ Mean Bias| **0.19%**     |

**Strengths:**
- High explanatory power and interpretability.
- Best fit when business environment remains stable.

**Weaknesses:**
- Assumes fixed patterns; less reactive to sudden changes.

---

### 2️⃣ Time Series Decomposition (R Script in Power BI)

- Decomposed sales into **Trend**, **Seasonality**, and **Residuals**.

**Key Insights:**
- Strong annual **seasonality** with peaks around Q2–Q3.
- Gradual **upward trend** over time.
- Residuals analysis showed no significant autocorrelation, suggesting good model fit.
- A **shift in behavior observed in May 2020**, not captured by historical trends.

---

### 3️⃣ Holt-Winters (Python, Power BI)

- Tested three configurations:
  - Additive Trend + Additive Seasonality
  - Multiplicative Trend + Multiplicative Seasonality
  - 🌟 Multiplicative Trend + Multiplicative Seasonality + **Damped Trend**

**Best Model:**  
🌟 **Mul+Mul+Damped**

| Metric        | Value         |
|---------------|---------------|
| 📈 MAPE       | ~**17.3%**    |
| 📉 MAD        | ~$353,149~    |
| 📊 RMSE       | ~$530,000~    |

**Strengths:**
- More adaptive to recent changes.
- Automatically assigns higher weight to recent observations.
- Robust to moderate volatility.

---

### 4️⃣ SARIMA Model (Python, Power BI & Notebook)

- SARIMA tuned for seasonality & autocorrelation.

**Performance:**
| Metric | Value      |
|--------|------------|
| MAPE   | ~46%       |

**Notes:**
- Poorer fit than others due to limited training & complexity constraints in Power BI.
- Useful for experimentation but computationally intensive within Power BI.

---

## 🔍 Observed Structural Shift: May 2020

In **May 2020**, actual sales exhibited a noticeable **upward shift** not anticipated by the Regression Model (trained on pre-2020 data).  
This event suggests the presence of an external factor (e.g., product launch, market change) that introduced a structural break.

- 📌 Regression Model could not capture this as it relies on fixed assumptions.
- 📌 Holt-Winters, being adaptive, responded better to this change.
- 📌 SARIMA, while flexible, struggled due to complexity & resource constraints.

---

## 🚀 Business-Friendly Summary & Recommendations

> *“The Regression Model remains the most accurate and interpretable choice based on historical data. However, the structural shift observed in May 2020 — which was not accounted for in the trained model — could make forecasts less reliable if similar disruptions occur in the future.”*

### Recommendations:

✅ Use the **Regression Model** for:
- Understanding historical drivers.
- Diagnostic and explanatory reporting.
- Forecasting when business patterns are stable.

✅ Use the **Holt-Winters Mul+Mul+Damped Model** for:
- Environments with volatility, shocks, or evolving trends.
- Reacting to structural shifts like the May 2020 event.

✅ Next Steps:
- Retrain the Regression Model with post-May 2020 data and include a dummy variable for the shift.
- Monitor both models over time and evaluate holdout periods.
- Consider an **ensemble approach** combining both models’ strengths.
- If computational resources permit, further explore tuned SARIMA or machine learning-based forecasting for long-term enhancement.

---

## 📚 Skills & Tools Demonstrated

- 📊 Business Analytics & KPI Reporting
- 🐍 Python (`statsmodels`, `sklearn`, `matplotlib`)
- 📈 Excel Multiple Regression
- 📉 R Script Time Series Decomposition
- 📊 Power BI Custom Visuals & Automation
- 🧐 Forecast Accuracy Metrics: **MAPE, MAD, RMSE, R², Bias**

---

## 🎯 Value Delivered

This project bridges the gap between **statistical rigor and business impact**, empowering decision-makers to:

- Choose the right forecasting model based on market stability.
- Understand key sales drivers and structural changes.
- Improve planning agility in dynamic environments.

By delivering accurate forecasts and identifying potential pitfalls, this analysis provides a roadmap for smarter, data-driven decisions.

---

*For questions or collaboration opportunities, feel free to reach out!*
