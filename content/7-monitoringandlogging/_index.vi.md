---
title: "Tạo S3 bucket để chứa log"
date: "2025-06-14"
weight: 7
chapter: false
pre: "<b> 7.1 </b>"
---

Vào **AWS S3 Console**

Nhấn **Create bucket**

Nhập tên **bucket**, ví dụ: ``cloudfront-logs-2025-demo``

Tắt **"Block all public access"**

Bật **versioning**

Nhấn **Create bucket**

![s3](/images/7.monitoringandlogging/1.png)

![s3](/images/7.monitoringandlogging/2.png)

## Tạo Glue Database

Vào **AWS Glue Console**

Chọn **tab Databases** → Nhấn **Add database**

Đặt tên: **cloudfront_logs_db**

Nhấn **Create**

![s3](/images/7.monitoringandlogging/3.png)

![s3](/images/7.monitoringandlogging/4.png)

![s3](/images/7.monitoringandlogging/5.png)