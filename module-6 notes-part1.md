**Module 6 – Storage**
##Lesson 1 – Introduction to Storage

AWS provides storage services to store, access, manage, and back up data in the cloud. Instead of using physical storage hardware, AWS provides virtual storage solutions that can scale according to business needs.

AWS offers three main types of storage:

Block Storage
Object Storage
File Storage
Why Different Storage Types?

Just like a coffee shop stores different things in different places:

Coffee beans → Airtight containers
Paperwork → Filing cabinet
Secret recipes → Locked safe

Similarly, AWS uses different storage solutions for different types of data because not all data has the same requirements.

Block Storage

Block storage divides data into small pieces called blocks.

Each block can be updated independently without changing the entire file.

Because of this, block storage provides:

Fast access
Low latency
Efficient updates

Block storage is ideal for:

Applications
Databases
Frequent updates
Fast read/write operations
Features of Block Storage
Data stored in blocks
Individual blocks can be modified
Persistent storage
Low latency performance
Can be encrypted
Supports snapshots (backups)
AWS Block Storage Services
Amazon EC2 Instance Store
Unmanaged service
Non-persistent storage
High-performance storage
Directly attached to EC2 instances
Used for temporary data
Amazon Elastic Block Store (Amazon EBS)
Managed service
Persistent storage
Attached to EC2 instances
Multiple volume types
Suitable for different workloads
Object Storage

Object storage stores data as objects.

Each object contains:

Actual data
Unique identifier (ID)
Metadata

Metadata helps organize and retrieve data efficiently.

Unlike block storage, if any change is made, the entire object must be rewritten.

Object Storage Structure

Objects are stored in:

Buckets

Buckets use a flat structure rather than folders.

Best Use Cases

Object storage is ideal for:

Videos
Backups
Images
Logs
Files that do not change frequently
Benefits of Object Storage
Unlimited scalability
Efficient metadata management
Easy search and analytics
Store massive amounts of unstructured data
AWS Object Storage Service
Amazon Simple Storage Service (Amazon S3)

Amazon S3 is:

Fully managed
Scalable
Object storage service

Used for storing and retrieving any amount of data from anywhere.

File Storage

File storage uses a traditional hierarchical file system.

Files are organized using:

Folders
 └── Subfolders
      └── Files

File storage can be shared among multiple users and applications.

Benefits of File Storage
Shared access
Familiar folder structure
Works with most systems
Minimal code changes required
Best Use Cases

File storage is ideal for:

Shared documents
Content management systems
Team collaboration
Shared application data
AWS File Storage Services
Amazon Elastic File System (Amazon EFS)
Fully managed
Scalable
NFS file system
Works with AWS services and on-premises resources
Amazon FSx

Fully managed file storage service for:

Windows
Lustre
NetApp ONTAP
Additional Storage Services

Some AWS storage services do not fit directly into block, object, or file storage categories.

AWS Storage Gateway

AWS Storage Gateway is:

Fully managed
Hybrid cloud storage service

Provides on-premises access to virtually unlimited cloud storage.

AWS Elastic Disaster Recovery

AWS Elastic Disaster Recovery is:

Fully managed
Disaster recovery service

Used to recover:

Physical servers
Virtual servers
Cloud-based servers

into AWS.

AWS Shared Responsibility Model for Storage

AWS groups storage services into three categories:

Fully Managed
Managed
Unmanaged
Fully Managed Services

AWS manages:

Hardware
Infrastructure
Storage stack
Data durability
Availability
Encryption at rest
Replication

https://skillbuilder.aws/cds/2904c5c9-71cc-407b-bf8f-c0a68df3cc5d/assets/M06_02_10_persistence-InstanceStore_noprocess.png
Customer manages:

Data
Access controls
Service configuration

Customer responsibility is lowest.

Managed Services

AWS manages:

Storage infrastructure
Hardware redundancy
Volume replication

Customer manages:

Backup strategies
Encryption configuration
Performance optimization
Capacity planning

Customer responsibility is higher than fully managed services.

Unmanaged Services

AWS manages only:

Physical hardware
Network infrastructure

Customer manages:

Data
Backup and recovery
Encryption
Performance optimization
Durability

Customer responsibility is highest.

