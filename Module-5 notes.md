# Module 5 – Networking

## Introduction to Networking

Networking refers to interconnected devices that exchange data and resources. In AWS, networking consists of the infrastructure and services that work together to host applications, data, and cloud resources.

Networking helps AWS resources communicate with each other and with users over the internet.
<img width="1680" height="875" alt="image" src="https://github.com/user-attachments/assets/11b874a9-6130-4ecf-bbd8-13d09fda7f24" />

---

# Amazon Virtual Private Cloud (Amazon VPC)

Amazon VPC (Virtual Private Cloud) is a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define.

A VPC acts as your private network inside AWS.

When using a VPC, you can:

* Define your own private IP address range
* Launch AWS resources
* Control connectivity
* Control security
* Organize resources

Amazon VPC provides three major benefits:

### Security

You can:

* Secure connections
* Monitor traffic
* Restrict access
* Control communication between resources

### Control

You have control over:

* Resource placement
* Connectivity
* Security configuration

### Convenience

Amazon VPC reduces the effort required to create and manage networks compared to traditional on-premises environments.
<img width="1680" height="440" alt="image" src="https://github.com/user-attachments/assets/65b811cb-796d-467b-b993-793b73980204" />

---

# Subnets

A subnet is a section of a VPC.

Subnets help organize resources inside a VPC.

Resources are grouped into subnets based on their purpose and accessibility requirements.
<img width="1516" height="1443" alt="image" src="https://github.com/user-attachments/assets/942a165e-96a1-4409-b64b-11d6ca2a3c0b" />

---

## Public Subnet

A public subnet contains resources that should be accessible from the internet.

Examples include:

* Customer-facing websites
* Public applications
* Internet-facing load balancers

Resources in a public subnet can communicate with the internet.

---

## Private Subnet

A private subnet contains resources that should not be directly accessible from the internet.

Examples include:

* Databases
* Internal business applications
* Customer information systems
* Backend services

Private subnets provide additional protection for sensitive resources.

---

# Internet Gateway

An Internet Gateway allows communication between a VPC and the internet.

Without an Internet Gateway:

* Internet users cannot access resources inside the VPC.

With an Internet Gateway:

* Internet traffic can enter and leave the VPC.

Internet Gateways are commonly used for:

* Websites
* Public applications
* Internet-facing services

You can think of an Internet Gateway as the front door to your VPC.
<img width="1680" height="381" alt="image" src="https://github.com/user-attachments/assets/b55b22df-9660-4186-9327-5ad0a5864e93" />

---

# Virtual Private Gateway

A Virtual Private Gateway enables secure communication between a VPC and a private network.

It is commonly used with VPN connections.

A Virtual Private Gateway allows traffic into a VPC only if it originates from an approved private network.

Common connections include:

* Corporate networks
* On-premises data centers
* Internal business environments
<img width="1680" height="900" alt="image" src="https://github.com/user-attachments/assets/2ab844ce-7db3-47bb-89c1-8657e7603a8c" />

---

# Virtual Private Network (VPN)

A VPN creates a secure encrypted tunnel through the internet.

VPNs protect network traffic while it travels between locations.

Benefits include:

* Secure communication
* Data privacy
* Encrypted traffic

VPNs are often used to securely connect company networks to AWS resources.

---

# AWS Direct Connect

AWS Direct Connect provides a dedicated private connection between a customer network and AWS.

Unlike VPN connections that use the public internet, Direct Connect uses dedicated connectivity.

Benefits include:

* Higher bandwidth
* Consistent performance
* Improved security
* Reduced network congestion
* Compliance support

Direct Connect is commonly used when organizations transfer large amounts of data between AWS and their data centers.

---

# AWS Client VPN

AWS Client VPN is a fully managed VPN service that connects remote workers and on-premises networks to AWS resources.

Features:

* Fully managed
* Elastic
* Automatically scales based on demand

Benefits:

* Advanced authentication
* Remote access
* Simplified management

Use case:

Organizations with remote employees who need secure access to AWS resources.

---

# AWS Site-to-Site VPN

AWS Site-to-Site VPN creates secure connections between:

* Branch offices
* Data centers
* AWS resources

Benefits:

* Secure communication
* High availability
* Private connectivity

Use cases:

* Application migration
* Connecting corporate offices to AWS

---

# AWS PrivateLink

AWS PrivateLink enables private communication between VPCs, services, and resources.

With AWS PrivateLink, communication occurs without requiring:

* Internet Gateway
* Public IP address
* Site-to-Site VPN
* Direct Connect

Benefits:

* Secure communication
* Simplified connectivity
* Private access to services

PrivateLink allows resources to communicate as if they were inside the same VPC.

---

# Security Groups

Security Groups act as virtual firewalls for Amazon EC2 instances.

Security Groups operate at the instance level.

Characteristics:

* Stateful
* Allow rules only

Security Groups control:

* Inbound traffic
* Outbound traffic

Because they are stateful, return traffic is automatically allowed.

---

# Network Access Control Lists (Network ACLs)

