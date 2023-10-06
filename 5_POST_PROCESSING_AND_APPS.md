# Post-Processing & Application Development on Invoice Data

Once we've extracted invoice data, it's essential to process, cleanse, and then use it to develop insightful applications.

## Table of Contents

1. Data Cleansing
2. Central Storage in AWS
3. Applications
   - Anomaly Detection
   - Expense Forecasting
   - Vendor Analysis
   - Category-wise Spending Analysis
   - Invoice Approval Automation

### 1. Data Cleansing

Data cleansing involves:

- Removing duplicates.
- Filling missing values or flagging them.
- Validating invoice data against known formats or lists.

### 2. Central Storage in AWS

Storing the processed data centrally is crucial. We recommend using Amazon RDS for structured invoice data or Amazon Redshift if you're planning more extensive data warehousing and analytics. 

### 3. Applications

#### a. Anomaly Detection

Utilize Amazon SageMaker with built-in anomaly detection algorithms. Train a model on the historical invoice data, and then evaluate new invoices against this model to flag potential anomalies.

[Detailed Guide on Anomaly Detection](./5.1_ANOMALY_DETECTION.md)

#### b. Expense Forecasting

Leverage time-series forecasting models in SageMaker, like DeepAR, to predict future expenses based on historical data.

[Detailed Guide on Expense Forecasting](./5.2_EXPENSE_FORECASTING.md)

#### c. Vendor Analysis

Analyse vendor-related metrics to evaluate their performance, consistency, and more. Amazon QuickSight can be a great tool for visual analytics.

[Detailed Guide on Vendor Analysis](./5.3_VENDOR_ANALYSIS.md)

#### d. Category-wise Spending Analysis

Break down expenses into categories and analyze trends, spikes, or reductions in spending over time.

[Detailed Guide on Spending Analysis](./5.4_SPENDING_ANALYSIS.md)

#### e. Invoice Approval Automation

Develop a Lambda function to automatically approve or flag invoices based on certain criteria. This can be integrated with AWS Step Functions for a more complex workflow.

[Detailed Guide on Invoice Approval Automation](./5.5_INVOICE_APPROVAL_AUTOMATION.md)

## Conclusion

With the processed and cleansed invoice data, numerous applications can provide insights, automation, and value to businesses.