Storage Services Summary
Storage Type	AWS Service
Block Storage	EC2 Instance Store, Amazon EBS
Object Storage	Amazon S3
File Storage	Amazon EFS, Amazon FSx

Lesson 2 – EC2 Instance Store and Amazon Elastic Block Store (Amazon EBS)
Block Storage

When applications run on Amazon EC2, they need:

CPU
Memory
Network
Storage

Block storage stores data in blocks and allows only the required blocks to be updated instead of rewriting the entire file.

This makes block storage suitable for:

Databases
Enterprise applications
File systems
Amazon EC2 Instance Store

Amazon EC2 Instance Store is block-level storage physically attached to the EC2 host machine.

Depending on the EC2 instance type, instance store may be available as default storage.


Key Feature
No Data Persistence

If an EC2 instance is:

Stopped
Terminated

all data stored in the instance store is deleted.

This happens because when the instance starts again, it may run on a different physical host where the original storage does not exist.

Characteristics
Unmanaged storage
Temporary storage
High-performance storage
Physically attached to host
Non-persistent
Included with EC2 pricing
Benefits
Automatically Available Storage

Instance store may be available automatically depending on the instance type.

Cost Effective

No additional storage cost because it is included in the EC2 instance price.

High Performance

Provides very high I/O performance for temporary workloads.

Use Cases

Best for:

Buffers
Caches
Scratch data
Temporary processing data
Heavy calculations
Temporary data processing workloads

Not recommended for:

Databases
Long-term storage
Applications requiring data retention
Amazon Elastic Block Store (Amazon EBS)

Amazon EBS provides persistent block-level storage volumes for Amazon EC2 instances.

EBS volumes act like virtual hard drives that can be attached to EC2 instances.

Unlike instance store, EBS volumes are not tied directly to the physical host.

Key Feature
Data Persistence

If an EC2 instance is:

Stopped
Restarted
Terminated

the data stored in the EBS volume remains available.

Characteristics
Managed service
Persistent storage
Attached to EC2 instances
Low latency
Consistent performance
Multiple volume types available
EBS Volumes

To create an EBS volume:

Define volume size
Select volume type
Configure settings
Create volume
Attach volume to EC2 instance

Applications can then store data on the EBS volume.

EBS Snapshots

Because EBS volumes store important data, AWS recommends creating:

Amazon EBS Snapshots

Snapshots are incremental backups of EBS volumes.

Used for:

Backup
Recovery
Disaster recovery
Data protection
Performance

EBS performance is measured using:

IOPS
Input/Output Operations Per Second

Higher IOPS means higher storage performance.

Benefits
Persistent Storage

Data remains available even if the EC2 instance stops.

Data Portability

Volumes can be:

Detached
Reattached

to different EC2 instances.

Backup Support

Supports snapshots for backup and recovery.

Flexible Configuration

Different volume types available for different workloads.

Use Cases
Database Hosting

Provides consistent and low-latency storage for databases.

Backup Storage

Stores important application data.

Development Environments

Supports rapid deployment using snapshots.

Data Portability Use Cases
Data Migration

Move storage between instances.

Instance Type Changes

Detach volume from one instance and attach it to another.

Disaster Recovery

Recover data from snapshots and reattach volumes.

Cost Optimization

Move storage resources based on requirements.

Performance Tuning


MCQ Answers
Q1

A developer needs high I/O performance and does not need to retain data long-term.

✅ Answer:

EC2 instance store provides high I/O performance for temporary storage needs.

Q2

Why is Amazon EBS suitable for storing financial application data?

✅ Answer:

Amazon EBS provides high availability and durability by automatically replicating volumes within the same Availability Zone.

Q3

How does Amazon EBS solve data persistence issues?

✅ Answer:

Amazon EBS volumes exist independently from the instance and persist even after the instance is terminated.


Lesson 3 – Amazon Elastic Block Store (Amazon EBS) Data Lifecycle

Amazon EBS Data Lifecycle refers to the process of managing EBS volumes throughout their lifecycle, including:

Creating volumes
Backing up volumes
Managing snapshots
Restoring data
Deleting unused resources

As part of the AWS Shared Responsibility Model, customers are responsible for managing their own data and backup strategy.

Amazon EBS Snapshots

An EBS Snapshot is a point-in-time backup of an EBS volume.

