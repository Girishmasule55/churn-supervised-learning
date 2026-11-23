# Customer Churn Prediction — Summary Report

> **Complete this report after running the notebook. Replace every bracketed prompt with findings from your actual outputs. Do not invent or estimate model metrics.**

## 1. Business Problem and Dataset

This project addresses customer churn for a telecommunications business. Customer churn occurs when a subscriber stops using or paying for the company's service. Predicting churn can help the retention team identify at-risk customers and take timely action. Retaining an existing customer can be more cost-effective than repeatedly acquiring new customers; the business should consider Customer Acquisition Cost (CAC) alongside Customer Lifetime Value (CLV).

The project uses the IBM Telco Customer Churn dataset, containing 7,043 customer records and demographic, service, contract, billing, and churn information. The target is `Churn`, with `Yes` indicating a customer who left and `No` indicating a retained customer.

## 2. Preprocessing and Class Imbalance

The `customerID` identifier was removed. `TotalCharges` was converted to numeric values and missing values were handled using the median. Additional features included `tenure_group`, `num_services`, and `AutoPay`. Categorical variables were converted into numeric representations, and selected numerical features were standardized.

The data was split into training and test sets using an 80/20 split with stratification and `random_state=42`. SMOTE was applied to the training set only, leaving the test set unchanged. The training class counts before and after SMOTE were:

- Before SMOTE: **[insert class counts]**
- After SMOTE: **[insert class counts]**

## 3. Model Comparison and Recommendation

Four classifiers were evaluated: KNN, Gaussian Naive Bayes, SVM, and Decision Tree.

| Model | Accuracy | Precision (Churn) | Recall (Churn) | F1 (Churn) | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| KNN | [value] | [value] | [value] | [value] | [value] |
| Gaussian Naive Bayes | [value] | [value] | [value] | [value] | [value] |
| SVM | [value] | [value] | [value] | [value] | [value] |
| Decision Tree | [value] | [value] | [value] | [value] | [value] |

**Recommended model:** [insert model name]

The recommended model achieved a churn-class recall of **[value]**, precision of **[value]**, and ROC-AUC of **[value]** on the held-out test set. It is recommended because [explain the balance between missed churners, unnecessary retention calls, interpretability, and prediction speed]. The retention team should also consider how many customers it can realistically contact each day.

## 4. Key Churn Signals and Business Actions

1. **[Signal 1 from EDA or model analysis]:** [Explain the observed relationship and a suitable retention action.]
2. **[Signal 2 from EDA or model analysis]:** [Explain the observed relationship and a suitable retention action.]
3. **[Signal 3 from EDA or model analysis]:** [Explain the observed relationship and a suitable retention action.]

The false-negative analysis found **[count]** churners missed by the selected model. Their average tenure was **[value]** months and their average monthly charge was **[value]**. [Describe any supported difference from the overall churner profile.]

## 5. Next Steps

Possible next steps include collecting richer customer interaction and service-complaint data, validating the model on newer customer cohorts, monitoring performance and data drift, and testing retention campaigns against a control group. A production version should package preprocessing and the selected estimator together, expose a scoring API if needed, and monitor precision, recall, latency, and business outcomes over time.
