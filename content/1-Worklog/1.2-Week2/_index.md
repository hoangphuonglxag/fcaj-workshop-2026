---
title: "Week 2 Worklog"
date: 2026-10-16
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

* Master AWS core networking through **Amazon VPC (Virtual Private Cloud)** — the essential security boundary for deploying data workloads (Redshift, RDS, EMR, Glue).
* Understand IP allocation using **CIDR** notation and differentiate between **Public Subnets** and **Private Subnets**.
* Analyze packet routing mechanics via **Internet Gateways (IGW)**, **Route Tables**, and **NAT Gateways**.
* Compare network defense controls: **Security Groups (Stateful)** and **Network Access Control Lists - NACLs (Stateless)**.
* Study **VPC Endpoints (Gateway Endpoint for Amazon S3)** — an indispensable pattern allowing private compute clusters to access S3 over the AWS private backbone with zero data processing fees.

---

### Core Learning Topics & Research Modules This Week:

| Day | Focus Area | Detailed Study Topics & Core Keywords | Recommended Resources & Study Tools |
| :---: | :--- | :--- | :--- |
| **Fri** | **Amazon VPC Fundamentals & CIDR** | • **VPC Concepts:** Logically isolated virtual network dedicated to an AWS account.<br>• **IP Planning (CIDR):** Calculating IPv4 ranges (`10.0.0.0/16` = 65,536 IPs, `/24` = 256 IPs). AWS 5 reserved IPs per subnet.<br>• **Public vs Private Subnet:** Differences in auto-assign public IP settings and default route table association with an Internet Gateway. | • [AWS VPC Fundamentals](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)<br>• [Visual Subnet Calculator](https://www.davidc.net/sites/default/subnets/subnets.html) |
| **Sat** | **Routing & Internet Gateway** | • **Internet Gateway (IGW):** Redundant, horizontally scaled VPC component connecting to the public internet.<br>• **Route Tables:** Defining local routes and default routes (`0.0.0.0/0` -> `igw-xxxx`).<br>• **Multi-AZ Topology:** Why production environments mandate deployment across at least 2 Availability Zones. | • [VPC Route Tables Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html)<br>• AWS Reference Architecture: Multi-AZ VPC Patterns |
| **Mon** | **NAT Gateway & Private Egress** | • **Private Subnet Internet Access:** How private workers (EC2, Spark) fetch libraries (pip, yum, maven) without exposing listening ports to inbound internet traffic.<br>• **NAT Gateway vs NAT Instance:** Comparing high availability, automated scaling (up to 100 Gbps), maintenance, and pricing.<br>• **Elastic IP (EIP):** Static public IPv4 assigned to NAT Gateway. | • [AWS NAT Gateway Guide](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html)<br>• Video: NAT Gateway vs NAT Instance Deep Dive |
| **Tue** | **Network Security: Security Groups vs NACLs** | • **Security Groups (SG):** Instance-level firewall, **Stateful** (return traffic is automatically allowed).<br>• **NACLs:** Subnet-level firewall, **Stateless** (explicit inbound and outbound rules required), numbered rule evaluations.<br>• **Bastion Host / Jump Server:** Secure jump-box pattern for accessing private subnet instances via SSH agent forwarding. | • [Security Groups vs NACLs Comparison](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Security.html)<br>• AWS Whitepaper: Best Practices for VPC Security |
| **Wed** | **VPC Endpoints & Data Cost Optimization** | • **Data Engineering Cost Bottleneck:** Routing terabytes of S3 ETL traffic through a NAT Gateway incurs costly NAT data processing fees (~$0.045/GB).<br>• **VPC Endpoints (AWS PrivateLink):**<br>&emsp; + **Gateway Endpoint:** Dedicated to S3 and DynamoDB (free, route table target).<br>&emsp; + **Interface Endpoint:** For all other services (provisions ENI with private IP in subnet). | • [VPC Endpoints for Amazon S3](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-s3.html)<br>• [AWS PrivateLink Architecture](https://aws.amazon.com/privatelink/) |
| **Thu** | **Architecture Diagramming & Synthesis** | • Diagram a production-ready Multi-AZ Data Platform VPC using draw.io: VPC, 2 AZs, Public Subnets (NAT GW, Bastion), Private Subnets (Workers, RDS), and S3 Gateway Endpoint.<br>• Practice scenario-based networking questions from the AWS Solutions Architect Associate exam. | • Diagramming: [draw.io with AWS 2024 Architecture Icons](https://app.diagrams.net/) |

---

### Target Outcomes & Competency Checklist:

1. **Network Topology Mastery:** Able to independently design and justify a complete VPC architecture for enterprise data workloads.
2. **Packet Flow Fluency:** Accurately trace the end-to-end packet path when a private worker pulls a Python package through a NAT Gateway.
3. **Data Cost Optimization:** Deeply understand why **S3 Gateway Endpoints** are non-negotiable for large-scale data engineering on AWS.
