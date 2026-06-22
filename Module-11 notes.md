**AWS Cloud Practitioner – Module 11: Pricing and Support**

**Lesson 1: Introduction to Pricing and Support**
AWS provides services to help customers understand pricing, manage cloud costs, receive technical support, and optimize spending. The main focus areas of this module are AWS Pricing, AWS Support, AWS Marketplace, AWS Partners, and Cost Optimization.

Key Areas
- AWS Pricing Concepts
- Billing and Cost Management Tools
- AWS Support Plans
- AWS Marketplace and AWS Partner Network (APN)
- Cost Optimization Strategies
<img width="1680" height="945" alt="image" src="https://github.com/user-attachments/assets/0ecd3b3b-6943-415d-ac2a-ed0c9ccdbfe7" />

---
**Lesson 2: AWS Pricing Concepts**

AWS follows a Pay-As-You-Go pricing model where customers pay only for the resources they use.

Three Core Pricing Principles
1. Pay As You Go

- Pay only for resources consumed.
- No upfront investment.
- Ideal for variable workloads.

2. Save When You Commit

- Commit for 1 or 3 years.
- Receive discounts through Savings Plans and Reserved Instances.
- Best for predictable workloads.

3. Pay Less By Using More

- Volume-based discounts.
- Higher usage leads to lower per-unit costs.

Main Cost Drivers

Compute
Examples:
- Amazon EC2
- AWS Lambda
- Amazon ECS

Cost depends on processing power and usage duration.
Storage
Examples:

- Amazon S3- Amazon EBS

Cost depends on amount of data stored and storage class used.
Data Transfer
- Inbound transfer is usually free.
- Outbound transfer is charged.
- More outbound traffic increases cost.
---

**Lesson 3: AWS Pricing and Billing Services**

AWS Organizations

Used for centralized management of multiple AWS accounts.

Features:

- Consolidated billing
- Account management
- Security policy management

Use Cases:

- Large organizations
- Multiple departments
- Centralized cost management

AWS Billing and Cost Management Dashboard

Provides:

- Current charges
- Usage reports
- Cost forecasts
- Invoice management

AWS Budgets

Allows custom budgets and alerts.

Use Cases:

- Monthly spending limits
- Cost notifications
- Usage monitoring

AWS Cost Explorer

Helps analyze and forecast AWS costs.

Features:

- Cost trends
- Forecasting
- Service-wise cost analysis

AWS Pricing Calculator

Used before deployment to estimate costs.

Use Cases:

- Budget planning
- Cost comparison
- Architecture estimation
<img width="1680" height="383" alt="image" src="https://github.com/user-attachments/assets/6d7b535b-269a-4423-a98a-f88b99636617" />

---

**Lesson 4: AWS Support Plans**

AWS offers different support levels depending on business requirements.

Basic Support

Included free with every AWS account.

Features:

- Documentation
- Whitepapers
- AWS re:Post
- Customer service
- Core Trusted Advisor checks

Developer Support

Includes:

- Email support
- Basic Support features

Response Time:

- 24 hours for guidance
- 12 hours for impaired systems

Business Support

Includes:

- Phone support
- Full Trusted Advisor checks

Response Time:

- 4 hours for impaired production systems
- 1 hour for production outages

Enterprise On-Ramp

Includes:

- Pool of Technical Account Managers (TAMs)
Enterprise Support

Highest support level.

Features:

- Dedicated TAM
- Full Trusted Advisor recommendations
- Architectural guidance

Technical Account Manager (TAM)

Provides:

- Architectural guidance
- Cost optimization recommendations
- AWS best practices
- Operational support

---

**Lesson 5: AWS Marketplace and AWS Partners**

AWS Marketplace

AWS Marketplace is a digital catalog of third-party software running on AWS.

Benefits:

- Faster deployment
- Reduced development effort
- Flexible pricing
- Consolidated billing

Available Solutions

SaaS Applications

- Project management tools
- Collaboration platforms
- Marketing solutions

AI and Machine Learning

- Prebuilt models
- NLP services
- Image recognition solutions

Data and Analytics

- Business Intelligence tools
- Reporting platforms
- Data integration tools

AWS Partner Network (APN)

A global community of AWS consulting and technology partners.

Benefits:

- Specialized solutions
- Funding programs
- Training opportunities
- Partner events and workshops

Exam Point

AWS Marketplace provides:

- SaaS Applications
- Data and Analytics Solutions

---

**Lesson 6: Cost Optimization**

Cost optimization focuses on reducing cloud spending while maintaining performance and reliability.

EC2 Optimization

Rightsizing

Select the correct instance size based on workload needs.

Tool:

- AWS Compute Optimizer

Spot Instances

Use unused AWS capacity.

Benefits:

- Up to 90% cost savings

Best For:

- Flexible workloads
- Batch processing

Auto Scaling

Automatically adjusts resources based on demand.

Benefits:

- Reduced costs
- Improved efficiency

Resource Cleanup

Remove:

- Unused EC2 instances
- Unused EBS volumes
- Old snapshots

---

RDS Optimization

Rightsizing

Choose appropriate database instance sizes.

Read Replicas

Scale read operations without upgrading primary databases.

Amazon ElastiCache

Stores frequently accessed data in memory.

Benefits:

- Reduced database load
- Better performance
<img width="1586" height="895" alt="image" src="https://github.com/user-attachments/assets/3a0da4f2-3879-4026-8455-42bf3e2df723" />

---

S3 Optimization

Storage Classes

Choose the appropriate storage class:

- S3 Standard
- S3 Intelligent-Tiering
- S3 Glacier

Data Compression

Compress files before storing them.

Benefits:

- Lower storage costs

Lifecycle Policies

Automatically:

- Move data to cheaper storage
- Delete outdated files

---

Network Optimization

Reduce Data Transfer

Minimize:

- Internet traffic
- Cross-Availability Zone traffic

Use VPC Endpoints

Benefits:
- Lower transfer costs
- Improved security
- Private AWS connectivity

---

Cost Optimization Best Practices
1. Monitor costs regularly.
2. Use AWS Budgets.
3. Analyze spending with Cost Explorer.
4. Enable Auto Scaling.
5. Use Spot Instances where possible.
6. Rightsize resources.
7. Remove unused resources.
8. Use S3 lifecycle policies.
9. Compress stored data.
10. Use VPC Endpoints when appropriate.

---
//Keyword :
AWS Budgets → Cost Alerts

AWS Cost Explorer → Cost Analysis

AWS Pricing Calculator → Cost Estimation

AWS Organizations → Multiple Accounts

Enterprise Support → Dedicated TAM

AWS Marketplace → Third-Party Software

Spot Instances → Up to 90% Discount

Compute + Storage + Data Transfer → Main Cost Drivers
