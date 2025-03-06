
# Transitions in Focus: Delinquency to Resolution in California

## Summary

This project focuses on analyzing the transition of mortgage loans from delinquency to resolution within California’s secondary market. By integrating Freddie Mac’s loan-level data with external economic indicators, the study employs advanced machine learning techniques—including multinomial logistic regression and XGBoost—to predict loan performance and monitor status transitions. The analysis spans pre-COVID, COVID, and post-COVID periods to capture dynamic borrower behavior, ultimately guiding risk management and strategic decision-making in the housing market.

## Business Overview and Objectives

**Business Context:**  
Freddie Mac supports liquidity and stability in the U.S. housing market by purchasing loans from banks and securitizing them. Monitoring transitions in loan delinquency is crucial, as prepayments reduce long-term interest revenue while defaults incur unrecoverable losses.

**Key Objectives:**
- Predict the progression of 30-day delinquent mortgage loans.
- Evaluate the impact of economic shifts on loan performance.
- Minimize forecasting errors (using RMSE) to improve risk assessment.
- Analyze loan transition trends across pre-COVID, COVID, and post-COVID periods.

## Data Highlights and Preparation

**Data Sources:**
- **Freddie Mac’s Loan-Level Dataset:** Over 1 million loans and detailed monthly performance data capturing transitions in loan status.
- **External Economic Indicators:** Data on GDP growth, unemployment rates, and the House Price Index (HPI) for macroeconomic context.

**Data Integration:**  
Datasets were unified by matching Loan Sequence Numbers, resulting in a comprehensive California-specific dataset covering both origination and monthly performance.

**Data Cleaning:**  
- Replaced out-of-range values and placeholder codes with NA.
- Converted columns to appropriate data types.
- Isolated 30-day delinquent loans for focused analysis.
- Integrated economic indicators to assess external impacts on loan performance.

## Methodology

**Feature Engineering:**  
Key variables were derived, including loan age, interest rate, credit score, and delinquency indicators. Lagged features were created to track transitions over time.

**Modeling Techniques:**
- **Multinomial Logistic Regression:**  
  Used for its interpretability in classifying loan delinquency statuses; evaluated across different economic periods.
- **XGBoost:**  
  Employed to capture non-linear relationships and improve predictive accuracy, demonstrating superior performance, especially during the COVID period.

**Evaluation Metrics:**  
Accuracy and RMSE were the primary metrics. Notably, the XGBoost model achieved RMSE values of 7.58% (pre-COVID), 1.47% (during COVID), and 4.74% (post-COVID).

## Findings and Insights

- **Transition Trends:**  
  - *Pre-COVID:* A significant portion of loans transitioned to 60-day delinquency, indicating early risk signals.  
  - *During COVID:* The majority of loans remained current, likely due to borrower relief measures.  
  - *Post-COVID:* A moderate increase in 90+ day delinquency was observed, reflecting gradual normalization.
  
- **Credit Score Dynamics:**  
  Loans with higher credit scores (700+) tended to remain current, suggesting that creditworthiness is a strong predictor of loan stability.

- **Loan Age Impact:**  
  Newer loans exhibited higher transition activity, while older loans showed increased persistence in delinquency, emphasizing the need for timely intervention.

## Challenges and Workarounds

- **Data Integration Issues:**  
  Incomplete records (e.g., missing MSA codes) complicated urban-rural analysis; a mapping workaround using ZIP codes was attempted, though with limitations.

- **Validation Constraints:**  
  Fewer data points in recent years risked model overfitting; thus, the model was trained on data up to 2018 to ensure robust performance and then validated on later periods.

## Recommendations

- **Lending Practices:**  
  Prioritize borrowers with credit scores above 700 to minimize delinquency risk and employ stricter criteria for lower credit score segments.

- **Early Intervention:**  
  Focus on engaging borrowers in the early stages (0–39 months) to prevent escalation of delinquency, and provide tailored support for older loans (60+ months) where resolution rates decline.

- **Refinancing Incentives:**  
  Offer refinancing options to high-performing borrowers to reinforce stable repayment behavior.

## Roadmap and Future Work

**Short-Term Goals:**
- Enhance model precision through additional feature engineering and incorporating more granular economic data.
- Refine validation strategies to better capture recent trends and reduce overfitting.

**Long-Term Strategies:**
- Expand the dataset to include emerging trends in borrower behavior and external economic conditions.
- Investigate the integration of real-time data feeds to continuously update model predictions.
- Explore alternative modeling approaches and ensemble techniques to further reduce forecasting errors.

## Conclusion

This project demonstrates that sophisticated machine learning models can effectively predict transitions in mortgage loan delinquency, supporting risk management in California’s housing market. By integrating comprehensive loan-level data with economic indicators, the study provides valuable insights into borrower behavior across different economic periods. The actionable recommendations derived from this analysis can help mitigate risks, enhance financial stability, and guide strategic decision-making in the mortgage industry.

