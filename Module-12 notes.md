# Module 12: Migrating to the AWS Cloud

## Lesson 1: Introduction to Migration

Cloud migration is the process of moving applications, databases, storage, and other IT resources from on-premises environments or another cloud provider to AWS. Migration is usually not a single event but an ongoing process that involves planning, execution, testing, and optimization.

Organizations migrate to AWS for several reasons, including cost reduction, scalability, improved reliability, enhanced security, and access to modern cloud services. Large migrations are typically completed in phases to reduce risk and maintain business continuity.

AWS organizes the migration journey into three major phases.

### Assess

The Assess phase focuses on understanding the organization's current environment and determining whether cloud migration is the right decision.

During this phase, organizations:

* Evaluate current infrastructure and workloads
* Identify business objectives and expected outcomes
* Analyze migration readiness
* Create a business case for cloud adoption
* Estimate costs and benefits

The goal is to understand the value of migration and build a clear migration strategy.

### Mobilize

The Mobilize phase focuses on preparation and planning.

Organizations:

* Build migration plans
* Identify application dependencies
* Close skill and process gaps
* Prepare teams and resources
* Select appropriate migration strategies

This phase ensures the organization is ready before workloads begin moving to AWS.

### Migrate and Modernize

This phase involves moving applications and data to AWS and validating that they function correctly.

Organizations:

* Migrate applications
* Validate migrated workloads
* Optimize applications for cloud environments
* Modernize architectures when needed
Migration is often iterative, with workloads moving in stages until the entire environment has been migrated successfully.
<img width="1680" height="683" alt="image" src="https://github.com/user-attachments/assets/94516ff4-2b5a-4906-9cc5-9153ed4b8ce1" />

---

## Lesson 2: AWS Cloud Adoption Framework (AWS CAF)

The AWS Cloud Adoption Framework (AWS CAF) provides guidance, best practices, and organizational structure to help companies successfully adopt cloud technologies.

Cloud migration affects many departments, not just technical teams. AWS CAF helps align business, technical, and operational stakeholders by organizing responsibilities into six perspectives.
<img width="1680" height="439" alt="image" src="https://github.com/user-attachments/assets/72f3ad75-5b50-4200-98c3-bd709244b148" />

### Business Perspective

The Business perspective ensures that cloud initiatives align with organizational goals and business outcomes.

Responsibilities include:

* Building business cases
* Aligning IT investments with business objectives
* Measuring business value
* Prioritizing cloud initiatives

Common stakeholders:

* Business managers
* Finance managers
* Budget owners
* Strategic planners

### People Perspective

The People perspective focuses on organizational readiness and workforce transformation.

Responsibilities include:

* Training employees
* Identifying skill gaps
* Workforce planning
* Managing organizational change

Common stakeholders:

* Human Resources
* Staffing teams
* Department managers

### Governance Perspective

The Governance perspective ensures cloud investments support business goals while maintaining compliance and risk management.

Responsibilities include:

* Portfolio management
* Risk assessment
* Performance measurement
* Policy development

Common stakeholders:

* CIOs
* Enterprise architects
* Program managers
* Business analysts

### Platform Perspective

The Platform perspective focuses on designing and implementing cloud infrastructure.

Responsibilities include:

* Cloud architecture
* Application migration
* Infrastructure design
* Platform modernization

Common stakeholders:

* Cloud architects
* Infrastructure engineers
* Solution architects

### Security Perspective

The Security perspective ensures workloads meet security and compliance requirements.

Responsibilities include:

* Security controls
* Identity management
* Auditing
* Monitoring and compliance

Common stakeholders:

* CISOs
* Security managers
* Security analysts

### Operations Perspective

The Operations perspective focuses on running and supporting cloud workloads.

Responsibilities include:

* Monitoring systems
* Incident management
* Disaster recovery
* Operational procedures

Common stakeholders:

* Operations managers
* IT support teams
* System administrators

AWS CAF helps organizations identify readiness gaps and create action plans for successful cloud adoption.

---

## Lesson 3: Seven Migration Strategies

AWS defines seven common migration approaches known as the Seven Rs.

### Rehost

Rehosting is commonly called Lift and Shift.

Applications are moved to AWS with minimal or no modifications.

Characteristics:

* Fastest migration approach
* Minimal changes required
* Lower initial effort
* Immediate cloud adoption
<img width="1680" height="657" alt="image" src="https://github.com/user-attachments/assets/c8357925-3d95-407f-bedd-97620a12bd11" />

Example:

Moving an on-premises server directly to an Amazon EC2 instance.

### Relocate

Relocation moves virtual machines or containers to AWS without redesigning applications.

Characteristics:

* Minimal changes
* Suitable for VMware environments
* Quick migration path

### Replatform

Replatforming is often called Lift, Tinker, and Shift.

Applications are migrated with small cloud optimizations but without changing the application's core architecture.

Characteristics:

* Limited modifications
* Better cloud benefits
* Faster than refactoring

Example:

Migrating a MySQL database to Amazon RDS without modifying application code.

### Refactor

Refactoring involves redesigning applications to take advantage of cloud-native services.

