# House Price Analysis using Multiple Linear Regression

Analyzed King County house price data using Multiple Linear Regression with full diagnostic testing including VIF, Breusch-Pagan, Durbin-Watson, and dummy variable encoding in Python.

---

## About the Project

This project analyzes how different house features affect house prices using Multiple Linear Regression on the King County house sales dataset. It covers the full data analysis pipeline from data cleaning and exploratory analysis to model building, diagnostic testing, and interpretation of results.

```
Dataset     :  King County House Sales (kc_house_data.csv)
Target      :  House Price
Features    :  sqft_living, bedrooms, bathrooms, floors
```

---

## Project Structure

```
Assignment_02/
│
├── Assignment_02.ipynb       # Main Jupyter Notebook
│
├── Step 1  →  Import Libraries and Load Dataset
├── Step 2  →  Select Relevant Variables
├── Step 3  →  Research Hypotheses
├── Step 4  →  Exploratory Data Analysis (EDA)
├── Step 5  →  Data Visualization
├── Step 6  →  Multiple Linear Regression
├── Step 7  →  Diagnostic Tests
└── Step 8  →  Regression with Dummy Variables
```

---

## Research Hypotheses

Four hypotheses were formally tested at a 5% significance level for each independent variable.

**Living Area (sqft_living)**
Larger houses provide more utility so price is expected to increase as square footage increases.

**Bedrooms**
More bedrooms generally increase value, though too many in a fixed space may reduce individual room size and affect price.

**Bathrooms**
Additional bathrooms are a convenience feature that typically adds to the market value.

**Floors**
Houses with fewer floors may have slightly lower value depending on buyer preferences.

---

## Step by Step Breakdown

**Step 1: Data Cleaning**
Missing values and duplicate records were checked and removed. Data types and summary statistics were reviewed to understand the dataset.

**Step 2: Data Visualization**
Pair plots, a correlation heatmap, box plots, histograms, and a 3D scatter plot were used to explore relationships between variables.

**Step 3: Log Transformation**
Price and sqft_living were both found to be right skewed. Log transformation was applied to both columns to make the distribution more normal.

**Step 4: Outlier Removal**
Outliers were removed using the IQR method by filtering values beyond 1.5 times the interquartile range.

**Step 5: Multiple Linear Regression**
A regression model was built using sqft_living, bedrooms, bathrooms, and floors as features to predict house price. The data was split into 75% training and 25% testing.

**Step 6: Multicollinearity Check (VIF)**
Variance Inflation Factor was calculated for all variables. No multicollinearity problem was found.

**Step 7: Normality Check (QQ Plot and Jarque-Bera Test)**
Residuals were plotted on a QQ plot and tested using the Jarque-Bera test. Slight non-normality was found but considered acceptable.

**Step 8: Heteroscedasticity Test (Breusch-Pagan)**
The Breusch-Pagan test was applied to check for heteroscedasticity. The model was re-fitted using HC3 robust standard errors to handle this.

**Step 9: Reduced Model**
Bathrooms showed minimal and insignificant effect so it was removed to simplify the model. The reduced model used sqft_living, bedrooms, and floors.

**Step 10: Autocorrelation Check (Durbin-Watson)**
The Durbin-Watson statistic was close to 2 which confirms no autocorrelation in the residuals.

**Step 11: Dummy Variable Creation**
The floors variable was converted into a categorical variable with Low (1 floor or less) and High (more than 1 floor) categories. Dummy encoding was applied using one-hot encoding with drop_first to avoid the dummy variable trap.

**Step 12: Final Model Interpretation**
The final model with dummy variables showed that sqft_living has a strong positive effect on price, bedrooms show a small negative effect due to overlap with house size, and low floor houses have a slightly lower price compared to high floor houses.

---

## Technologies Used

- Python 3
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Plotly
- Statsmodels
- Scikit-learn
- SciPy

---

## Evaluation and Diagnostics Summary

| Test | Purpose | Result |
|---|---|---|
| VIF | Multicollinearity | No issue found |
| QQ Plot + Jarque-Bera | Normality of residuals | Slight non-normality, acceptable |
| Breusch-Pagan | Heteroscedasticity | HC3 robust errors applied |
| Durbin-Watson | Autocorrelation | Close to 2, no issue |
| OLS Summary | Model significance | All key variables significant |

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/House-Price-Regression.git
   ```

2. Install required libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn plotly statsmodels scikit-learn scipy
   ```

3. Open the notebook:
   ```bash
   jupyter notebook House Price Analysis using Multiple Linear Regression.ipynb
   ```

4. Run all cells from top to bottom.

---

## 📝 License

This project is intended for **academic and non-commercial use only**.

---

## 📧 Author

**Fawad Saqib**  
💬 Reach out via GitHub for feedback or collaboration!
