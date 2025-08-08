---
title: "Tạo Lambda function"
date: "2025-06-14"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

## Cấu hình Lambda@Edge để thêm Security Headers cho CloudFront

### 🔹 Bước 1: Tạo Lambda Function

1. Truy cập **AWS Lambda**.
2. Chọn **Region**: `US East (N. Virginia)` (`us-east-1`).

![s3](/images/3.connect/1.png)

3. Nhấn **Create function**.
4. Chọn **Author from scratch**, sau đó cấu hình:
   - **Function name**: `AddSecurityHeaders`
   - **Runtime**: `Node.js 18.x`

![s3](/images/3.connect/2.png)

---
