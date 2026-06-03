# Module 3 — Exploring Compute Services ☁️

## MODULE 3 INTRODUCTION

# Introduction to Serverless Computing

Serverless computing allows developers to run applications without managing the underlying infrastructure.

With serverless services:

* No server management is required
* AWS handles scaling
* AWS manages availability
* AWS manages maintenance
* Developers focus mainly on application code

AWS provides different compute service models:

* Unmanaged services
* Managed services
* Serverless services

---

# Unmanaged Services

Unmanaged services provide the highest level of control.

Example:

* Amazon EC2

With EC2:

* Customers manage operating systems
* Customers manage scaling
* Customers manage patching
* Customers manage applications

AWS only manages the physical infrastructure.

---

# Managed Services

Managed services reduce infrastructure management responsibilities.

AWS handles more operational tasks while customers focus mainly on configurations and applications.

Examples:

* Elastic Load Balancing (ELB)
* Amazon SNS
* Amazon SQS

---

# Serverless Services

Serverless services completely hide infrastructure management from users.

AWS manages:

* Provisioning
* Scaling
* High availability
* Maintenance

Customers mainly manage:

* Application code
* Permissions
* Business logic

---

# Shared Responsibility in Serverless Computing

AWS manages:

* Infrastructure
* Scaling
* Server availability
* Patching

Customers manage:

* Application code
* Data access permissions
* Security configurations

---

# AWS Lambda

AWS Lambda is a serverless compute service that runs code in response to events.

Lambda is also called:

* Function as a Service (FaaS)

With Lambda:

* No server provisioning required
* Automatic scaling
* High availability
* Pay only for compute usage

---

# How Lambda Works

Users:

1. Create a Lambda function
2. Upload code
3. Configure a trigger

The function runs automatically when the event occurs.
<img width="1680" height="571" alt="image" src="https://github.com/user-attachments/assets/e7347ef3-eade-49f1-ae7b-f35cc577775f" />


---

# Lambda Triggers

Triggers are events that start Lambda functions.

Examples:

* File upload to Amazon S3
* Message in Amazon SQS
* API request
* Real-time stream processing

---

# Lambda Features

## Automatic Scaling

Lambda automatically scales depending on the number of requests.

---

## High Availability

AWS manages infrastructure availability automatically.

---

## Pay-As-You-Go Pricing

Charges apply only for compute time used.

---

## Runtime Support

Lambda supports multiple runtimes:

* Python
* Java
* Node.js

Custom runtimes are also supported.

---

# Lambda Limitations

Maximum Lambda execution time:

* 15 minutes

Lambda is best for:

* Short-running
* Event-driven workloads

---

# Lambda Use Cases

* Real-time image processing
* Website request handling
* Data processing
* Expense report generation
* Event-driven workflows

---

# Lambda and SQS Workflow

Example workflow:

1. Message enters SQS queue
2. SQS triggers Lambda
3. Lambda processes the message
4. Logs stored in CloudWatch

---

# Containers and Orchestration on AWS

Containers package:

* Application code
* Dependencies
* Runtime
* Configuration

into a single portable unit.

Containers provide:

* Consistent environments
* Portability
* Faster deployments
* Better resource efficiency
<img width="1680" height="608" alt="image" src="https://github.com/user-attachments/assets/e0269656-4874-4815-a0f9-f6052307c89a" />

---

# Containers vs Virtual Machines

## Containers

* Lightweight
* Faster startup
* Share host operating system

---

## Virtual Machines (VMs)

* Run separate operating systems
* Use hypervisors
* Higher resource usage

---

# Benefits of Containers

* Consistent deployments
* Easier troubleshooting
* Portability across environments
* Efficient scaling

---

# Container Orchestration

Managing many containers manually becomes difficult.

Container orchestration services automate:

* Deployment
* Scaling
* Monitoring
* Recovery
* Updates

---

# Amazon ECS

Amazon Elastic Container Service (ECS) is a container orchestration service.

Used for:

* Running Docker containers
* Managing containerized applications

---

# Amazon ECS Launch Types

## ECS with EC2

Provides more infrastructure control.

Good for:

* Custom hardware requirements
* Advanced networking configurations

---

## ECS with Fargate

Serverless container hosting.

AWS manages servers automatically.

---

# Amazon EKS

Amazon Elastic Kubernetes Service (EKS) is a managed Kubernetes service.

Used for:

* Running Kubernetes workloads
* Large-scale container deployments

---

# Amazon EKS Launch Types

## EKS with EC2

Provides full infrastructure control.

---

## EKS with Fargate

Serverless Kubernetes deployment.

---

# Amazon ECR

Amazon Elastic Container Registry (ECR) stores container images.

Features:

* Store images securely
* Push and pull container images
* Supports OCI-compliant images

---

# AWS Fargate

AWS Fargate is a serverless compute engine for containers.

Works with:

* Amazon ECS
* Amazon EKS

Benefits:

* No server management
* Automatic infrastructure handling
* Pay only for resources used

---

# Additional Compute Services

AWS provides purpose-built compute services for specific use cases.

---

# AWS Elastic Beanstalk

Elastic Beanstalk simplifies application deployment.

Users upload:

* Application code
* Desired configuration

Elastic Beanstalk automatically manages:

* EC2 instances
* Load balancing
* Scaling
* Monitoring

---

# Elastic Beanstalk Use Cases

* Web applications
* REST APIs
* Backend services
* Microservices

---

# AWS Batch

AWS Batch manages batch computing workloads.

Automatically:

* Schedules jobs
* Scales resources
* Manages infrastructure

---

# AWS Batch Use Cases

* Scientific computing
* Big data processing
* Machine learning training
* Media transcoding

---

# Amazon Lightsail

Amazon Lightsail provides:

* Virtual private servers
* Storage
* Databases
* Networking

with simple pricing and setup.

---

# Lightsail Use Cases

* Blogs
* Small business websites
* Learning cloud services
* Low-traffic applications

---

# AWS Outposts

AWS Outposts extends AWS infrastructure to on-premises environments.

Provides:

* Hybrid cloud architecture
* Consistent AWS experience
* Local AWS services

---

# Outposts Use Cases

* Low-latency workloads
* Regulatory compliance
* Data residency requirements
* Hybrid cloud deployments

