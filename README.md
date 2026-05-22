# BilansPlus

BilansPlus is a local cloud engineering project that simulates an accounting document processing platform using AWS-style services through LocalStack.
The system is designed around a fictional accounting workflow where businesses upload financial documents, the platform stores them, queues them for processing, classifies them by document type, suggests relevant accounting kontos, stores metadata, and keeps an audit trail.
The goal of this project is to demonstrate practical cloud engineering patterns in a safe local environment without using real AWS billing resources.

## What BilansPlus Simulates
BilansPlus represents a backend system for accounting agencies and small businesses that need to process documents such as:
- supplier invoices
- receipts
- bank statements
- payment confirmations
- accounting reports
- tax-related documents
The platform focuses on the lifecycle of an accounting document from upload to processing status.

## Core Architecture
The project uses a local AWS simulation powered by LocalStack.
Planned AWS-style services include:
- Amazon S3 for storing raw and processed documents
- Amazon SQS for queue-based document processing
- AWS Lambda for serverless document processing logic
- Amazon DynamoDB for storing document metadata and konto suggestions
- IAM-style permissions for service access modeling
- Terraform for infrastructure as code

## Project Structure

BilansPlus/

│

├── docs/

├── infra/

├── services/

├── config/

├── scripts/

├── samples/

└── tests/

## Folder Overview

### docs/
Contains project documentation, including the business overview, architecture explanation, event flow, security model, and operational runbook.

### infra/
Contains infrastructure code. The Terraform configuration will define the local AWS resources used by the project, including S3 buckets, SQS queues, DynamoDB tables, Lambda functions, and IAM roles.

### services/
Contains the application services that make up BilansPlus.

Planned services include:
* `document-intake` for handling document uploads
* `document-processor` for processing queued accounting documents
* `konto-classifier` for suggesting accounting kontos
* `status-api` for checking document processing status

### config/
Contains business configuration files such as konto mappings, supported document types, and classification rules.

### scripts/
Contains automation scripts for local setup, infrastructure deployment, cleanup, Lambda packaging, and smoke testing.

### samples/
Contains realistic sample accounting documents used for local demonstrations and end-to-end testing.

### tests/
Contains unit, integration, and end-to-end tests for validating the system.

## Intended Document Flow
Document upload
    ↓
S3 raw document storage
    ↓
SQS processing queue
    ↓
Lambda document processor
    ↓
Konto classification
    ↓
DynamoDB metadata storage
    ↓
Audit event logging
    ↓
Document status available for review

## Purpose of the Project
BilansPlus is built as a portfolio-grade cloud engineering project. It is intended to show practical knowledge of:
* local AWS development with LocalStack
* infrastructure as code with Terraform
* event-driven architecture
* queue-based processing
* serverless application design
* cloud storage patterns
* NoSQL metadata storage
* automation scripting
* clean project documentation

====================================

This project is designed to run locally with Docker, LocalStack, AWS CLI, and Terraform.
No real AWS resources are required for local development or were hurt in the making of this git repo.
