# Module 7: Databases — Complete Notes (Lessons 1–6 + Extras)

Quick overview
- This document covers AWS database services, how to choose the right one, hands-on demo summaries, sample SQL/CLI, architecture patterns, real-life examples, and exam-ready revision tips.
- Purpose: study notes + GitHub repo content.

---

## Lesson 1: Introduction to Databases

### Why databases?
- Applications need to store, manage, and retrieve data reliably.
- Example: Coffee shop loyalty program
  - Store: customer details, orders, reward points, purchase history
  - Without a database: data duplication, inconsistent updates, hard queries

### AWS Shared Responsibility Model for Databases

₁ Fully managed services (AWS handles hardware, OS, patching, backup infrastructure; customer handles data, users, permissions)
- Examples: DynamoDB, Neptune, DocumentDB

₂ Managed services (AWS manages infrastructure; customer manages DB configuration, backups, optimization)
- Example: Amazon RDS

### Choosing the right database
- Use the right database for the right workload:
  - Structured, relational data → RDS (SQL)
  - Flexible schema / high scale → DynamoDB (NoSQL)
  - Connected data → Neptune (Graph)
  - JSON documents → DocumentDB (MongoDB-compatible)
  - High-read latency → ElastiCache / DAX (caching)

---

## Lesson 2: Relational Database Services (Amazon RDS)

### What is a relational database?
- Data stored in tables (rows + columns)
- Uses SQL, fixed schema, supports relationships (foreign keys)
- Example:
  - Users: (UserID, Name)
  - Orders: (OrderID, UserID) — relates to Users via UserID

### Key features
- SQL support
- ACID transactions
- Joins and foreign keys
- Indexed queries

### Amazon RDS overview
- Managed relational database service
- AWS handles: hardware, patching, maintenance, backups
- Supported engines: MySQL, PostgreSQL, MariaDB, Oracle, SQL Server
- Features: Multi-AZ (high availability), automated backups, read replicas (engine-dependent), scaling storage/compute

### Real-life example — Bike Rental System
- Tables: Users, Bikes, Bookings, Payments
- Relationships: Bookings reference Users and Bikes
- RDS is suitable because of structured schema and ACID needs

### Sample SQL (create database & tables)
```sql
CREATE DATABASE ecommerce;
USE ecommerce;

CREATE TABLE Users (
  UserID INT AUTO_INCREMENT PRIMARY KEY,
  Name VARCHAR(100),
  Email VARCHAR(255) UNIQUE
);

CREATE TABLE Orders (
  OrderID INT AUTO_INCREMENT PRIMARY KEY,
  UserID INT,
  OrderDate DATETIME,
  FOREIGN KEY (UserID) REFERENCES Users(UserID)
);
```

### Sample AWS CLI (create RDS instance)
```bash
aws rds create-db-instance \
  --db-instance-identifier mydbinstance \
  --db-instance-class db.t3.micro \
  --engine mysql \
  --allocated-storage 20 \
  --master-username admin \
  --master-user-password YourPassword123 \
  --backup-retention-period 7
```

### Benefits summary
- Easy management (no server management)
- Automated backups
- Scalability (storage & compute)
- High availability (Multi-AZ)

Place your RDS demo screenshots here (in assets/ folder in your repo):
- assets/rds_demo_1.png — creation / status screen
- assets/rds_demo_2.png — database/tables view

---

## Lesson 3: NoSQL Database Services (Amazon DynamoDB)

### What is NoSQL?
- No fixed rows/columns; flexible schema
- Stores items with attributes that can differ per item
- Common models: key-value, document, wide-column, graph

### Amazon DynamoDB overview
- Fully managed, serverless NoSQL database
- Features: flexible schema, auto-scaling, single-digit millisecond latency, global tables, encryption at rest, streams

### Example item (key-value)
- Key = "1"
- Value:
  - Name: Ankita
  - Address: Pune
  - FavoriteDrink: Coffee

### Real-life example — Instagram profiles
- User profiles differ in stored attributes (some have bio + website + location; others just bio)
- DynamoDB handles varying attributes efficiently

### Operations
- PutItem, GetItem, Query (efficient with partition key), Scan (reads whole table — expensive)
- Partition key vs sort key for composite primary keys

### Sample AWS CLI
```bash
aws dynamodb create-table \
  --table-name Orders \
  --attribute-definitions AttributeName=OrderNumber,AttributeType=N \
  --key-schema AttributeName=OrderNumber,KeyType=HASH \
  --provisioned-throughput ReadCapacityUnits=5,WriteCapacityUnits=5

# Put item
aws dynamodb put-item --table-name Orders --item '{
  "OrderNumber": {"N": "5"},
  "Customer": {"S": "Ankita"},
  "Items": {"S": "[\"bike\",\"helmet\"]"}
}'

# Query (efficient)
aws dynamodb query \
  --table-name Orders \
  --key-condition-expression "OrderNumber = :ord" \
  --expression-attribute-values '{":ord": {"N": "5"}}'

# Scan (reads entire table)
aws dynamodb scan --table-name Orders
```

### Query vs Scan
- Query: specify partition key (and optional sort key) — efficient
- Scan: reads entire table — avoid for large tables

### Benefits summary
- Performance at scale (single-digit ms)
- Automatic scaling
- High availability (replicated across facilities)
- Flexible schema

Place your DynamoDB demo screenshot here:
- assets/dynamodb_demo_1.png — table with items

---

## Lesson 4: AWS Databases Demonstration

