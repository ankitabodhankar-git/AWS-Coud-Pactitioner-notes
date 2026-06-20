# Module 9: Security on AWS 

## Lesson 1: Introduction to Security on AWS

### Authentication and Authorization

Security starts with two important concepts:

#### Authentication

Authentication is the process of verifying the identity of a user or entity.

Examples:

* Username and password
* Multi-Factor Authentication (MFA)
* Security tokens

Example:
An employee logs into a company portal using a username and password.

#### Authorization

Authorization determines what actions a user is allowed to perform after authentication.

Example:
An employee can access their own records but cannot access records belonging to other employees.

### AWS Shared Responsibility Model

Cloud security is a shared responsibility between AWS and customers.

#### Customer Responsibility (Security IN the Cloud)

Customers are responsible for:

* Protecting data
* Managing applications
* Managing operating systems (for some services)
* Managing user access and permissions
* Configuring security settings

#### AWS Responsibility (Security OF the Cloud)
<img width="1299" height="456" alt="image" src="https://github.com/user-attachments/assets/dc92237f-c074-4833-93e7-0975d1360ff6" />

AWS is responsible for:

* Physical security of data centers
* Hardware infrastructure
* Networking infrastructure
* Virtualization layer
* AWS Regions and Availability Zones

### AWS Security Controls

AWS security controls help customers:

1. Prevent security incidents
2. Protect networks, applications, and data
3. Detect and respond to security incidents

---

## Lesson 2: Preventing Unauthorized Access

### AWS Identity and Access Management (IAM)

IAM is the primary AWS service used to control access to AWS resources.

IAM follows the Principle of Least Privilege:

Users should receive only the permissions required to perform their tasks.

### AWS Root User

The root user is the owner of the AWS account.

Best Practices:

* Use a strong password
* Enable MFA immediately
* Avoid using the root account for daily tasks

### Multi-Factor Authentication (MFA)

MFA requires two or more verification methods before access is granted.

Example:

* Password
* Authentication app code

Benefits:

* Increased security
* Reduced risk of unauthorized access

### IAM Users

IAM Users represent individual people or applications.

Characteristics:

* Have permanent credentials
* Start with no permissions
* Receive permissions through IAM policies

### IAM Groups

Groups are collections of IAM users.

Benefits:

* Easier permission management
* Permissions applied to the group automatically apply to all users

Example:

Developers Group

Permissions:

* EC2 access
* S3 access

### IAM Policies

Policies define permissions using JSON documents.

Policies specify:

* Effect (Allow or Deny)
* Action
* Resource

Example:

Allow a user to read an S3 bucket.

### IAM Roles

Roles provide temporary access permissions.

Characteristics:

* No username or password
* Temporary credentials
* Commonly used by AWS services

Use Cases:

* EC2 accessing S3
* Lambda accessing DynamoDB
* Cross-account access

### IAM Identity Center

IAM Identity Center provides centralized identity management and Single Sign-On (SSO).

Benefits:

* One login for multiple AWS accounts
* Centralized access management

### AWS Secrets Manager

Secrets Manager securely stores:

* Database credentials
* API keys
* Passwords
* Tokens

Benefits:

* Automatic rotation
* Secure storage
* Centralized management

### AWS Systems Manager

Systems Manager helps manage infrastructure at scale.

Capabilities:

* Patch management
* Configuration management
* Automation
* Resource monitoring

---

## Lesson 3: Protecting Networks and Applications

### Denial of Service (DoS)

A DoS attack attempts to overwhelm a system using a single source.

Result:

* Service becomes unavailable

### Distributed Denial of Service (DDoS)

A DDoS attack uses many compromised devices to flood a target system.

Result:

* Network congestion
* Application downtime

### Security Groups

Security Groups act as virtual firewalls for AWS resources.

Characteristics:

* Control inbound traffic
* Control outbound traffic
* Allow rules only

Example:

Allow:

* HTTP (80)
* HTTPS (443)

Block all other traffic.
<img width="1045" height="264" alt="image" src="https://github.com/user-attachments/assets/4a2dee88-571f-4aea-9190-ef051757a410" />
<img width="1045" height="378" alt="image" src="https://github.com/user-attachments/assets/b002ec66-b094-4607-acf5-b8fb2cba17ae" />

### Elastic Load Balancing (ELB)

ELB distributes traffic across multiple resources.

Benefits:

* High availability
* Better performance
* Protection against traffic spikes

### AWS Shield Standard

AWS Shield Standard provides automatic protection against common DDoS attacks.

Characteristics:

* Included at no additional cost
* Enabled automatically

### AWS Shield Advanced

Advanced DDoS protection service.

Benefits:

* Enhanced monitoring
* Detailed attack diagnostics
* Additional mitigation capabilities

### AWS WAF (Web Application Firewall)

AWS WAF protects web applications from common web attacks.

Examples:

