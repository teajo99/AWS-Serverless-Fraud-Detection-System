# AWS Serverless Fraud Detection System

## Overview

This project is a serverless fraud detection system built on AWS.  
It processes tax submissions, stores audit records, detects fraud in real time, and sends alerts using event-driven architecture.

---

## Architecture

EventBridge → Lambda (Tax Processor) → DynamoDB → Lambda (Fraud Detection) → SNS → SQS / Email

---

## AWS Services Used

- Amazon EventBridge
- AWS Lambda
- Amazon DynamoDB
- Amazon SNS
- Amazon SQS
- AWS IAM
- Amazon CloudWatch

---

## Features

- Event-driven processing
- Real-time fraud detection
- Scalable serverless architecture
- Audit logging
- SNS alert notifications
- SQS compliance queue

---

## Fraud Rules

A tax return is flagged as suspicious if:

- Income > 1,000,000
- Deductions > 80% of income
- Income is negative

---

## How It Works

1. EventBridge receives tax submission event
2. TaxProcessor Lambda stores data in DynamoDB
3. FraudDetection Lambda evaluates risk
4. SNS sends fraud alerts
5. SQS/email receives notifications