### RDS demo summary
- Created MySQL instance: `database-1`
- Username: `admin`, Password: custom password
- Status: Creating → Available
- Created database: `ecommerce`
- Created tables: Users, Products, Orders
- Orders table used foreign keys (demonstrates relational design)

Add screenshots:
- assets/rds_demo_1.png
- assets/rds_demo_2.png

### DynamoDB demo summary
- Created table: `Orders`
- Partition Key: `OrderNumber`
- Loaded 10 items demonstrating flexible schema (some records include "notes"; others don't)
- Demonstrated:
  - Scan: returns all records
  - Query: returns specific items where OrderNumber = 5

Add screenshot:
- assets/dynamodb_demo_1.png

---

## Lesson 5: In-Memory Caching Services (Amazon ElastiCache)

### Problem
- Database receives thousands of repeated requests (e.g., same product page requested by many users).
- Result: database overloaded, higher latency.

### Solution: Cache
- Store frequently used data in RAM (RAM is much faster than disk).
- Application checks cache first; if missing, reads from DB and stores result in cache.

### Amazon ElastiCache overview
- Fully managed caching service
- Supports: Redis, Memcached
- Use as a caching layer between application and database

### Architecture (text diagram)
- User → EC2 Application → ElastiCache → RDS

### Cache behavior
- Cache hit: data found in cache → return instantly
- Cache miss: read from DB, store result in cache, return result

### Benefits
- High performance (microsecond latency)
- High availability (automatic failover)
- Multi-AZ replication (copies across Availability Zones)
- Cost optimization (reduces load on databases)

### Use cases
- Session management
- Gaming leaderboards
- Frequently viewed products
- Content delivery

### Example pattern (pseudocode)
```python
value = cache.get("product:123")
if not value:
  value = db.query("SELECT * FROM Products WHERE id=123")
  cache.set("product:123", value, ttl=300)
return value
```

Add architecture image:
- assets/elasticache_architecture.png

---

## Lesson 6: Additional Database Services

### Amazon DocumentDB
- MongoDB-compatible document database
- Stores JSON-like documents:
  ```json
  {
    "name": "Ankita",
    "city": "Pune",
    "skills": ["HTML", "CSS"]
  }
  ```
- Use cases:
  - Content Management Systems
  - Product Catalogs
  - User Profiles
  - Personalization Systems
- Benefits:
  - MongoDB compatibility
  - Auto scaling
  - Read replicas
  - High performance

### Amazon Neptune (Graph DB)
- Graph database designed for connected data (vertices + edges)
- Example: Social network
  - Ankita → Friend → Rahul → Friend → Priya
- Use cases:
  - Social networks
  - Fraud detection
  - Recommendation engines
- Benefits:
  - Graph-optimized
  - Millisecond queries
  - High performance
  - Auto scaling

### DynamoDB Accelerator (DAX)
- In-memory caching layer specifically for DynamoDB
- Purpose: faster reads (microsecond latency)
- Similar idea to ElastiCache but optimized for DynamoDB

### Amazon Managed Blockchain
- Managed service to build and manage blockchain networks
- Use when:
  - Supply chain tracking
  - Asset tracking
  - Food safety verification
- Example:
  - Track food from farm → warehouse → supermarket to verify origin and chain of custody

### AWS Backup
- Centralized backup management
- Supports:
  - EBS, EFS, RDS, DynamoDB, on-premises data
- Benefits:
  - Single dashboard
  - Automated backups
  - Cross-region backups
  - Compliance support
- Example: Hospital system centralizing backups for patient records, databases, and file systems

---

## Module 7 Quick Comparison Table

| Service           | Type            | Best For                                 |
|-------------------|-----------------|------------------------------------------|
| RDS             | Relational      | Structured data, SQL, relationships      |
| DynamoDB        | NoSQL           | Flexible schema, high scale, key-value   |
| ElastiCache     | Cache           | Faster reads, reduce DB load             |
| DocumentDB      | Document DB     | JSON documents, MongoDB-compatible       |
| Neptune         | Graph DB        | Relationships, connected data            |
| AWS Backup      | Backup Service  | Centralized data protection              |
| DAX             | DynamoDB Cache  | Accelerate DynamoDB reads                |
| Managed Blockchain| Blockchain    | Supply chain & asset tracking            |

---

## Easy Exam Revision (Cheat Sheet)

- RDS: SQL + Tables + Relationships
- DynamoDB: NoSQL + Key-Value + Flexible Schema + Query vs Scan
- ElastiCache: Cache in RAM + Faster Responses + Redis/Memcached
- DocumentDB: MongoDB Compatible + JSON Documents
- Neptune: Graph Database + Relationships
- AWS Backup: Centralized Backups
- DAX: Cache for DynamoDB
- Managed Blockchain: Blockchain Networks & Supply Chain Tracking

---

## Practical Tips & Patterns

### When to use RDS
- Structured data
- Need foreign keys, joins, ACID transactions
- Examples: e-commerce orders, booking systems, financial data

### When to use DynamoDB
- Need flexible schema
- High write/read scale
- Simple access patterns using partition key
- Examples: user sessions, IoT event data, game leaderboards

### When to use caching (ElastiCache / DAX)
- Many repeated reads for same data
- Latency-sensitive applications
- Caching reduces DB load and cost

### Query vs Scan in DynamoDB
- Use Query with partition key (and sort key conditions) for efficiency.
- Avoid Scan for large tables; it reads the entire table.

### Security & compliance
- Use encryption at rest and in transit
- Use IAM for access control
- Use AWS Backup for centralized backup and cross-region copies

End of notes.