Characteristics:

* Significant code changes
* Improved scalability
* Enhanced performance
* Highest modernization benefits

Example:

Converting a monolithic application into microservices.

### Repurchase

Repurchasing replaces an existing application with a different cloud-based product.

Characteristics:

* Vendor replacement
* Software modernization
* New licensing model

Example:

Replacing an on-premises CRM with a SaaS solution from AWS Marketplace.

### Retain

Retention means keeping an application in its current environment.

Characteristics:

* No migration performed
* Temporary decision
* Used when migration is not yet justified

### Retire

Retiring involves shutting down applications that are no longer required.

Characteristics:

* Eliminates maintenance costs
* Reduces complexity
* Removes unused workloads

Organizations often discover many applications that can be retired during migration assessments.

---

## Lesson 4: Migration Services and Tools

AWS provides specialized tools to simplify cloud migration.

### Migration Evaluator

Migration Evaluator helps organizations create a data-driven business case for migration.

It analyzes existing infrastructure and estimates:

* Migration costs
* Potential savings
* Licensing opportunities
* Cloud readiness

Migration Evaluator is primarily used during the Assess phase.

### AWS Application Discovery Service

Application Discovery Service collects information about on-premises environments.

It gathers:

* Server inventory
* Performance metrics
* Application dependencies
* Network connections

This information helps organizations create detailed migration plans.

### AWS Migration Hub

Migration Hub serves as a central management console for migration activities.

Features include:

* Migration tracking
* Progress monitoring
* Team collaboration
* Planning and assessment tools

Migration Hub provides a single view of migration projects across AWS services.

### AWS Application Migration Service

Application Migration Service simplifies moving applications to AWS.

Features include:

* Automated replication
* Minimal downtime
* Continuous synchronization
* Application modernization support

It supports migrations from physical servers, virtual machines, and cloud environments.

### AWS Migration and Modernization Competency Partners

Organizations can work with AWS-certified partners that specialize in migration projects.

These partners provide:

* Technical expertise
* Planning assistance
* Migration execution
* Modernization support

---

## Lesson 5: Database Migrations

Database migration involves moving database workloads from one environment to another while maintaining data integrity and availability.

Database migrations can be categorized into two types.

### Homogeneous Migration

The source and target databases use the same database engine.

Example:

Oracle to Oracle or MySQL to MySQL.

These migrations are generally simpler because database structures remain unchanged.

### Heterogeneous Migration

The source and target databases use different database engines.

Example:

Oracle to Amazon Aurora PostgreSQL.

These migrations require schema conversion and application adjustments.

### AWS Database Migration Service (AWS DMS)

AWS DMS helps migrate databases securely with minimal downtime.

Capabilities include:

* Database migration
* Continuous replication
* Data warehouse migration
* Live database synchronization

DMS supports both homogeneous and heterogeneous migrations.

A key advantage is that source databases can remain operational during migration.

### AWS Schema Conversion Tool (AWS SCT)

AWS SCT helps convert database structures between different database engines.

It converts:

* Schemas
* Stored procedures
* Functions
* Views
* Database code

AWS SCT also identifies components requiring manual conversion and estimates migration effort.

Organizations frequently use AWS SCT together with AWS DMS during heterogeneous migrations.

---

## Lesson 6: Transferring Data Online

Many organizations move data to AWS using network-based transfers.

Online transfer methods are ideal when sufficient bandwidth is available.

### AWS DataSync

AWS DataSync automates and accelerates large-scale data transfers between on-premises storage and AWS.

Capabilities include:

* Data validation
* Encryption
* Scheduling
* Bandwidth control
* Reporting and monitoring

DataSync simplifies migration while maintaining security and reliability.

It is commonly used for:

* Data migration
* Archiving
* Hybrid cloud workflows
* Data replication

### AWS Transfer Family

AWS Transfer Family provides managed file transfer services.

Supported protocols include:

* FTP
* FTPS
* SFTP

The service integrates directly with:

* Amazon S3
* Amazon EFS

It simplifies secure file sharing with employees, customers, and business partners.

### AWS Direct Connect

AWS Direct Connect creates a dedicated private connection between an organization's network and AWS.

Benefits include:

* Higher bandwidth
* Lower latency
* Improved reliability
* Reduced network costs

Direct Connect is often used when large amounts of data must be transferred securely and consistently.

---

## Lesson 7: Transferring Data Offline

Some organizations cannot transfer large amounts of data online because of bandwidth limitations, remote locations, or extremely large datasets.

In these situations, AWS provides physical data transfer solutions.

### AWS Snowball Edge Storage Optimized Devices

AWS Snowball Edge devices are physical appliances designed for offline data transfer.

Organizations copy data onto the device and ship it directly to AWS.

Features include:

* High-capacity storage
* NVMe performance
* Rugged design
* Secure encryption

Snowball Edge devices support multi-petabyte migrations and significantly reduce migration time when network transfers are impractical.
In addition to data migration, Snowball Edge devices can perform edge computing workloads in remote environments where internet connectivity is limited or unavailable.