Network ACLs provide security at the subnet level.

Characteristics:

* Stateless
* Support allow rules
* Support deny rules

Network ACLs evaluate all inbound and outbound traffic separately.

They provide an additional layer of security for subnets.

---

# Security Groups vs Network ACLs

### Security Groups

* Instance-level security
* Stateful
* Allow rules only

### Network ACLs

* Subnet-level security
* Stateless
* Allow and deny rules

Both work together to secure resources within a VPC.

---

# Building a VPC Architecture

When building a VPC, the typical process includes:

### Create a VPC

First create an Amazon VPC and choose the AWS Region.

---

### Create Subnets

Create:

* Public Subnets
* Private Subnets

Best practice is to create subnets across multiple Availability Zones to improve availability.

Example architecture:

* 2 Public Subnets
* 2 Private Subnets
* 2 Availability Zones

---

### Create an Internet Gateway

Attach the Internet Gateway to the VPC.

This allows public resources to communicate with the internet.

---

### Create Route Tables

Route Tables contain rules called routes.

Routes determine where network traffic is sent.

Example:

Destination:

0.0.0.0/0

Target:

Internet Gateway

This route allows internet traffic.

---

### Associate Public Subnets

Public subnets are associated with route tables that include internet routes.

Private subnets remain private because they do not use routes that connect directly to the internet.

---

### Configure Security

After networking components are created, security is configured using:

* Security Groups
* Network ACLs

---

# Edge Networking

Edge networking brings data and content closer to users.

Benefits include:

* Lower latency
* Faster response times
* Better user experiences

AWS uses Edge Locations to support edge networking services.

---

# Domain Name System (DNS)

DNS stands for Domain Name System.

DNS translates:

Domain Names

↓

IP Addresses

Humans use domain names.

Computers use IP addresses.

DNS acts as the translator between them.

Example:

```text
www.example.com
```

↓

```text
192.2.0.2
```

This process is called DNS Resolution.

---

# Amazon Route 53

Amazon Route 53 is AWS's DNS service.

Route 53 provides a reliable and cost-effective way to route users to applications and resources.

Features:

* DNS management
* Domain registration
* Traffic routing
* Automatic scaling

Route 53 can route traffic to:

* Amazon EC2 Instances
* Load Balancers
* AWS resources
* External resources

---

## Route 53 Routing Policies

Route 53 supports several routing policies:

### Latency-Based Routing

Routes users to the location with the lowest latency.

### Geolocation Routing

Routes users based on geographic location.

### Geoproximity Routing

Routes users based on geographic distance.

### Weighted Routing

Distributes traffic based on assigned weights.

---

# Amazon CloudFront

Amazon CloudFront is a Content Delivery Network (CDN).

CloudFront delivers content from locations closer to users.

Benefits:

* Faster loading times
* Lower latency
* Improved reliability
* Better user experience

CloudFront stores copies of content at edge locations around the world.

Content examples:

* Websites
* Images
* Videos
* Applications

---

## CloudFront Use Cases

### Streaming Services

Delivers videos smoothly even during high demand.

### Ecommerce Websites

Delivers product images and web pages quickly.

### Mobile Applications

Delivers maps, images, and application data efficiently.

---

# AWS Global Accelerator

AWS Global Accelerator improves:

* Availability
* Performance
* Security

Global Accelerator uses the AWS global network to route traffic efficiently.

Features:

* Intelligent traffic routing
* Fast failover
* Improved application performance

Use cases include:

* Global gaming applications
* Financial services applications

---

# Global Architectures

Many organizations operate across multiple AWS Regions and multiple VPCs.

These organizations often require:

* Global availability
* Low latency
* Reliable connectivity
<img width="1680" height="657" alt="image" src="https://github.com/user-attachments/assets/e2e18712-f52b-4f2f-9c59-dbbb6a78029d" />

---

# VPN vs Direct Connect

### Use VPN When:

* Secure connectivity is required
* Data transfers are smaller
* Flexible connectivity is needed

### Use Direct Connect When:

* Large data transfers occur
* Higher bandwidth is required
* Dedicated connectivity is needed

---

# VPN and Direct Connect Together

Organizations can use VPN and Direct Connect together.

A common design is:

Direct Connect = Primary Connection

VPN = Backup Connection

This provides failover capability if the Direct Connect connection becomes unavailable.

---

# Multi-Region Architecture

Global applications often use:

* Multiple AWS Regions
* Multiple VPCs
* Route 53
* CloudFront

This architecture improves:

* Availability
* User experience
* Global content delivery

---

# Route 53 and CloudFront Working Together

Step 1:

User accesses a website using a domain name.

Step 2:

Route 53 determines the most appropriate AWS Region.

Step 3:

The user is directed to the nearest CloudFront Edge Location.

Step 4:

CloudFront retrieves and delivers content from the origin server.

Result:

* Lower latency
* Faster content delivery
* Improved global user experience



These networking services help organizations securely connect resources, control access, improve performance, and deliver applications to users around the world.
