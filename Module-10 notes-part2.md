**Module 10  Lesson 6: Auditing AWS Resources for Compliance**
AWS Config

AWS Config is a service used to assess, audit, and evaluate the configurations of AWS resources.

It continuously monitors resource configurations and compares them against desired settings or company standards.

Benefits
Evaluates resource configurations against desired state
Tracks configuration changes over time
Simplifies troubleshooting
Helps identify non-compliant resources
Supports security monitoring
Use Cases
Continuous compliance auditing
Security monitoring and analysis
Change management
Operational troubleshooting
Example

A company only allows approved EC2 instance types.

AWS Config continuously checks resources and identifies any EC2 instances that violate company standards.

AWS Audit Manager

AWS Audit Manager helps automate risk and compliance assessments.

It continuously audits AWS usage and automatically collects evidence needed for audits.

Benefits
Automated evidence collection
Saves audit preparation time
Simplifies collaboration between teams
Maintains audit integrity using read-only evidence
Use Cases
Compliance assessments
Internal audits
Risk management
Automated evidence collection
Example

Instead of manually collecting screenshots and reports for audits, Audit Manager automatically gathers evidence from AWS services.

Quick Revision
AWS Config

Purpose:
Evaluate and audit AWS resource configurations.

Keywords:
Configuration Monitoring
Compliance Checking
Change Tracking

AWS Audit Manager

Purpose:
Automate audit evidence collection and compliance assessments.

Keywords:
Audit Automation
Evidence Collection
Risk Assessment

**Lesson 7: AWS Organizations**
What is AWS Organizations?

AWS Organizations is an account management service used to centrally manage multiple AWS accounts.

It helps organizations:

Manage accounts centrally
Consolidate billing
Control security policies
Simplify governance
Share resources
Benefits
Centralized Management

Manage multiple AWS accounts from one location.

Consolidated Billing

All account charges roll up into a management account.

Simplified Governance

Apply organization-wide policies.

Improved Security

Control which services and actions accounts can access.

Scalability

Programmatically create new AWS accounts.

Key Concepts
Management Account

Main parent account that controls the organization.

Member Accounts

Child accounts managed by the organization.

Organizational Units (OUs)

Logical groupings of AWS accounts.

Examples:
Production OU
Development OU
Security OU
Service Control Policies (SCPs)

SCPs define the maximum permissions available to AWS accounts.
SCPs can be applied to:

Root
Organizational Units (OUs)
Individual Member Accounts

SCPs affect:
IAM Users
IAM Groups
IAM Roles
Root User inside member accounts
Important

SCPs do NOT grant permissions.

They only define permission boundaries.

Use Cases
Automating account creation
Managing multiple teams
Security governance
Resource sharing
Compliance management
Quick Revision
AWS Organizations
<img width="1680" height="838" alt="image" src="https://github.com/user-attachments/assets/48b693b6-cf79-4b09-be50-c7463252ce22" />

Purpose:
Manage multiple AWS accounts centrally.

Organizational Unit (OU)

Logical grouping of AWS accounts.

SCP

Defines maximum permissions allowed within accounts.

**Lesson 8: Governance**

Governance ensures AWS environments follow organizational rules, standards, and best practices.

AWS provides three major governance services:

AWS Control Tower
AWS Service Catalog
AWS License Manager
AWS Control Tower

AWS Control Tower helps set up and govern secure, compliant multi-account AWS environments.

It automates account setup using AWS best practices.

Benefits
Automated account provisioning
Built-in governance
Security guardrails
Compliance monitoring
Faster multi-account setup
Key Features
Landing Zone

Pre-configured multi-account environment.

Guardrails

Rules that enforce security and compliance standards.

Dashboard

Provides visibility into accounts and compliance status.

Use Cases
Multi-account governance
Secure account provisioning
Compliance enforcement
Enterprise AWS environments
AWS Service Catalog

AWS Service Catalog allows organizations to create and manage approved catalogs of AWS resources.

Employees can deploy only approved resources.

Benefits
Faster resource deployment
Improved governance
Standardized resource configurations
Reduced configuration mistakes
Use Cases
Approved resource catalogs
Standardized deployments
CI/CD resource provisioning
Access-controlled deployments
AWS License Manager

AWS License Manager helps manage software licenses in AWS.

Supports Bring Your Own License (BYOL) models.
Benefits
License tracking
Cost optimization
License compliance
Centralized management
Use Cases
Microsoft license management
BYOL environments
License auditing
Software entitlement distribution
Quick Revision
AWS Control Tower

Purpose:
Govern and automate secure multi-account environments.

AWS Service Catalog

Purpose:
Deploy approved AWS resources through a catalog.

AWS License Manager

Purpose:
Manage and track software licenses.

**Lesson 9: AWS Health**
What is AWS Health?

AWS Health provides information about events and changes that may impact AWS resources.

It delivers personalized notifications for your AWS environment.

AWS Health Dashboard

Provides account-specific health information.

Displays:
Service events
Planned maintenance
Account notifications
Resource health events
Benefits
Real-time health visibility
Personalized notifications
Actionable guidance
Improved incident response
Use Cases
Troubleshooting incidents
Monitoring AWS service issues
Planning maintenance activities
Managing lifecycle events
Quick Revision
AWS Health

Purpose:
Monitor AWS service events affecting your resources.

AWS Health Dashboard

Provides:
Account-specific health and event information.

**Lesson 10: AWS Trusted Advisor**
What is AWS Trusted Advisor?

AWS Trusted Advisor continuously evaluates AWS resources against AWS best practices.

It provides recommendations to improve:

Cost Optimization
Performance
Security
Fault Tolerance
Service Limits
Trusted Advisor Categories
Cost Optimization
<img width="1680" height="504" alt="image" src="https://github.com/user-attachments/assets/de557c57-5f87-4af3-bde9-471780008827" />

Identifies unused or underutilized resources.

Examples:

Idle EC2 instances
Unused EBS volumes
Idle RDS databases
Performance

Improves resource performance.

Examples:

EBS throughput optimization
Resource utilization improvements
Security

Identifies security risks.

Examples:

Open security groups
Missing MFA
Security vulnerabilities
Fault Tolerance

Improves availability and resilience.

Examples:

Missing backups
Poor Multi-AZ deployment
Missing snapshots
Service Limits

Monitors AWS service quotas.

Provides alerts when approaching limits.

Benefits
Aligns resources with AWS best practices
Improves security
Reduces costs
Improves reliability
Enhances performance
IAM Access Analyzer

IAM Access Analyzer helps organizations achieve Least Privilege Access.

It analyzes permissions and identifies unintended access.

Benefits
Permission validation
Access verification
Security improvement
Policy refinement
Use Cases
Permission auditing
Removing excessive permissions
Least privilege implementation
IAM policy reviews
Quick Revision
AWS Trusted Advisor

Purpose:
Optimize AWS environments using AWS best practices.

Checks:

Cost
Security
Performance
Fault Tolerance
Service Limits
IAM Access Analyzer

Purpose:
Analyze permissions and achieve least privilege access.
