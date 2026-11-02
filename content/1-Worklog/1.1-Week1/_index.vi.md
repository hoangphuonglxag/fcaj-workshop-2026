---
title: "Worklog Tuần 1"
date: 2026-10-09
weight: 1
chapter: false
pre: "1.1 "
---

### Mục tiêu tuần 1:

* Nắm vững các khái niệm nền tảng về **Điện toán đám mây (Cloud Computing)** và **Hạ tầng toàn cầu AWS (Global Infrastructure)**.
* Hiểu cơ chế bảo mật và phân quyền với **AWS IAM (Identity & Access Management)** — nền móng để cấp quyền cho các dịch vụ Data sau này.
* Tìm hiểu kiến trúc máy chủ ảo **Amazon EC2** và ổ cứng lưu trữ khối **Amazon EBS**.
* Thiết lập môi trường tự học và giả lập dịch vụ AWS trên máy cá nhân (LocalStack, Docker, AWS CLI) mà không cần thẻ tín dụng / tài khoản AWS trả phí.

---

### Các đề mục kiến thức cần học & nghiên cứu trong tuần:

| Thứ | Chủ đề trọng tâm | Chi tiết nội dung cần tìm hiểu & Từ khóa cốt lõi | Tài liệu & Môi trường thực hành đề xuất |
| :---: | :--- | :--- | :--- |
| **Thứ 6** | **Cloud Fundamentals & AWS Infra** | • **Khái niệm Cloud:** IaaS vs PaaS vs SaaS; Public vs Private vs Hybrid Cloud.<br>• **AWS Global Infrastructure:** Regions, Availability Zones (AZs), Data Centers, Edge Locations / CloudFront PoPs.<br>• **Mô hình trách nhiệm:** AWS Shared Responsibility Model (Bảo mật CỦA đám mây vs BẢO MẬT TRONG đám mây). | • [AWS Global Infrastructure Overview](https://aws.amazon.com/about-aws/global-infrastructure/)<br>• [AWS Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/) |
| **Thứ 7** | **AWS IAM (Bảo mật & Phân quyền)** | • **Root Account:** Vì sao phải khóa Root và bật MFA.<br>• **IAM Entities:** IAM Users, Groups, Roles, Policies.<br>• **IAM Policies JSON:** Cấu trúc Effect (Allow/Deny), Action, Resource, Condition.<br>• **IAM Role vs User:** Khi nào dùng Role (cho EC2, Lambda, Glue) thay vì User credential cứng. | • [AWS IAM Core Concepts](https://docs.aws.amazon.com/iam/latest/UserGuide/introduction.html)<br>• [AWS Policy Generator](https://awspolicygen.s3.amazonaws.com/policygen.html) |
| **Thứ 2** | **Công cụ quản trị & Giả lập Local** | • **AWS CLI v2:** Cài đặt trên máy cục bộ, lệnh `aws configure`, quản lý named profiles.<br>• **Giải pháp học không cần thẻ:** Tìm hiểu **LocalStack** (giả lập AWS cục bộ qua Docker) và **AWS Educate** (tài khoản học tập không cần thẻ tín dụng). | • [Cài đặt AWS CLI v2](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)<br>• [LocalStack Getting Started](https://docs.localstack.cloud/getting-started/) |
| **Thứ 3** | **Amazon EC2 (Máy chủ ảo)** | • **EC2 Architecture:** CPU, vCPU, RAM, Instance Types (T-series General Purpose, C-series Compute, R-series Memory cho Big Data).<br>• **AMI (Amazon Machine Image):** Linux 2023, Ubuntu, Custom AMI.<br>• **Bảo mật EC2:** SSH Key Pairs (.pem / .ppk), Security Groups (Inbound / Outbound rules).<br>• **Cơ chế kết nối:** SSH, EC2 Instance Connect, AWS Systems Manager (SSM) Session Manager. | • [Amazon EC2 Basics](https://docs.aws.amazon.com/ec2/latest/userguide/concepts.html)<br>• Video: AWS EC2 Explained - freeCodeCamp / AWS Skill Builder |
| **Thứ 4** | **Amazon EBS (Lưu trữ khối)** | • **Khái niệm EBS Volume:** Gắn vào 1 EC2 trong cùng 1 AZ (Network Drive).<br>• **Phân loại Volume:** General Purpose SSD (gp2, gp3), Provisioned IOPS SSD (io1, io2), Throughput Optimized HDD (st1 cho Big Data/Logs).<br>• **EBS Snapshots:** Cơ chế sao lưu gia tăng (Incremental Backup), lưu trên S3 ngầm định. | • [Amazon EBS Volume Types](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-volume-types.html) |
| **Thứ 5** | **Tổng kết & Tự đánh giá** | • Ôn tập sơ đồ liên kết: IAM Role -> EC2 -> Gắn EBS Volume.<br>• Trả lời bộ câu hỏi trắc nghiệm kiến thức Tuần 1 (chuẩn đề thi Cloud Practitioner / SAA).<br>• Hoàn thiện ghi chú kỹ thuật cá nhân. | • [AWS Skill Builder Free Courses](https://explore.skillbuilder.aws/) |

---

### Tiêu chí & Năng lực cần đạt sau tuần 1:

1. **Hiểu rõ bản chất:** Giải thích được vì sao doanh nghiệp chuyển từ On-premise lên Cloud và cách chọn Region tối ưu (độ trễ, chi phí, luật dữ liệu).
2. **Nắm vững IAM:** Viết và đọc hiểu được một JSON IAM Policy cơ bản (ví dụ: cấp quyền chỉ đọc S3 cho một IAM Role).
3. **Hiểu sâu EC2 & EBS:** Phân biệt được sự khác biệt giữa Instance Store (lưu trữ tạm mất khi stop) và EBS (bền vững), biết chọn loại EC2 phù hợp khi chạy tác vụ xử lý dữ liệu (RAM-intensive vs CPU-intensive).
