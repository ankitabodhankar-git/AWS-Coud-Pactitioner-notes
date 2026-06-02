# Module 2 — Compute in the Cloud ☁️

## MODULE 2 INTRODUCTION

### Introduction to Amazon EC2

Amazon EC2 (Elastic Compute Cloud) is a web service that provides secure, resizable compute capacity in the cloud.

EC2 allows users to:

* Launch virtual servers
* Scale compute resources
* Run applications in the cloud
* Pay only for usage

EC2 instances can run:

* Linux
* Windows

AWS manages the infrastructure, while customers manage applications and configurations.

---

# COMPUTE IN THE CLOUD

# Amazon EC2 Instance Types

Amazon EC2 provides different instance types optimized for different workloads.

---

## General Purpose

Balanced compute, memory, and networking.

Good for:

* Web servers
* Small databases
* Development environments

---

## Compute Optimized

High-performance processors for compute-intensive workloads.

Good for:

* Gaming servers
* Scientific modeling
* Batch processing

---

## Memory Optimized

Fast performance for workloads processing large datasets in memory.

Good for:

* High-performance databases
* Real-time analytics

---

## Accelerated Computing

Uses hardware accelerators such as GPUs.

Good for:

* Machine learning
* Video rendering
* Graphics processing

---

# How to Provision AWS Resources

AWS resources are managed using APIs.

There are three main ways to interact with AWS services:

---

## AWS Management Console

Browser-based interface used to manage AWS services visually.

Used for:

* Learning AWS
* Monitoring resources
* Managing services visually

---

## AWS CLI

Command-line tool used to interact with AWS using commands.

Benefits:

* Automation
* Scripting
* Reduced manual errors

---

## AWS SDK

Allows developers to interact with AWS using programming languages such as:

* Python
* Java
* Node.js

---

# Shared Responsibility in Compute Services

AWS manages:

* Physical infrastructure
* Hardware
* Networking

Customers manage:

* Operating systems
* Applications
* Security configurations
* Data access permissions

---

# Demo: Launching an Amazon EC2 Instance

When launching an EC2 instance, users configure:

* Instance name
* Amazon Machine Image (AMI)
* Instance type
* Key pair
* Network settings
* Storage options

---

# Amazon Machine Image (AMI)

An AMI is a prebuilt template containing:

* Operating system
* Application software
* Configurations

AMIs help create consistent environments across multiple EC2 instances.

---

# Amazon EC2 Pricing

AWS provides multiple EC2 pricing options.

---

## On-Demand Instances

Pay only for usage with no long-term commitment.

Good for:

* Short-term workloads
* Testing environments

---

## Reserved Instances

Lower pricing for long-term workloads.

Good for:

* Predictable usage
* Long-running applications

---

## Spot Instances

Use unused EC2 capacity at lower prices.

Good for:

* Flexible workloads
* Batch jobs

---

## Savings Plans

Flexible pricing model with usage commitment.

---

## Dedicated Hosts

Physical servers dedicated to one customer.

Good for:

* Compliance requirements
* Licensing requirements

---

## Dedicated Instances

Instances running on dedicated hardware without full host control.

---

# AUTO SCALING AND LOAD BALANCING

# Scaling Amazon EC2

Scalability means increasing resources to handle growing workloads.

Elasticity means automatically adjusting resources based on demand.

---

# Types of Scaling

## Scaling Up

Increase power of existing instances.

---

## Scaling Out

Add more EC2 instances.

---

# Amazon EC2 Auto Scaling

Automatically adds or removes EC2 instances based on:

* Demand
* Performance metrics
* Application traffic

---

# Auto Scaling Group Settings

## Minimum Capacity

Minimum number of instances running.

---

## Desired Capacity

Target number of running instances.

---

## Maximum Capacity

Maximum number of instances allowed.

---

# Directing Traffic with Elastic Load Balancing

Elastic Load Balancing (ELB) distributes incoming traffic across multiple EC2 instances.

Benefits:

* High availability
* Improved performance
* Even traffic distribution

---

# Routing Methods

## Round Robin

Traffic distributed evenly across servers.

---

## Least Connections

Traffic sent to server with fewest active connections.

---

## IP Hash

Routes users based on IP address.

---

## Least Response Time

Traffic sent to fastest responding server.

---

# Amazon EC2 Auto Scaling and ELB

Auto Scaling adjusts the number of instances.

ELB distributes traffic evenly across instances.

---

# Messaging and Queuing

Messaging and queuing help applications communicate reliably.

---

# Tightly Coupled Architecture

Applications depend directly on each other.

Failure in one component affects others.

---

# Loosely Coupled Architecture

Applications communicate through queues.

If one component fails, others continue working.

---

# Amazon SQS

Amazon Simple Queue Service (Amazon SQS) stores messages between software components.

Benefits:

* Reliable communication
* Message buffering
* Decoupled architecture

---

# Amazon SNS

Amazon Simple Notification Service (Amazon SNS) uses publish-subscribe messaging.

SNS sends notifications through:

* SMS
* Email
* Push notifications

---

# EventBridge

Amazon EventBridge routes events between applications and AWS services.

Supports:

* Event-driven architectures
* Scalable communication

---

## Module Summary

Module 2 covered:

* Amazon EC2
* Instance types
* Provisioning AWS resources
* Amazon EC2 pricing
* Auto Scaling
* Elastic Load Balancing
* Messaging and queuing services
