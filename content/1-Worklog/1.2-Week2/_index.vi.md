---
title: "Worklog Tuần 2"
date: 2026-10-16
weight: 2
chapter: false
pre: " 1.2"
---

### Mục tiêu tuần 2:

* Nắm vững kiến trúc mạng cốt lõi của AWS qua **Amazon VPC (Virtual Private Cloud)** — ranh giới bảo mật bắt buộc để triển khai các cụm dữ liệu (Redshift, RDS, EMR, Glue).
* Hiểu cách quy hoạch dải mạng **CIDR**, phân chia **Public Subnet** và **Private Subnet**.
* Làm rõ luồng điều hướng gói tin với **Internet Gateway (IGW)**, **Route Tables**, và **NAT Gateway**.
* So sánh sâu hai cơ chế tường lửa: **Security Groups (Stateful)** và **Network Access Control Lists - NACLs (Stateless)**.
* Nghiên cứu cơ chế **VPC Endpoints (Gateway Endpoint cho Amazon S3)** — kiến trúc sống còn giúp các tác vụ Data truy cập S3 qua mạng nội bộ của AWS với chi phí 0 đồng và băng thông tối đa.

---

### Các đề mục kiến thức cần học & nghiên cứu trong tuần:

| Thứ | Chủ đề trọng tâm | Chi tiết nội dung cần tìm hiểu & Từ khóa cốt lõi | Tài liệu & Công cụ học tập đề xuất |
| :---: | :--- | :--- | :--- |
| **Thứ 6** | **Tổng quan Amazon VPC & CIDR** | • **Khái niệm VPC:** Mạng ảo độc lập logic dành riêng cho tài khoản AWS.<br>• **Quy hoạch IP (CIDR):** Cách tính toán dải IP IPv4 (`10.0.0.0/16` = 65,536 IPs, `/24` = 256 IPs). 5 IP dự trữ đặc biệt của AWS trong mỗi subnet.<br>• **Public Subnet vs Private Subnet:** Khác nhau ở điểm nào (Auto-assign Public IP và Route Table có trỏ ra Internet Gateway hay không). | • [AWS VPC Fundamentals](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)<br>• Công cụ trực quan: [CIDR Calculator / Visual Subnet Calculator](https://www.davidc.net/sites/default/subnets/subnets.html) |
| **Thứ 7** | **Định tuyến (Routing) & Internet Gateway** | • **Internet Gateway (IGW):** Cổng kết nối giữa VPC và Public Internet (Highly Available, Serverless).<br>• **Route Tables:** Cách định cấu hình Local Route và Default Route (`0.0.0.0/0` -> `igw-xxxx`).<br>• **Mô hình Multi-AZ:** Tại sao một hệ thống production luôn cần tối thiểu 2 AZs (ví dụ: AZ-a và AZ-b). | • [VPC Route Tables Guide](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html)<br>• Sơ đồ tham khảo: AWS Reference Architecture - Multi-AZ VPC |
| **Thứ 2** | **NAT Gateway & Private Egress** | • **Vấn đề của Private Subnet:** Khi các Data Worker (EC2, Spark) cần ra ngoài internet để tải thư viện (pip, yum, maven) nhưng không được phép mở cổng nhận traffic từ bên ngoài.<br>• **NAT Gateway vs NAT Instance:** So sánh về tính sẵn sàng (HA), băng thông (tối đa 100 Gbps), quản trị và chi phí.<br>• **Elastic IP (EIP):** Khái niệm IP tĩnh công cộng gán cho NAT Gateway. | • [AWS NAT Gateway Docs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html)<br>• Video: NAT Gateway vs NAT Instance - Tech with Lucy / Stephane Maarek |
| **Thứ 3** | **Bảo mật mạng: Security Groups vs NACLs** | • **Security Groups (SG):** Hoạt động ở tầng máy chủ (Instance level), tính chất **Stateful** (cho phép chiều vào thì tự động cho phép chiều ra tương ứng).<br>• **NACLs:** Hoạt động ở tầng mạng con (Subnet level), tính chất **Stateless** (phải mở cả Inbound và Outbound rules riêng biệt), đánh số thứ tự ưu tiên (Rule number).<br>• **Bastion Host / Jump Server:** Kiến trúc truy cập an toàn vào máy chủ Private Subnet qua SSH forwarding. | • [Security Groups vs NACLs Comparison](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Security.html)<br>• Bảng so sánh Stateful vs Stateless trên AWS Whitepapers |
| **Thứ 4** | **VPC Endpoints & Tối ưu Data Pipeline** | • **Vấn đề chi phí của Data Engineer:** Nếu cụm Spark trong Private Subnet đọc 10TB dữ liệu từ S3 qua NAT Gateway, chi phí Data Processing của NAT Gateway sẽ rất đắt (~$0.045/GB).<br>• **VPC Endpoints (AWS PrivateLink):**<br>&emsp; + **Gateway Endpoint:** Dành cho S3 và DynamoDB (miễn phí, thêm route vào Route Table).<br>&emsp; + **Interface Endpoint:** Dành cho các dịch vụ khác (tạo Elastic Network Interface - ENI có Private IP). | • [VPC Endpoints for Amazon S3](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-s3.html)<br>• [AWS PrivateLink Architecture](https://aws.amazon.com/privatelink/) |
| **Thứ 5** | **Vẽ sơ đồ kiến trúc & Tổng kết** | • Thiết kế lại toàn bộ sơ đồ mạng Multi-AZ chuẩn Data Platform trên draw.io / Miro: Gồm VPC, 2 AZ, Public Subnets (NAT GW, Bastion), Private Subnets (Worker, DB), S3 Gateway Endpoint.<br>• Làm các câu hỏi tình huống thiết kế mạng trong kỳ thi Solutions Architect Associate. | • Công cụ vẽ kiến trúc: [draw.io (thư viện AWS 2024 Icons)](https://app.diagrams.net/) |

---

### Tiêu chí & Năng lực cần đạt sau tuần 2:

1. **Tư duy thiết kế mạng:** Tự tay vẽ và giải thích được một sơ đồ VPC hoàn chỉnh cho một công ty: đâu là nơi đặt Load Balancer, đâu là nơi đặt Server xử lý dữ liệu, đâu là nơi đặt Database.
2. **Nắm rõ luồng đi của gói tin (Packet Flow):** Mô tả chính xác đường đi khi một máy tính trong Private Subnet tải thư viện Python từ PyPI qua NAT Gateway.
3. **Tối ưu chi phí cho Data:** Hiểu rõ vì sao luôn luôn phải dùng **S3 Gateway Endpoint** trong bất kỳ kiến trúc dữ liệu nào trên AWS.
