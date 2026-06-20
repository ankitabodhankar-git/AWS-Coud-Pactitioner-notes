# Module 9: Security on AWS — Complete Study Notes

## Lesson 1: Introduction to Security on AWS

### What You Will Learn

- How **authentication** and **authorization** help secure enterprise data
- **Customer and AWS security responsibilities** in the cloud
- Different types of **AWS security controls**
<img width="1299" height="456" alt="image" src="https://github.com/user-attachments/assets/f454ea61-8f0a-4885-8fe6-a66f44342ecd" />

---

### Two Fundamental Security Concepts

| Concept | What It Means | Example |
|:--|:--|:--|
| **Authentication** | Verifying who someone is (username + password) | Employee logs in to portal |
| **Authorization** | What someone is allowed to do (permissions) | Employee can only see their own records |

**Simple Way to Remember:**
- Authentication = **"Who are you?"**
- Authorization = **"What can you do?"**

---

### 🔄 AWS Shared Responsibility Model

Cloud security is **shared** between **Customer** and **AWS**.

| Who | Responsible For | What It Means |
|:--|:--|:--|
| **Customer** | Security **IN** the cloud | Your data, your systems, your applications, who has access |
| **AWS** | Security **OF** the cloud | Physical data centers, hardware, hypervisor, global infrastructure |

---

### ✅ Exam Question: Healthcare Company

**Question:** What is the **customer's security responsibility**?

| Option | Correct? |
|:--|:--|
| Protecting physical security of data centers | ❌ No (AWS responsibility) |
| **Protecting sensitive patient data in S3 and RDS** | ✅ **Yes (Customer responsibility)** |
| Maintaining/patching hypervisor | ❌ No (AWS responsibility) |
| Replacing faulty hardware | ❌ No (AWS responsibility) |

**Answer:** ✅ **Protecting sensitive patient data stored in Amazon S3 and Amazon RDS**

---

### 🛡️ AWS Security Controls (3 Types)

| Control | Purpose |
|:--|:--|
| **Prevent** | Stop security incidents (permission + access management) |
| **Protect** | Protect networks, applications, and data |
| **Detect & Respond** | Find and fix security incidents quickly |

---

### ✅ Exam Question: Online Banking

**Scenario:** Customer logs in (username + password) → tries to transfer $10,000 → system checks if customer has **privileges** for this amount

**Question:** What type of check is this?

| Option | Correct? |
|:--|:--|
| Authentication | ❌ No (verifying identity) |
| **Authorization** | ✅ **Yes (checking privileges)** |
| Encryption | ❌ No (data protection) |
| Auditing | ❌ No (tracking actions) |

**Answer:** ✅ **Authorization**

---

## 🛡️ Lesson 2: Preventing Unauthorized Access

### What You Will Learn

- Benefits and purpose of **AWS IAM (Identity and Access Management)**
- Best practices for protecting **AWS root user**
- **IAM identities and policies** for **principle of least privilege**
- Additional AWS services for **least privilege**

---

### 🔐 AWS Account Root User

**What is Root User?**
- Owner of the AWS account
- Can do **anything** in the account (EC2, S3, ML, etc.)
- Like being the **owner of a coffee shop** (can use any system, cannot be restricted)

**⚠️ Root User is EXTREMELY Powerful**

**Best Practices:**
1. ✅ Set **strong password** when creating account
2. ✅ Turn on **MFA (Multi-Factor Authentication)** immediately after logging in
3. ❌ **DON'T use root user for daily tasks**

---

### What is MFA?

**MFA** = You need **2+ verification methods** to log in:
- Email + Password + **Randomized token**

**Example Answer:** ✅ **Provide two or more verification methods to gain access**

---

### 🏗️ AWS IAM (Identity and Access Management)

**What is IAM?**
Service to control access to AWS resources in a **granular way**.

**IAM Default Rule:**
- By default, **ALL actions are DENIED**
- You must **explicitly ALLOW** any action

**Principle of Least Privilege:**
- Give access **only to what they need**
- Give **nothing else**

---

### IAM Components

| Component | What It Is | Permissions |
|:--|:--|:--|
| **IAM Users** | Individual identities (like John Doe) | By default: **ZERO permissions** |
| **IAM Groups** | Group of users (like "employees") | Attach policy to group → all users **inherit permissions** |
| **IAM Roles** | Temporary access identity | **No username/password** → can be assumed for **temporary time** |
| **IAM Policies** | JSON document (defines permissions) | Describes what API calls user can/cannot make |

