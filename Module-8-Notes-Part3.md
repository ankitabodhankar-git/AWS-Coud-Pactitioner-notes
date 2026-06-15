# Module 8 – AI/ML and Data Analytics

# Lesson 6: Introduction to Data Analytics

## What is Data Analytics?

Data Analytics is the process of transforming raw historical data into valuable insights and trends.

Businesses use Data Analytics to:

- Understand past events
- Analyze customer behavior
- Improve business decisions
- Identify opportunities and risks

### Real-Life Examples

#### Loan Companies
Use analytics to explain why a loan was approved or rejected.

#### Medical Researchers
Analyze clinical trial results using hypothesis testing.

#### Insurance Companies
Use analytics to calculate risks and satisfy government regulations.

---

## What is a Data Lake?

A Data Lake is a central storage location that stores large amounts of raw data from multiple sources.

### Benefits

- Stores structured and unstructured data
- Scales easily
- Supports analytics and ML workloads
- Keeps all business data in one place

### AWS Service

**Amazon S3** is commonly used as a Data Lake.

---

## ETL Process

ETL stands for:

### Extract

Collect data from different sources.

Examples:

- Databases
- Applications
- APIs
- Sensors

### Transform

Convert data into a clean and consistent format.

Examples:

- Remove duplicates
- Fix errors
- Standardize formats

### Load

Load processed data into a destination system.

Examples:

- Data Warehouse
- Analytics Platform
- Reporting Tool

---

## ETL Example

### Online Shopping Company

#### Extract

Collect customer data from:

- Website
- Mobile App
- Payment Gateway

#### Transform

Convert data into a standard format.

#### Load

Store data into a data warehouse for reporting and analysis.

---

## ELT Process

ELT stands for:

- Extract
- Load
- Transform

In cloud environments, data is loaded first and transformed later when required.

---

## Zero-ETL

Sometimes data is already clean and usable.

In such situations ETL is not required.

This approach is called **Zero-ETL**.

---

## What are Data Pipelines?

A Data Pipeline is an automated process that moves data from source systems to destination systems.

Think of it as a factory assembly line for data.

### Benefits

- Automation
- Faster processing
- Reduced human errors
- Repeatable workflows
- Real-time data movement

---

# Lesson 7: Data Pipelines on AWS

## Purpose of Data Pipelines

Data Pipelines automate the collection, transformation, storage, and delivery of data.

Without Data Pipelines:

- Data movement is manual
- More errors occur
- Processing becomes slow

With Data Pipelines:

- Automated workflows
- Faster analytics
- Better scalability
- Improved reliability

---

## AWS Services Used in Data Pipelines

### Amazon Kinesis Data Streams

Used for real-time data ingestion.

Examples:

- Website clicks
- App activity
- IoT sensor data

---

### Amazon Data Firehose

Used to automatically deliver streaming data.

Benefits:

- Fully managed
- Auto scaling
- Near real-time delivery

Destinations include:

- Amazon S3
- Amazon Redshift
- Amazon OpenSearch

---

### AWS Lambda

Used to transform incoming data automatically.

Example:

JSON → CSV

---

### Amazon S3

Stores large amounts of raw and processed data.

Acts as a Data Lake.

---

### AWS Glue Data Catalog

Stores metadata about datasets.

Makes data discoverable and searchable.

---

### Amazon Athena

Runs SQL queries directly on data stored in Amazon S3.

No database servers are required.

Example:

```sql
SELECT * FROM customers;
```

---

### Amazon SageMaker AI

Uses stored data to build and train Machine Learning models.

Examples:

- Recommendation systems
- Forecasting
- Fraud detection

---

## Real-Life Data Pipeline Example

### E-Commerce Application

Customer data is stored in DynamoDB.

Pipeline Flow:

```text
DynamoDB
↓
Kinesis Data Streams
↓
Amazon Data Firehose
↓
AWS Lambda
↓
Amazon S3 Data Lake
↓
Glue Data Catalog
↓
Amazon Athena
↓
Amazon SageMaker AI
```

---

## Benefits

- Real-time processing
- Automation
- Reduced errors
- Supports analytics
- Supports Machine Learning
- Scales automatically

---

# Lesson 8: Data Analytics and AI/ML

## Scenario

An E-Commerce company wants to:

- Analyze customer behavior
- Train recommendation models
- Use the same data for analytics and ML

---

**Data analytics and AI/ML architecture diagram**

<img width="1680" height="1021" alt="image" src="https://github.com/user-attachments/assets/47a20ba9-c4dd-496d-a2b4-6f5465380de1" />

---

## Step-by-Step Process

### Step 1: Store Customer Data

Customer activities such as:

- Orders
- Searches
- Purchases

are stored in DynamoDB.

---

### Step 2: Stream Data

DynamoDB sends updates to Kinesis Data Streams.

---

### Step 3: Deliver Data

Amazon Data Firehose receives and delivers the data.

---

### Step 4: Transform Data

AWS Lambda converts data into the required format.

Example:

JSON → CSV

---

### Step 5: Store Data

Processed data is stored in Amazon S3.

S3 acts as the company's Data Lake.

---

### Step 6: Create Metadata

AWS Glue Data Catalog stores schema and metadata information.

---

### Step 7: Analyze Data

Amazon Athena runs SQL queries directly on S3 data.

Example:

```sql
SELECT * FROM customer_orders;
```

---

### Step 8: Train ML Models

Amazon SageMaker AI uses the data stored in S3 to train recommendation models.

Example:

Customer buys Coffee

↓

Recommend Muffin

---

## Real-Life Example

### Online Shopping Website

Customer buys:

- Laptop
- Mouse
- Keyboard

Pipeline:

```text
App
↓
DynamoDB
↓
Kinesis
↓
Firehose
↓
S3
↓
Athena + SageMaker
```

Results:

- Marketing Team analyzes sales trends.
- Data Scientists train recommendation models.
- Customers receive personalized recommendations.

---

# MCQ Questions

### What does ETL stand for?

✅ Extract, Transform, Load

### What is the purpose of Data Analytics?

✅ To uncover valuable insights and trends from historical data.

### Which AWS service is commonly used as a Data Lake?

✅ Amazon S3

### Which AWS service runs SQL queries directly on S3?

✅ Amazon Athena

### Which AWS service is used to build and train ML models?

✅ Amazon SageMaker AI




