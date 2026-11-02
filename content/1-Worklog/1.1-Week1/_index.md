---
title: "Week 1 Worklog"
date: 2026-10-09
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Week 1 Objectives:

* Master fundamental concepts of **Cloud Computing** and **AWS Global Infrastructure**.
* Understand security and access governance via **AWS IAM (Identity & Access Management)** — the foundation for data service authorization.
* Learn core compute and storage architectures: **Amazon EC2** and **Amazon EBS**.
* Set up a local study environment and explore AWS simulation tools (LocalStack, Docker, AWS CLI) without requiring a credit card or paid AWS account.

---

### Core Learning Topics & Research Modules This Week:

| Day | Focus Area | Detailed Study Topics & Core Keywords | Recommended Resources & Emulation Tools |
| :---: | :--- | :--- | :--- |
| **Fri** | **Cloud Fundamentals & AWS Infra** | • **Cloud Paradigms:** IaaS vs PaaS vs SaaS; Public vs Private vs Hybrid Cloud.<br>• **AWS Global Infrastructure:** Regions, Availability Zones (AZs), Data Centers, Edge Locations / CloudFront PoPs.<br>• **Responsibility Model:** AWS Shared Responsibility Model (Security OF the Cloud vs Security IN the Cloud). | • [AWS Global Infrastructure Overview](https://aws.amazon.com/about-aws/global-infrastructure/)<br>• [AWS Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/) |
| **Sat** | **AWS IAM (Security & Permissions)** | • **Root Account:** Why the root account must be secured with MFA and locked.<br>• **IAM Entities:** IAM Users, Groups, Roles, Policies.<br>• **IAM Policies JSON:** Structure of Effect (Allow/Deny), Action, Resource, Condition.<br>• **IAM Roles vs Users:** When to use Roles (for EC2, Lambda, Glue) instead of hardcoded long-term credentials. | • [AWS IAM Core Concepts](https://docs.aws.amazon.com/iam/latest/UserGuide/introduction.html)<br>• [AWS Policy Generator](https://awspolicygen.s3.amazonaws.com/policygen.html) |
| **Mon** | **Management Tools & Local Emulation** | • **AWS CLI v2:** Installation, `aws configure`, managing named profiles.<br>• **No-Credit-Card Learning:** Exploring **LocalStack** (AWS local cloud emulator via Docker) and **AWS Educate** (free training accounts without credit cards). | • [AWS CLI Installation Guide](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)<br>• [LocalStack Documentation](https://docs.localstack.cloud/getting-started/) |
| **Tue** | **Amazon EC2 (Virtual Compute)** | • **EC2 Architecture:** vCPU, RAM, Instance families (T-series General Purpose, C-series Compute, R-series Memory for Big Data).<br>• **AMI (Amazon Machine Image):** Linux 2023, Ubuntu, Custom AMI.<br>• **EC2 Security:** SSH Key Pairs (.pem / .ppk), Security Groups (Stateful firewall rules).<br>• **Connection Mechanics:** SSH, EC2 Instance Connect, AWS Systems Manager (SSM) Session Manager. | • [Amazon EC2 Basics](https://docs.aws.amazon.com/ec2/latest/userguide/concepts.html)<br>• Video: AWS EC2 Deep Dive - AWS Skill Builder |
| **Wed** | **Amazon EBS (Block Storage)** | • **EBS Volume Concepts:** Network-attached storage within a single AZ.<br>• **Volume Types:** General Purpose SSD (gp2, gp3), Provisioned IOPS SSD (io1, io2), Throughput Optimized HDD (st1 for large streaming/batch logs).<br>• **EBS Snapshots:** Incremental backup mechanism backed by S3. | • [Amazon EBS Volume Types](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-volume-types.html) |
| **Thu** | **Synthesis & Self-Assessment** | • Review connection model: IAM Role -> EC2 -> Attached EBS Volume.<br>• Practice sample practice questions (aligned with Cloud Practitioner & SAA).<br>• Complete personal study notes and architecture cheatsheet. | • [AWS Skill Builder Free Learning](https://explore.skillbuilder.aws/) |

---

### Target Outcomes & Competency Checklist:

1. **Foundational Clarity:** Able to explain why enterprises migrate to cloud and how to choose optimal regions (latency, cost, compliance).
2. **IAM Proficiency:** Capable of reading and drafting JSON IAM Policies (e.g., granting read-only S3 access to a specific role).
3. **Compute & Storage Discernment:** Clear differentiation between ephemeral Instance Store and persistent EBS; knowing which EC2 type suits data workloads.
