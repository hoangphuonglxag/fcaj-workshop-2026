---
title: "Nhật ký công việc"
date: 2026-10-09
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

Trang này tổng hợp nhật ký công việc (Worklog) theo từng tuần trong suốt quá trình tham gia chương trình **Workforce Bootcamp - First Cloud AI Journey (FCAJ)** với định hướng chuyên sâu **Cloud Data Engineer**.

Lộ trình thực tập được thiết kế gồm 12 tuần, đi từ nền tảng điện toán đám mây, kiến trúc hạ tầng mạng, lưu trữ và cơ sở dữ liệu, cho đến xây dựng các đường ống dữ liệu (Data Pipelines), xử lý phân tán (Distributed Processing), Data Lakehouse và tối ưu chi phí:

### 📌 Lộ trình thực tập 12 tuần (Định hướng Cloud Data Engineer):

* **[Tuần 1: Onboarding, AWS Fundamentals, IAM & Compute (EC2, CLI)](1.1-week1/)**
  * Làm quen văn hóa FCAJ, tìm hiểu AWS Global Infrastructure, quản lý danh tính và phân quyền (IAM), thiết lập AWS CLI và khởi tạo máy chủ EC2.

* **[Tuần 2: Mạng & Bảo mật hạ tầng: Custom VPC, Subnets, NAT & VPC Endpoints](1.2-week2/)**
  * Thiết kế mạng nội bộ VPC chuẩn Multi-AZ, cấu hình Public/Private Subnet, NAT Gateway, Security Group/NACL và thiết lập VPC Endpoints cho các dịch vụ dữ liệu an toàn.

* **[Tuần 3: Lưu trữ & Cơ sở dữ liệu: Amazon S3 Data Lake, RDS & DynamoDB](1.3-week3/)**
  * Nắm vững Amazon S3 làm nền tảng Data Lake, phân vùng dữ liệu (Partitioning), cấu hình vòng đời (Lifecycle Rules), triển khai Relational Database (RDS) và NoSQL (DynamoDB).

* **[Tuần 4: Serverless Computing & Tự động hóa Pipeline: Lambda, S3 Triggers, CloudWatch](1.4-week4/)**
  * Xây dựng kiến trúc xử lý sự kiện (Event-driven) với AWS Lambda, tự động kích hoạt ETL khi có dữ liệu mới trên S3, giám sát và cảnh báo hệ thống qua CloudWatch & EventBridge.

* **[Tuần 5: Thu thập & Tiếp nhận dữ liệu thời gian thực (Data Ingestion & Streaming)](1.5-week5/)**
  * Tìm hiểu các luồng dữ liệu thời gian thực với Amazon Kinesis Data Streams / Firehose và Amazon MSK (Managed Streaming for Kafka).

* **[Tuần 6: Quản lý Metadata & Truy vấn dữ liệu Serverless: AWS Glue Catalog & Athena](1.6-week6/)**
  * Thu thập lược đồ dữ liệu tự động bằng Glue Crawler, quản trị Data Catalog và thực thi truy vấn phân tích SQL trực tiếp trên S3 với Amazon Athena.

* **[Tuần 7: Xử lý dữ liệu Batch & Chuyển đổi ETL: AWS Glue Studio & PySpark](1.7-week7/)**
  * Phát triển các Glue ETL Jobs chuyển đổi dữ liệu từ Raw sang Parquet/Iceberg, làm sạch và chuẩn hóa dữ liệu lớn serverless.

* **[Tuần 8: Xử lý dữ liệu phân tán quy mô lớn: Amazon EMR & Apache Spark](1.8-week8/)**
  * Khởi tạo và quản trị cụm EMR (Elastic MapReduce), chạy các tác vụ Spark & Hadoop xử lý dữ liệu lớn.

* **[Tuần 9: Kho dữ liệu hiện đại (Data Warehousing): Amazon Redshift & Redshift Serverless](1.9-week9/)**
  * Thiết kế cấu trúc bảng, khóa phân vùng (Distribution Keys), Sort Keys và nạp dữ liệu vào Amazon Redshift phục vụ Business Intelligence.

* **[Tuần 10: Điều phối & Tự động hóa đường ống dữ liệu: Amazon MWAA (Airflow)](1.10-week10/)**
  * Xây dựng và quản lý các luồng DAGs điều phối toàn diện hệ thống ETL phức tạp bằng Apache Airflow trên AWS.

* **[Tuần 11: Quản trị dữ liệu, Bảo mật chuyên sâu & Tối ưu chi phí](1.11-week11/)**
  * Phân quyền chi tiết tới cấp dòng/cột với AWS Lake Formation, mã hóa dữ liệu với AWS KMS và tối ưu hóa chi phí vận hành hạ tầng dữ liệu.

* **[Tuần 12: Hoàn thiện Workshop, Capstone Project & Tổng kết thực tập](1.12-week12/)**
  * Tổng kết đồ án thực tập End-to-End Cloud Data Platform, viết tài liệu kỹ thuật và báo cáo bảo vệ thực tập.
