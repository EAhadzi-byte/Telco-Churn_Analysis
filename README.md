📊 Customer Churn Analysis & Predictive Modeling
📝 Project Overview
This project addresses the critical business challenge of Customer Churn. By analyzing historical customer data, I built a machine learning pipeline to identify at-risk users and provide data-driven recommendations to improve retention rates.

🛠️ The Pipeline
1. Data Cleaning & Preprocessing
Missing Value Imputation: Handled nulls in TotalCharges using median values to maintain data distribution.

Data Typing: Converted categorical strings into numerical formats for model compatibility.

Handling Outliers: Audited tenure and billing columns for statistical anomalies.

2. Exploratory Data Analysis (EDA)
Key Visual Insights:

The 6-Month Danger Zone: Churn is highest among customers in their first half-year.

Price Sensitivity: A sharp increase in churn was observed once MonthlyCharges exceeded $70.

Contract Power: Month-to-month users are 4x more likely to leave than those on two-year contracts.

Payment Friction: Electronic check users show significantly higher churn than those on autopay.

3. Feature Engineering
Created new behavioral indicators to boost model "signal":

Stickiness Score: A metric combining multiple add-on services (Online Security, Tech Support, etc.).

Price-to-Tenure Ratio: Identifying high-paying new customers who represent the highest financial risk.

4. Machine Learning Modeling
I compared two distinct approaches to find the optimal balance of interpretability and power:
Model,                         Purpose,                    Performance (ROC-AUC)
Logistic Regression,       Baseline & Interpretability,      ~0.80
Random Forest              ,Capturing Complex Patterns       ,0.84
Hyperparameter Tuning: Conducted sensitivity analysis on n_estimators, max_depth, and min_samples_leaf to reach the final optimal configuration.

🔍 Post-Predictive Analysis & Error Profiling
Instead of trusting the "Black Box," I performed a deep dive into the model's decisions:

Feature Importance: Identified that Tenure, Total Charges, and Contract Type are the primary drivers of the model's predictions.

False Negative Analysis: Investigated "Silent Leavers" (customers the model missed) to identify unobserved factors like service quality.

Probability Ranking: Generated a "Priority Hit-List" of the top 10% most at-risk customers for immediate intervention.

💡 Business Recommendations
Targeted Onboarding: Launch a "Success Program" for new customers in the first 90 days to bridge the "6-month churn gap."

Incentivize Autopay: Move customers away from Electronic Checks toward Automated Clearing House (ACH) or Credit Card payments to reduce "monthly payment fatigue."

High-Value Retention: Use the Churn Probability Score to assign human account managers to the top 5% of at-risk, high-revenue customers.

Service Bundling: Promote "anchor" services like Tech Support and Security, as they significantly increase customer "stickiness."
