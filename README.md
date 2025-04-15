# Multiclass Text Classification on AWS

A production-ready news headline classification system deployed on AWS Cloud.

Video Link : https://drive.google.com/file/d/1iWA-DgLednUmPh6HMF8MwcBVIVWC3bhR/view?usp=sharing

## Project Overview

This project implements an end-to-end machine learning pipeline for classifying news headlines into four categories: Business, Entertainment, Science, and Health. It demonstrates how to take a model from development to production using AWS services.

## Architecture
![Editor _ Mermaid Chart-2025-04-15-022717](https://github.com/user-attachments/assets/965be26d-f2bf-4aaa-a1c4-d796250bf55e)

The system consists of two main pipelines:

### Training Pipeline
- Data preprocessing and EDA on news headlines dataset
- Fine-tuning a DistilBERT model for multiclass classification
- Storing model artifacts in S3

### Inference Pipeline
- API Gateway for receiving classification requests
- Lambda function for request processing
- SageMaker endpoint hosting the model
- CloudWatch for monitoring and logging
- DynamoDB for transaction logging

## Key Components

### Model Architecture
The system uses a modified DistilBERT architecture with:
- Pre-trained DistilBERT base model
- Custom classification head with 768-dimensional hidden layer
- ReLU activation and dropout for regularization
- Softmax output for 4-class classification

### AWS Services Used
- **Amazon S3**: Stores model artifacts and training data
- **Amazon SageMaker**: Hosts the model for inference
- **AWS Lambda**: Processes API requests
- **Amazon API Gateway**: Provides RESTful API endpoint
- **Amazon CloudWatch**: Monitors performance
- **Amazon DynamoDB**: Logs transactions

## Getting Started

### Prerequisites
- Python 3.6+
- PyTorch
- Transformers library
- AWS CLI configured with appropriate permissions

### Training the Model
1. Run the EDA notebook to understand the dataset
2. Execute `script.py` to train the model
3. Model artifacts will be saved for deployment

### Deploying the Model
1. Use the Deployment notebook to create a SageMaker endpoint
2. Configure the Lambda function in `aws-lambda-llm-endpoint-invoke-function.py`
3. Set up API Gateway to trigger the Lambda function

### Testing the Endpoint
1. Use the load testing scripts in the `load-testing` directory
2. Monitor performance in CloudWatch

## Future Improvements
- Data drift monitoring
- Live API for continuous data ingestion
- MongoDB feature store
- A/B testing of model versions
- Automated retraining pipeline
- CI/CD for deployment automation

## Contact
Sahil Amundkar - sahil.amundkar@gmail.com
