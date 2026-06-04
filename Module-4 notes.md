# Module 4 — Going Global ☁️

## MODULE 4 INTRODUCTION

# Introduction to Going Global

AWS Global Infrastructure helps businesses deploy applications around the world while maintaining:

* High Availability
* Scalability
* Agility
* Elasticity
* Low Latency

This module focuses on:

* AWS Regions
* Availability Zones (AZs)
* Edge Locations
* Infrastructure as Code (IaC)
* AWS CloudFormation

---

# Coffee Shop Analogy

The coffee shop is expanding internationally.

AWS compares global expansion to:

| Coffee Shop                 | AWS                  |
| --------------------------- | -------------------- |
| New coffee shop locations   | AWS Regions          |
| Coffee carts near customers | Edge Locations       |
| Same recipes everywhere     | CloudFormation & IaC |

---

# Going Global with AWS Infrastructure

When expanding globally, businesses must consider:

* Customer demand
* Performance
* Regulations
* Costs
* Reliability

AWS provides global infrastructure to support worldwide deployments.

---

# Choosing AWS Regions

An AWS Region is a physical location containing multiple Availability Zones.

Important Security Concept:

Each AWS Region is isolated from other Regions.

Data does not leave a Region unless you explicitly allow it.

---

# Key considerations when choosing Regions
<img width="1680" height="532" alt="image" src="https://github.com/user-attachments/assets/49404681-d8b5-4985-b7e6-32e61bd54d9a" />


## 1. Compliance

Compliance requirements must be considered first.

Some businesses must keep data within specific geographic boundaries.

Examples:

* Financial data in Germany may need to remain in Germany.
* Government workloads may require specific Regions.

If compliance requires a specific country, that requirement becomes the highest priority.

---

## GDPR Example

GDPR (General Data Protection Regulation) protects personal data and privacy of individuals in the European Union.

Organizations operating in the EU must:

* Protect customer data
* Obtain consent for data collection
* Allow data access and deletion

---

## 2. Proximity

Choose Regions close to users.

Benefits:

* Lower latency
* Faster application response
* Better customer experience

Example:

If most customers are in Singapore, deploying resources in Singapore usually provides better performance than deploying in Virginia.

---

## 3. Feature Availability

Not every AWS service or feature is available in every Region.

AWS continuously expands services across Regions.

Before selecting a Region, verify that required services are available there.

---

## AWS GovCloud Example

AWS GovCloud Regions are designed specifically for:

* US government agencies
* Government contractors

They provide additional compliance and security controls.

These capabilities are available only in specific Regions.

---

## 4. Pricing

Pricing varies by Region.

Factors affecting cost:

* Energy costs
* Local taxes
* Operational expenses
* Regulatory requirements

Some Regions may be more cost-effective than others.

---

# AWS Global Infrastructure

AWS Global Infrastructure consists of:

* Regions
* Availability Zones
* Edge Locations

Each component serves a different purpose.

---

# Availability Zones (AZs)

Availability Zones are separate locations inside a Region.

Each AZ contains:

* One or more data centers
* Independent power
* Independent networking

AZs are designed to be isolated from failures in other AZs.

---

# Multi-AZ Architecture

Resources are deployed across multiple Availability Zones.

Benefits:

* High availability
* Fault tolerance
* Disaster recovery
* Business continuity

If one AZ experiences an outage, traffic can fail over to another AZ.

Customers may not even notice the interruption.

---

# Multi-Region Architecture

Applications can also be deployed across multiple Regions.

Benefits:

* Regional disaster recovery
* Increased availability
* Global resilience

If an entire Region becomes unavailable, applications can fail over to another Region.

---

# Benefits of AWS Global Infrastructure

## High Availability

Systems remain operational even when failures occur.

Applications continue serving users with minimal downtime.

---

## Agility

Ability to quickly adapt to changing business needs.

AWS allows rapid deployment and modification of services.

---

## Elasticity

Ability to scale resources up or down automatically based on demand.

Resources increase during peak demand and decrease when demand drops.

---

# Edge Locations

Edge locations are smaller AWS facilities located closer to users.

Purpose:

Deliver content with lower latency.

---

# What Edge Locations Cache

* Images
* Videos
* Applications
* Static content
* Website assets

---

# Benefits of Edge Locations

* Faster content delivery
* Reduced latency
* Better user experience

---

# Amazon CloudFront

Amazon CloudFront is a Content Delivery Network (CDN).

CloudFront uses edge locations to deliver content closer to users.

Examples:

* Images
* Videos
* APIs
* Websites

---

# Amazon Route 53

Amazon Route 53 is AWS's DNS service.

DNS converts:

Human-readable domain names

Example:

```text
www.example.com
```

into

Machine-readable IP addresses.

Example:

```text
192.168.1.1
```

---

# AWS Outposts

AWS Outposts extends AWS infrastructure to on-premises environments.

Benefits:

* Hybrid cloud deployments
* Low latency
* Local AWS services
* Consistent AWS experience

---

# Infrastructure and Automation

Managing resources manually becomes difficult when deploying across:

* Multiple Regions
* Multiple accounts
* Multiple environments

Automation solves this problem.

---

# Infrastructure as Code (IaC)

Infrastructure as Code allows infrastructure to be defined using code files.

Infrastructure becomes:

* Repeatable
* Consistent
* Automated

Benefits:

* Faster deployments
* Reduced human error
* Version control support
* Easier scaling

---

# AWS CloudFormation

AWS CloudFormation is AWS's Infrastructure as Code service.

CloudFormation uses templates to define AWS resources.

Templates act as blueprints for infrastructure.

---

# How CloudFormation Works

Step 1:
Create a CloudFormation template.

Step 2:
Define resources inside the template.

Examples:

* EC2 instances
* Load Balancers
* Auto Scaling Groups
* Networking resources

Step 3:
CloudFormation automatically provisions resources.

---

# Benefits of CloudFormation

* Automated deployments
* Consistent environments
* Repeatable infrastructure
* Reduced manual effort
* Reduced configuration mistakes

---

# Example

Without CloudFormation:

Manually create every resource in Region A and Region B.

With CloudFormation:

Use one template to create identical environments across Regions.

---

# Ways to Interact with AWS Resources

AWS resources are accessed through APIs.

Common methods:

## AWS Management Console

Browser-based graphical interface.

Good for:

* Learning AWS
* Manual resource management

---

## AWS CLI

Command-line interface.

Good for:

* Automation
* Scripting

---

## AWS SDKs

Programmatic access through languages like:

* Python
* Java
* Node.js

---

## CloudFormation

Infrastructure as Code approach.

Good for:

* Large deployments
* Consistent environments
* Multi-Region deployments


