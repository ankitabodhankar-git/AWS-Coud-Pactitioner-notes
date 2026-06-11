Module 6 – Storage
// Lesson 7 – Amazon Elastic File System (EFS)

Amazon Elastic File System (EFS) is a fully managed file storage service that provides a shared file system for AWS applications. It uses the Linux Network File System (NFS) protocol and allows multiple EC2 instances to access the same files simultaneously.

Unlike EBS, which is attached to a single EC2 instance, EFS can be mounted by multiple EC2 instances across multiple Availability Zones. AWS automatically handles scaling, replication, and maintenance, so users do not need to manage storage capacity manually.

EFS is ideal for applications that require shared access to files, such as content management systems, web servers, development environments, analytics workloads, and media applications.

Benefits of Amazon EFS

Shared Access
Multiple EC2 instances can access the same files at the same time.

Elastic Storage
Storage automatically grows and shrinks as files are added or removed.

Multi-AZ Redundancy
Data is stored across multiple Availability Zones for high availability and durability.

EFS Storage Classes

EFS Standard
Used for frequently accessed files and provides the highest availability.

EFS Standard-IA
Used for infrequently accessed files at a lower cost.

EFS Archive
Used for files rarely accessed and provides the lowest storage cost.

EFS Lifecycle Policies

AWS automatically moves files between storage classes based on usage.

Not accessed for 30 days → Move to IA
Not accessed for 90 days → Move to Archive
Can optionally move files back to Standard when accessed
Real-Life Example

A company has multiple web servers serving the same website. All servers need access to common images, videos, and documents. Instead of storing copies on each server, all servers use a shared EFS file system.

Quick Revision
Shared File Storage
Multiple EC2 Access
Auto Scaling
Multi-AZ
Best for Shared Data
Lesson 8 – Amazon FSx

Amazon FSx is a fully managed file storage service that supports popular enterprise file systems. While EFS mainly supports Linux NFS, FSx supports multiple file systems such as Windows File Server, NetApp ONTAP, OpenZFS, and Lustre.

AWS manages infrastructure, patching, backups, and scaling, making it easier to run enterprise workloads.

Benefits of Amazon FSx

File System Integration
Works with existing applications and tools.

Managed Infrastructure
AWS handles maintenance and backups.

Scalable Storage
Storage can grow as needed.

Cost Effective
Pay only for the resources used.

Types of Amazon FSx
FSx for Windows File Server

Provides Windows-based shared storage.

Use Cases:

Windows File Servers
Active Directory Integration
SQL Server Workloads
Virtual Desktops
FSx for NetApp ONTAP

Provides enterprise storage features from NetApp.

Use Cases:

Data Management
Business Continuity
Workload Migration
FSx for OpenZFS

Provides NFS-based storage.

Use Cases:

Analytics
Content Management
Development & Testing
FSx for Lustre

Provides extremely high-performance storage.

Use Cases:

Machine Learning
High Performance Computing
Big Data Analytics
Real-Life Example

// A company running Windows applications and Active Directory wants cloud storage that works exactly like its existing Windows file servers. FSx for Windows File Server is the best solution.

Quick Revision
Enterprise File Storage
Supports Multiple File Systems
Windows, NetApp, OpenZFS, Lustre
AWS Managed Service


// Lesson 9 – AWS Storage Gateway

AWS Storage Gateway is a hybrid cloud storage service that connects on-premises environments with AWS Cloud storage.

It helps companies continue using existing infrastructure while benefiting from cloud storage.

Storage Gateway acts as a bridge between local storage and AWS storage services.

Benefits

Seamless Integration
Works with existing applications.

Improved Data Management
Simplifies backups and storage.

Local Caching
Frequently used data remains local.

Cost Optimization
Reduces expensive on-premises storage requirements.

Types of Storage Gateway
S3 File Gateway

Provides file access to Amazon S3 using NFS or SMB protocols.

Files are stored in Amazon S3 while frequently used data remains cached locally.

Use Cases:

File Backup
Cloud File Storage
File Sharing
Volume Gateway

Provides block storage.

Two modes:

Cached Volume Mode

Data stored in AWS
Frequently used data cached locally

Stored Volume Mode

Data stored locally
Backed up to AWS as EBS Snapshots
Tape Gateway

Replaces physical tape backup systems with virtual tapes stored in AWS.

Use Cases:

Backup
Long-Term Archiving
Compliance
Real-Life Example

A company wants to store files in AWS but still access them quickly from its office. S3 File Gateway keeps frequently used files cached locally while storing everything in S3.

Quick Revision
Hybrid Storage Service
Connects On-Premises + AWS
S3 File Gateway
Volume Gateway
Tape Gateway

// Lesson 10 – AWS Elastic Disaster Recovery (DRS)

AWS Elastic Disaster Recovery helps protect critical servers and applications from disasters and outages.

It continuously replicates server data into AWS so that workloads can be recovered quickly if failures occur.

Instead of maintaining a secondary data center, companies can use AWS as their disaster recovery site.

Benefits

Business Resilience
Applications remain available during outages.

Streamlined Recovery
Recovery processes are automated.

Cost Optimization
No need for expensive backup data centers.

How It Works

Elastic Disaster Recovery uses continuous block-level replication.

All server data is continuously copied into AWS.

If a disaster occurs:

Original server fails.
Recovery instance launches in AWS.
Business operations continue.
Real-Life Example

A bank continuously replicates transaction servers to AWS. If its primary data center fails, AWS launches recovery servers immediately.

Quick Revision
Disaster Recovery Service
Continuous Replication
Fast Recovery
Protects Critical Servers
Reduces Downtime

// Lesson 11 – Comparing Storage Services

This lesson compares S3, EBS, and EFS and explains when to use each service.

Amazon S3

S3 provides Object Storage.

Best for:

Websites
Images
Videos
Backups
Logs

Advantages:

Unlimited Scalability
Low Cost
High Durability
Amazon EBS

EBS provides Block Storage.

Best for:

Databases
EC2 Applications
Operating Systems

Advantages:

High Performance
Low Latency
Persistent Storage
Amazon EFS

EFS provides Shared File Storage.

Best for:

Shared Files
Team Collaboration
Media Applications
Multiple EC2 Instances

Advantages:

Shared Access
Automatic Scaling
Multi-AZ Support
Real-Life Comparison

Website Files
(HTML, CSS, Images)

→ Use S3

Database Storage

→ Use EBS

Shared Company Files

→ Use EFS

