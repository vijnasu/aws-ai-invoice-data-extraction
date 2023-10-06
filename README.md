# aws-ai-invoice-data-extraction
Incorporating AI/ML and Generative AI techniques into the AWS cloud-based data extraction system can make the process more sophisticated and adaptive to various invoice formats.

# AWS AI-Enabled Real-Time Invoice Data Extraction

A sophisticated cloud solution utilizing AWS services and AI/ML techniques to extract data from invoices in real-time.

## Overview

Harnessing the power of AWS and AI/ML, this project not only extracts textual data from invoices but adapts to various formats and can generate or predict missing information.

## Features

- **AI-Powered Data Extraction**: Uses both Amazon Textract and a custom-trained model on Amazon SageMaker for diverse invoice formats.
- **Generative AI**: Predicts and fills in missing data or provides insights.
- **Real-time Processing & Notification**: Process invoices instantly and notify users through Amazon SNS.

## Prerequisites

- AWS account with access to S3, Lambda, Textract, RDS/DynamoDB, SNS, and SageMaker.
- AWS CLI installed and configured.
- Knowledge of Python (for Lambda functions and ML models).

## Setup

### [1. Data Collection](./1_DATA_COLLECTION.md)

Gather diverse invoice samples and label them using Amazon SageMaker Ground Truth.

### [2. Train ML Models](./2_TRAINING_GUIDE.md)

Use Amazon SageMaker to:
   - Train custom data extraction models.
   - Train Generative AI models for prediction.

### [3. Deploy ML Models](./3_DEPLOYMENT_GUIDE.md)

Once trained, deploy the models as SageMaker endpoints.

### [4. Enhanced Lambda Function](./4_LAMBDA_INTEGRATION.md)

Update the Lambda function in the `lambda/` directory to integrate with the deployed SageMaker endpoints.

## Usage

Upload an invoice to the S3 bucket. The system will automatically process the invoice, extract and/or predict required data, store it in the database, and send a notification.

## Troubleshooting

Check CloudWatch logs for errors or issues during Lambda execution, Textract processing, or SageMaker predictions.

## Contributing

Pull requests are welcome. Discuss major changes in issues first.

## License

MIT