---

### IAM Policy Structure

```json
{
  "Effect": "Allow",        // Only 2 options: Allow or Deny
  "Action": "s3:ListBucket", // Any AWS API call
  "Resource": "bucket-ID"    // AWS resource ID
}
```

**What This Policy Does:**
- User can **view** bucket `coffee_shop_reports`
- User can do **nothing else** in the account

---

### IAM Policy Types

| Type | Created By | Can Use By |
|:--|:--|:--|
| **AWS Managed Policies** | AWS | As many users as you want |
| **Customer Managed Policies** | You (custom) | For specific use cases |

---

### IAM Roles (Temporary Access)

**What is IAM Role?**
- Similar to users/groups
- Can have permissions (allow/deny actions)
- **No static credentials** (no username/password)
- Can be assumed for **temporary time**

**When to Use Roles:**
- Grant temporary access to AWS resources
- AWS services interact with each other
- Federated identity access (users/applications)
- Cross-account access

---

### IAM Identity Center

**What It Does:**
- **Centralize** identity and access across AWS accounts + applications
- Connect to **existing identity source**
- Provide **single sign-on (SSO)** to all AWS services

**Federated Identity Management:**
- Users access multiple apps/services with **single set of credentials**

---

### Additional Access Management Services

| Service | What It Does |
|:--|:--|
| **AWS Secrets Manager** | Manage, rotate, retrieve **database credentials, API keys, secrets** |
| **AWS Systems Manager** | Centralized view of **nodes** → automate registry edits, user management, security patching |

**What are Secrets?**
- Passwords
- Database credentials
- API keys

**What are Nodes?**
- Connection points in network/system/structure

---

## 🔒 Lesson 3: Protecting Networks and Applications

### What You Will Learn

- How **DDoS attacks** attack networks and applications
- How **AWS infrastructure and services** protect against DDoS

---

### 🚨 DoS vs DDoS Attacks

| Attack | How It Works |
|:--|:--|
| **DoS (Denial of Service)** | Single attacker floods web application → application overloaded → legitimate requests denied |
| **DDoS (Distributed DoS)** | **Multiple compromised computers (zombie bots)** unknowingly send excessive traffic → target overwhelmed |

**Example Answer:** ✅ **DDoS uses multiple compromised computers and devices to launch the attack**

---

### How DDoS Attack Works (UDP Flood Example)

**Normal:**
1. Send request to weather service: "Give me forecast"
2. Weather service sends back forecasts

**Attack:**
1. Bad actor + zombie bots send request: "Give me forecast"
2. They give **fake return address** → **your address**
3. Weather service floods **your server** with megabytes of data
4. Your system **brought to standstill**
<img width="1045" height="264" alt="image" src="https://github.com/user-attachments/assets/29437925-f3a5-42c1-9695-f6ef43c1cfc4" />
<img width="1045" height="378" alt="image" src="https://github.com/user-attachments/assets/d9b8e483-fe34-46c7-b952-48806ee58c6e" />

---

### 🛡️ AWS Infrastructure Protection

| Component | How It Protects |
|:--|:--|
| **Security Groups** | Only allow proper request traffic → operate at **AWS network level** → shrug off massive attacks using entire **Region capacity** |
| **Elastic Load Balancing (ELB)** | Handles traffic first → frontend server **not overwhelmed** → runs at **Region level** |
| **AWS Regions** | **Enormous capacity** → extremely difficult to overwhelm → massively expensive for attackers |

---

### 🛡️ AWS Services for DDoS Protection

| Service | Cost | What It Does |
|:--|:--|:--|
| **AWS Shield Standard** | **Free** (built-in) | Automatically protect from **common/frequent DDoS** → built into ELB, CloudFront, Route 53 |
| **AWS Shield Advanced** | **Paid** | **Detailed attack diagnostics** → detect/mitigate **sophisticated DDoS** → integrates with CloudFront, Route 53, ELB |
| **AWS WAF** | Paid | **Web Application Firewall** → monitors requests → checks IP against **web ACL** → blocked IP = denied, legitimate = allowed → **ML to recognize new threats** |


