# 🥣 Predictive Modeling on Cereal Ratings: Nutritional Optimization & Linear Regression

This project constructs a robust multiple linear regression framework to evaluate how individual nutritional components drive consumer perception, using a dataset from Consumer Reports covering 77 breakfast cereal brands. The analysis focuses heavily on strict econometric diagnostics, power transformations, and feature selection to optimize model validity.


## 🛠️ Statistical Methodology & Workflow

1. **Exploratory Data Analysis (R):** Cleaned incomplete records, analyzed feature spread, and generated multi-variable correlation heatmaps to isolate baseline health trends (such as sugar's strong negative correlation with overall ratings).

2. **Strict Assumption Diagnostics:** Formally tested the classical linear regression assumptions:
   * Checked linearity and homoscedasticity using residual-vs-fitted spreads.
   * Detected a violation of the normality assumption using **Shapiro-Wilk** testing ($W = 0.931, p < 0.001$) and Q-Q diagnostics.
   * Validated residual independence via a **Durbin-Watson** test ($DW = 1.77, p = 0.139$) to rule out autocorrelation.
   * Evaluated variance inflation factors (VIF), confirming no presence of multicollinearity.

3. **Model Remediation (Box-Cox Transformation):** Implemented an optimal power transformation ($\lambda \approx 0.91$) to stabilize residual variance and achieve normality under Gauss-Markov assumptions.

4. **Feature Selection (Stepwise AIC):** Applied backward elimination to strip away non-significant parameters, yielding a highly parsimonious model focused exclusively on three dominant health metrics: **Sugars, Fiber, and Sodium**.


## 🔑 Key Findings
The final reduced model achieves an **Adjusted $R^2$ of 0.9158**, maintaining full explanatory power while reducing parameter noise. 

* **The Sugar & Salt Penalty:** Holding all else constant, increases in sugar and sodium induce statistically significant, heavy penalties on a cereal's overall market rating.

* **The Fiber Premium:** Dietary fiber acts as the strongest positive driver of consumer ratings, offering actionable insight for product formulation and market positioning.

---

### 📂 Files Included in this Repository:
* `CerealsRating.csv`: The clean, processed dataset.
* `Project STAT 481.Rmd`: The raw R Markdown source code containing the end-to-end data pipeline.
* `Project-STAT-481.html`: The fully rendered, production-ready research report with dynamic plots and tables.
