# DA5401: A6 – Imputation via Regression for Missing Data
**Author:** Yash Purswani\
**Roll Number:** ME22B214

## Overview
This notebook investigates various strategies for handling **missing data** in the [UCI Credit Card Default dataset](https://www.kaggle.com/datasets/uciml/default-of-credit-card-clients-dataset). 
The focus is on understanding how different imputation and deletion methods influence the **classification performance** of models predicting the target variable — `default payment next month`.

The notebook systematically compares:
- **Model A:** Mean/Median Imputation  
- **Model B:** Linear Regression Imputation  
- **Model C:** Random Forest Imputation  
- **Model D:** Listwise Deletion  

Performance is evaluated using **Precision**, **Recall**, and **F1 Score**, visualized through a **spider (radar) chart**.

## Objectives
- Introduce controlled missingness (MAR: Missing At Random) in selected numerical features.  
- Apply different imputation methods and evaluate their effect on classification accuracy.  
- Compare Linear and Non-Linear regression methods for imputing missing values.  
- Recommend the best missing data strategy based on both **theoretical assumptions** and **empirical model performance**.

## Key Concepts
- **MAR (Missing At Random):** Missingness depends on observed variables, not on the missing value itself.  
- **Listwise Deletion:** Removes all rows containing missing data, potentially losing valuable information.  
- **Imputation:** Fills missing values using statistical or predictive models to retain all samples.  
- **Linear vs. Non-Linear Imputation:** Linear models assume simple relationships; non-linear models (like Random Forest) capture complex feature interactions.

## Methodology
1. **Data Preparation:**  
   - Loaded and explored the credit card dataset.  
   - Artificially introduced MAR-type missingness (5–10%) in 2–3 numerical columns.

2. **Imputation Techniques:**  
   - Mean/Median Imputation  
   - Linear Regression Imputation  
   - Random Forest Imputation  

3. **Model D – Listwise Deletion:**  
   - Rows with missing values were dropped before model training.

4. **Evaluation Metrics:**  
   - Precision, Recall, and F1 Score compared across all models.  
   - Radar chart visualized model trade-offs.


## Results Summary
- **Random Forest Imputation (Model C)** yielded the best overall performance.  
- **Linear Regression Imputation (Model B)** performed reasonably but was limited by linear assumptions.  
- **Listwise Deletion (Model D)** performed poorly due to information loss.

## Conclusion
For this dataset, **non-linear model–based imputation (Random Forest)** is the most effective strategy.  
It preserves data size, captures complex dependencies, and results in higher predictive performance compared to deletion or simple imputation methods.

## Tools and Libraries
- Python 3.x
- Libraries: `numpy`, `pandas`, `scikit-learn`, `matplotlib`

## File Structure

- `ME22B214_A6.ipynb` → Main notebook with code, plots, and explanations.
- `UCI_Credit_Card.csv` → Dataset (downloaded from Kaggle).
- `README.md` → Project overview and insights.

## How to Run  
1. Install required libraries:  
   ```bash
   pip install pandas numpy scikit-learn seaborn matplotlib
2. Place `UCI_Credit_Card.csv` in the working directory
3. Open the notebook:
    ```bash
    jupyter notebook ME22B214_A6.ipynb
4. Run all cells to reproduce results.
