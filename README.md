# NST DVA Capstone 2 - Project Repository
 
A 2-week industry simulation capstone using Python, GitHub, and Tableau to convert raw data into actionable business intelligence.

## Project Overview

| Field | Details |
| :--- | :--- |
| **Project Title** | Turing_Algo_Analysts_CreditRiskAnalysis |
| **Sector** | Finance |
| **Team ID** | Turing_Algo_Analysts |
| **Members** | Sayuri Jandbandhu, Bhavna Talkute, Shriti Negi, Kirti Gautam, Vanshika |
| **Core Business Question** | How can we predict default risk based on loan-to-income ratio, debt-to-income ratio, and other credit factors to minimize financial exposure? |
| **Decision Supported** | Allow lenders to implement differentiated risk assessment strategies across income and DTI bands, potentially adjusting interest rates or loan amounts based on identified risk clusters. |

## Dataset Details
- **Source**: LendingClub (via `lending_club_loan_two.csv`)
- **Raw Volume**: 396,030 rows, 27 columns
- **Processed Volume**: 389,412 rows, 32 columns
- **Target Variable**: `loan_repayment_status` (Fully Paid vs Charged Off)

## KPI Framework

| KPI Name | Formula / Definition | Business Rationale |
| :--- | :--- | :--- |
| **Loan-to-Income Ratio** | `loan_amount / annual_income` | Shows how large the loan is relative to income. Higher value means the borrower is taking a bigger loan burden. |
| **Installment-to-Income Ratio** | `monthly_installment / (annual_income / 12)` | Measures how much of the borrower's monthly income goes toward loan repayment. |
| **Risk Score** | `0.4*DTI + 0.3*Utilization + 0.2*Loan_Income_Ratio*100 + 0.1*Bankruptcies*10` | Combined risk indicator. Higher score means the borrower may be financially riskier. |
| **Credit Stress Score** | `DTI + Utilization + (Derogatory_Records * 10)` | Measures credit pressure using DTI, credit utilization, and derogatory public records. |

## Key Insights
1. **Income Level is a Meaningful Signal**: Lower-income borrowers are significantly more likely to default.
2. **High Debt Burden Increases Risk**: Borrowers who charged off tend to have a higher debt-to-income ratio (DTI) than borrowers who fully paid. 
3. **Credit Stress Indicators**: Features like `credit_stress_score`, `interest_rate`, and `loan_income_ratio` are among the top predictors of default.

## Project Structure
- `data/raw/` - Raw datasets
- `data/processed/` - Cleaned and engineered datasets
- `notebooks/`
  - `01_extraction.ipynb`
  - `02_cleaning.ipynb`
  - `03_eda.ipynb`
  - `04_statistical_analysis.ipynb`
- `tableau/` - Contains dashboard links
- `reports/` - Final presentation and PDF reports

## Quick Start
**Locally:**
```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```