* SQL Injection
* Cross-Site Scripting (XSS)
* Malicious bots

Features:

* Custom rules
* Managed rule sets
* Traffic filtering

---

## Lesson 4: Protecting Data

### Encryption

Encryption protects information by converting readable data into unreadable data.

Only users with the correct key can decrypt and access the information.

### Encryption at Rest

Data stored on disk is encrypted.

Examples:

* Amazon S3 objects
* EBS volumes
* DynamoDB tables

Benefits:

* Protects stored data
* Meets compliance requirements

### Encryption in Transit

Data moving across networks is encrypted.

Examples:

* Browser to website
* Application to database

Benefits:

* Prevents interception
* Protects sensitive information
<img width="1356" height="509" alt="image" src="https://github.com/user-attachments/assets/96f7c779-74c5-4cb9-8970-0f148cb91cf2" />

### AWS Key Management Service (AWS KMS)

AWS KMS manages encryption keys.

Capabilities:

* Create keys
* Manage keys
* Rotate keys
* Control access to keys

Benefits:

* Centralized key management
* Secure encryption operations

### Amazon Macie

Amazon Macie discovers and protects sensitive data stored in Amazon S3.

Uses:

* Machine Learning
* Pattern matching

Detects:

* Personal information
* Financial information
* Sensitive business data

Benefits:

* Improved visibility
* Compliance support

### AWS Certificate Manager (ACM)

ACM manages SSL/TLS certificates.

Purpose:

* Encrypt data in transit
* Secure websites and applications

Benefits:

* Automatic certificate renewal
* Simplified certificate management

### SSL and TLS

SSL and TLS are protocols used to secure communications.

Benefits:

* Data confidentiality
* Data integrity
* Authentication

Example:

HTTPS websites use SSL/TLS certificates.

---

## Lesson 5: Detecting and Responding to Security Incidents

### Amazon Inspector

Amazon Inspector performs automated security assessments.

Supported Resources:

* Amazon EC2
* Containers
* AWS Lambda

Checks:

* Vulnerabilities
* Security best practices
* Exposed resources

Output:

* Findings
* Severity levels
* Remediation recommendations

### Amazon GuardDuty

GuardDuty provides intelligent threat detection.

Continuously monitors:

* AWS accounts
* Network activity
* Resource activity

Detection Methods:

* Threat intelligence
* Machine learning
* Anomaly detection

Examples:

* Suspicious IP addresses
* Unauthorized activity
* Compromised credentials

### Amazon Detective

Detective helps investigate security incidents.

Features:

* Interactive visualizations
* Timeline analysis
* Root cause investigation

Benefits:

* Faster investigations
* Better understanding of threats

### AWS Security Hub

Security Hub provides a centralized security dashboard.

Capabilities:

* Aggregates findings from multiple services
* Security monitoring
* Compliance monitoring

Benefits:

* Single pane of glass
* Faster remediation
* Improved visibility

### Security Detection Workflow

1. Amazon Inspector identifies vulnerabilities
2. Amazon GuardDuty detects threats
3. Amazon Detective investigates root causes
4. AWS Security Hub aggregates findings

---

## Lesson 6: Additional Security Resources

### AWS Security Documentation

AWS provides several security resources:

#### Security, Identity, and Compliance on AWS

Provides information about AWS security services and compliance programs.

#### AWS Knowledge Center

Provides:

* Troubleshooting guides
* Frequently asked questions
* Best practices

#### AWS Security Documentation

Official documentation for AWS security services.

#### AWS Security Blog

Provides:

* Security updates
* Best practices
* Expert guidance

### AWS Marketplace Security Resources

AWS Marketplace contains third-party security products and services.

Categories include:

#### Threat Detection and Prevention

Tools that identify and block malicious activities.

#### Identity and Access Management

Tools for authentication and authorization.

#### Data Protection

Tools for encryption and safeguarding sensitive information.

#### Compliance and Governance

Tools that help organizations meet regulatory requirements.

---

# Quick Revision

### Authentication

Verifies identity.

### Authorization

Determines permissions.

### IAM

Controls access to AWS resources.

### MFA

Adds an extra security layer.

### Security Groups

Virtual firewalls for AWS resources.

### AWS Shield

Protects against DDoS attacks.

### AWS WAF

Protects web applications.

### Encryption at Rest

Protects stored data.

### Encryption in Transit

Protects moving data.

### AWS KMS

Manages encryption keys.

### Amazon Macie

Finds sensitive data in S3.

### AWS Certificate Manager

Manages SSL/TLS certificates.

### Amazon Inspector

Automated vulnerability assessments.

### Amazon GuardDuty

Threat detection service.

### Amazon Detective

Root cause investigation service.

### AWS Security Hub

Centralized security dashboard.

### AWS Shared Responsibility Model

Customer = Security IN the cloud.
AWS = Security OF the cloud.
