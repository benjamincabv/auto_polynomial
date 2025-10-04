# auto_polynomial
# Automotive Data Modeling: MPG vs. Horsepower
By Benjamin Cabrera & Alexander Ohye

Modeling fuel efficiency (MPG) as a nonlinear function of horsepower using polynomial regression and cross-validation (ISLR Auto dataset).

## Introduction

This project explores how automotive features can be used to **predict fuel efficiency (miles per gallon, mpg)** using polynomial regression techniques.  

The dataset contains variables such as horsepower, cylinders, displacement, weight, acceleration, year, and origin.  

The goal is to apply polynomial regression with different degrees (2, 3, and 4) to model the nonlinear relationship between horsepower and mpg, evaluate performance using cross-validation, and identify the degree that best balances accuracy and generalization.  

A data frame with 392 observations on the following variables:

- mpg: Miles per gallon (target variable)  
- cylinders: Number of cylinders  
- displacement: Engine displacement (cubic inches)  
- horsepower: Engine horsepower  
- weight: Vehicle weight (lbs)  
- acceleration: 0–60 mph time (seconds)  
- year: Model year  
- origin: Origin (USA, Europe, Japan)  
- name: Car name (dropped in this analysis)

**The outcome variable to predict is *mpg*.**

---

## Methods

- Focused on the nonlinear relationship between horsepower and mpg  
- Standardization and polynomial feature transformation (degrees 2–4)  
- 10-fold cross-validation for model selection  
- Train/test evaluation using RMSE and MSE  
- Visualization of fitted curves and residuals  

Libraries used:
`pandas`, `numpy`, `matplotlib`, `scikit-learn`

---

## Key Results

**Cross-Validation Mean MSE:**
- Degree 2 → 18.81  
- Degree 3 → 18.93  
- Degree 4 → 19.43  

**Selected model:** Degree 2 (quadratic)  
**Test RMSE:** 4.626  
**RMSE as % of mean mpg:** 19.73%

**Quadratic equation (standardized horsepower h):**  
mpg ≈ 21.72 − 7.82·h + 1.61·h²

---

## Interpretation

The quadratic term captures the diminishing returns in efficiency:  
mpg decreases as horsepower increases, but the effect levels off for high horsepower vehicles.  
Higher-degree polynomials slightly worsened validation error, confirming that a simple quadratic model generalizes best.

---

## Conclusion

Polynomial regression revealed a clear nonlinear relationship between horsepower and fuel efficiency.  
Cross-validation identified the quadratic model as the optimal balance between bias and variance, achieving a test RMSE of about 4.6 (≈20% of mean mpg).  
This demonstrates how polynomial regression can effectively capture curvature in real-world data while maintaining interpretability and strong generalization.

---

## How to Run

1. Clone this repository.  
2. Place `Auto_ISLR.csv` in the project root.  
3. Open `auto-mpg-polynomial.ipynb` in Jupyter or Google Colab.  
4. Run all cells to reproduce results.

---

## Skills Demonstrated

- Polynomial regression modeling  
- Feature scaling and transformation  
- Cross-validation and model selection  
- Visualization of nonlinear relationships  
- Model evaluation and interpretability