A point-in-time backup means the data is captured exactly as it exists at a specific moment.

Snapshots can be created:

Daily
Weekly
Monthly

depending on business requirements.

Incremental Snapshots

EBS Snapshots are incremental.

First Snapshot

The first snapshot copies all data from the volume.

Subsequent Snapshots

Only blocks that changed since the previous snapshot are copied.

Example:

Monday Snapshot
→ Full Backup

Tuesday Snapshot
→ Only Changed Data

Wednesday Snapshot
→ Only New Changes

This makes snapshots:

Faster
More storage efficient
More cost effective
Where are Snapshots Stored?

EBS Snapshots are stored in:

Amazon S3

AWS stores snapshots redundantly across multiple Availability Zones to improve durability and availability.

Uses of EBS Snapshots
Disaster Recovery

Restore data if a volume is lost or corrupted.

Data Migration

Move data between environments.

Volume Resizing

Create larger volumes using snapshots.

Production Backups

Maintain consistent backups of critical workloads.

Environment Cloning

Create identical copies of production environments for testing.

Creating New Volumes from Snapshots

A snapshot can be used to create:

One volume
Multiple volumes

Any new volume created from a snapshot is an exact copy of the original volume at the time the snapshot was taken.

Customer Responsibilities

Under the Shared Responsibility Model, customers are responsible for:

Scheduling snapshots
Managing backups
Monitoring snapshot costs
Deleting unnecessary snapshots
Encrypting sensitive data
Testing recovery procedures
Verifying snapshot integrity

AWS provides the service, but customers manage the backup strategy.

Benefits of EBS Snapshots
Data Protection and Recovery

Protects important data and enables recovery when needed.

Operational Flexibility

Allows easy creation of test, development, and recovery environments.

Cost Effective

Because snapshots are incremental, only changed blocks are stored, reducing storage costs.

Amazon Data Lifecycle Manager (DLM)

Amazon Data Lifecycle Manager is a fully managed service that automates EBS snapshot management.

Instead of manually creating snapshots, organizations can define policies and let AWS automate the process.

What Data Lifecycle Manager Can Do
Automate Snapshot Creation

Create snapshots automatically based on schedules.

Retention Management

Keep snapshots only for a specified period.

Automatic Deletion

Remove outdated snapshots automatically.

Lifecycle Management

Manage the entire backup lifecycle.

Consistent Policies

Apply the same backup rules across an organization.

Why Use Data Lifecycle Manager?

Without automation:

Admin
   ↓
Login Every Week
   ↓
Create Snapshots Manually

With Data Lifecycle Manager:

Create Policy Once
          ↓
AWS Automatically Creates
Retains
Deletes Snapshots

This reduces:

Manual effort
Human error
Administrative workload
Benefits of Amazon Data Lifecycle Manager
Automation

Eliminates manual snapshot creation.

Cost Control

Automatically deletes outdated backups.

Compliance Support

Maintains retention requirements.

Scalability

Useful for thousands of EBS volumes.

Performance Optimization

Can schedule backups during off-peak hours.

Steps to Create a Snapshot Policy
Step 1
Create an EBS snapshots policy using the Amazon EC2 console, API calls, AWS Command Line Interface (AWS CLI), SDKs, or AWS CloudFormation.

Step 2
Select target resource type
Choose either an EBS volume or an EC2 instance as the target for the snapshot.

Step 3
Exclude volumes
Narrow down the data to be included in the snapshot by choosing options to exclude either the root volume or data volumes.

Step 4
Set custom schedules
Automate the creation, retention, and deletion of EBS snapshots by setting up custom schedules.

Step 5
Apply additional actions
Before finalizing the policy, you can apply additional actions. These include configuring elements of the snapshots like tags, snapshot archiving, Amazon EBS fast snapshot restore, cross-Region copying, and cross-account sharing.


MCQ Answers
Q1

What is the most significant benefit of using EBS snapshots for creating test environments?

✅ EBS snapshots enable rapid creation of new volumes from existing data, so you can quickly deploy identical test environments that mirror production.

Q2

What problem does AWS Data Lifecycle Manager primarily solve?

✅ Automating the creation, retention, and deletion of EBS snapshots and EBS-backed Amazon Machine Images (AMIs) according to a schedule.
