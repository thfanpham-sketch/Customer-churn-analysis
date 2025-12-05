
# Telco Customer Churn – MIS-Friendly Portfolio Project

## Objective
Predict which customers are likely to churn and recommend practical actions to reduce churn.

## Data
IBM Telco Customer Churn (Kaggle). Contains contract type, services, payment method, tenure (months), charges, and churn label (Yes/No).

## Steps I Completed
1. **Data cleaning**  
   - Converted `TotalCharges` to numeric and imputed blanks using `MonthlyCharges * tenure`.
   - Created `Churn_Flag` (1 = churned, 0 = stayed).

2. **Exploratory analysis (EDA)**  
   - **Churn by contract:** Month-to-month has the highest churn; one-year lower; two-year is the lowest.  
   - **Churn by payment:** Electronic check shows highest churn; automatic methods (card/bank transfer) are lower.  
   - **Tenure effect:** Short-tenure customers churn more.

3. **Model (Logistic Regression)**  
   - Train/test split (80/20), one-hot encoding for categorical, scaling for numeric.
   - **Metrics (default threshold 0.50):**  
     - Accuracy: ~0.74  
     - ROC‑AUC: ~0.84  
     - Precision: ~0.50  
     - Recall: ~0.78  
   - **Threshold tuning:** at 0.45, Recall ↑ ~0.84 (catch more churners) with Precision ~0.48.

4. **Top churn drivers (coefficients)**  
   - `InternetService_Fiber optic` (risk ↑)  
   - `Contract_Month-to-month` (risk ↑)  
   - `TotalCharges` (higher → risk ↑)  
   - `PaymentMethod_Electronic check` (risk ↑)  
   - Lack of `OnlineSecurity` / `TechSupport` (risk ↑)

## Business Recommendations
- **Promote longer contracts:** Discount or benefits for upgrading month‑to‑month customers to 1–2 year plans.  
- **Incentivize AutoPay:** Move customers off electronic checks to bank transfer/credit card via perks or credits.  
- **Onboard new customers:** First 90‑day welcome journey, quick tips, early check‑ins; target short‑tenure segments.  
- **Value bundles:** Add OnlineSecurity/TechSupport bundles, trials, or loyalty perks to boost perceived value.

## Project Files
- `notebooks/01_churn_analysis.ipynb` – cleaning, EDA, model, metrics, charts  
- `reports/figures/` – saved visuals 
- `data/` – dataset CSV 
- `.venv/` – virtual environment (excluded via `.gitignore`)


