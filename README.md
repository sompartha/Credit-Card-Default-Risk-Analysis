# Credit Card Default Risk Analysis

An interactive Power BI dashboard designed to analyse credit card customer behaviour, identify default patterns, and derive insights that can support credit risk assessment and monitoring.

## Project Overview

Credit card default is a significant concern for financial institutions because it directly affects portfolio quality, profitability, and credit risk management.

This project analyses customer demographic information, credit limits, repayment behaviour, and billing patterns to understand the factors associated with credit card default.

The project combines data analysis using Python with interactive visualisation using Microsoft Power BI.

## Project Objectives

- Analyse the distribution of credit card defaults across customer segments.
- Examine the relationship between repayment delays and default rates.
- Investigate default patterns across credit limit categories.
- Study customer characteristics such as age, gender, education, and marital status.
- Develop an interactive dashboard to communicate credit risk insights.

## Technology Stack

| Technology | Purpose |
|---|---|
| Python | Data analysis and preprocessing |
| Jupyter Notebook | Exploratory data analysis |
| Pandas and NumPy | Data manipulation |
| Matplotlib | Data visualisation |
| Microsoft Power BI | Interactive dashboard development |
| DAX | Measures and calculated columns |
| Excel / CSV | Dataset management |

## Dataset Description

The project uses a credit card customer dataset containing demographic, credit, billing, and repayment information.

Important variables include:

- `LIMIT_BAL`: Credit limit assigned to the customer.
- `SEX`: Customer gender.
- `EDUCATION`: Education category.
- `MARRIAGE`: Marital status.
- `AGE`: Customer age.
- `PAY_0` to `PAY_6`: Historical repayment status.
- `BILL_AMT1` to `BILL_AMT6`: Historical bill amounts.
- `PAY_AMT1` to `PAY_AMT6`: Historical payment amounts.
- `DEFAULT`: Credit card default indicator (1 = Default, 0 = Non-Default).

## Data Preparation and Feature Engineering

Data preparation and feature engineering were performed to support meaningful analysis.

Derived features include:

- Age Group
- Credit Utilisation
- Delay Months
- Behavioural Segment
- Credit Limit Band
- Utilisation Category

These features help organise customers into meaningful categories for comparative analysis.

## Dashboard Overview

The Power BI report contains two analytical pages.

### 1. Credit Risk Analytics Dashboard

The first page provides an overview of the credit card portfolio through key performance indicators and visualisations.

Key components:

- Total Customers
- Total Defaulters
- Overall Default Rate
- Average Credit Limit
- Default Rate by Age Group
- Default Rate by Repayment Status
- Default Rate by Credit Utilisation
- Customer Distribution by Credit Utilisation
- Default Rate by Education

### 2. Credit Risk Insights

The second page focuses on customer segmentation and repayment behaviour.

Key components:

- Default Rate by Gender
- Default Rate by Marriage Status
- Default Rate by Credit Limit
- Default Rate by Repayment Delay

## Key Analytical Measures

The dashboard uses DAX measures to calculate portfolio-level indicators.

**Total Customers**
```DAX
Total Customers = COUNTROWS(CustomerData)
```

**Total Defaulters**
```DAX
Total Defaulters =
CALCULATE(
    COUNTROWS(CustomerData),
    CustomerData[DEFAULT] = 1
)
```

**Default Rate**
```DAX
Default Rate =
DIVIDE(
    [Total Defaulters],
    [Total Customers],
    0
)
```

**Average Credit Limit**
```DAX
Average Credit Limit =
AVERAGE(CustomerData[LIMIT_BAL])
```

For segment-level default rates, the average of the binary `DEFAULT` variable is used.

## Repository Structure

```text
Credit-Card-Default-Risk-Analysis/
│
├── Credit_Risk_Analytics_Dashboard.pbix
├── Credit_Risk_Analysis (1).ipynb
├── credit_risk_cleaned_data (1).csv
└── README.md
```

## Key Takeaways

The dashboard enables users to:

- Compare default rates across demographic groups.
- Identify repayment patterns associated with higher default rates.
- Examine credit utilisation and credit limit segments.
- Explore customer-level risk patterns through interactive visualisations.

The analysis is exploratory. Observed associations should not be interpreted as proof of causation or as a validated credit approval model.

## Future Improvements

- Develop predictive credit default models using machine learning.
- Compare classification algorithms using precision, recall, F1-score, and ROC-AUC.
- Incorporate model explainability techniques such as SHAP.
- Develop customer-level risk scoring and early warning indicators.
- Extend the analysis using Expected Credit Loss modelling when reliable Exposure at Default and Loss Given Default assumptions are available.

## Author

**Samarpita Sinha**

Mechanical Engineering | IIT Kharagpur

GitHub: [sompartha](https://github.com/sompartha)

LinkedIn: [Samarpita Sinha](https://www.linkedin.com/in/sompartha-sinha-46b055298/)
