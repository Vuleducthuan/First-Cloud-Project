---
title: "Xóa CloudFront Distribution"
date: "2025-06-14"
weight: 8
chapter: false
pre: "<b> 8. </b>"
---

- Vào **CloudFront Console**

![s3](/images/8.cleanupawsresources/1.png)

- Chọn Distribution đã tạo → **Disable**

![s3](/images/8.cleanupawsresources/2.png)

- • Sau khi trạng thái là Disabled, chọn **Delete**

![s3](/images/8.cleanupawsresources/3.png)

![s3](/images/8.cleanupawsresources/4.png)

## Xóa S3 Buckets

- Bao gồm:
  - Bucket chứa website tĩnh
  - Bucket chứa CloudFront logs
- Vào S3 Console → Empty bucket → Delete bucket

![s3](/images/8.cleanupawsresources/5.png)

**Type: permanently delete**

![s3](/images/8.cleanupawsresources/6.png)

![s3](/images/8.cleanupawsresources/7.png)

Chon: Delete

![s3](/images/8.cleanupawsresources/8.png)

Name bucket: **webbadmintonvideo**

![s3](/images/8.cleanupawsresources/9.png)

Delete thanh cong

![s3](/images/8.cleanupawsresources/10.png)

## Xóa Lambda@Edge Functions

- Vào **Lambda Console** tại `us-east-1`

- Tìm function AddSecurityHeaders hoặc function khác dùng trong lab

- **Xóa các version** đã publish

- Sau đó **Delete function**

![s3](/images/8.cleanupawsresources/11.png)

![s3](/images/8.cleanupawsresources/12.png)

![s3](/images/8.cleanupawsresources/13.png)

## Xóa IAM Roles và Policies tạo cho lab

- Ví dụ:
  - `LambdaEdgeSecurityRole`
  - IAM user/role dùng cho Signed URLs
- Vào **IAM Console** → Delete role

![se3](/images/8.cleanupawsresources/14.png)

![se3](/images/8.cleanupawsresources/15.png)

![se3](/images/8.cleanupawsresources/16.png)

## Xóa CloudFront Key Groups và Public Keys

- Vào **CloudFront** → **Key management**
- Xóa:
  - Public key (CloudFrontPublicKey, FLE-PublicKey)
  - Key group (my-key-group)

![s3](/images/8.cleanupawsresources/17.png)

![s3](/images/8.cleanupawsresources/18.png)

![s3](/images/8.cleanupawsresources/19.png)

![s3](/images/8.cleanupawsresources/20.png)

![s3](/images/8.cleanupawsresources/21.png)

![s3](/images/8.cleanupawsresources/22.png)

![s3](/images/8.cleanupawsresources/23.png)

![s3](/images/8.cleanupawsresources/24.png)

## Xóa Glue và dữ liệu log

- **Glue Crawler (cf-log-crawler) → Delete**

- **Glue Database (cloudfront_logs_db) → Delete**

![s3](/images/9.deleteglueandlogdata/1.png)

Action: Delete Crawlers

![s3](/images/9.deleteglueandlogdata/2.png)

![s3](/images/9.deleteglueandlogdata/3.png)

![s3](/images/9.deleteglueandlogdata/4.png)

## Xóa Glue Database

- Trong **Glue Console** → tab **Databases**

- Tìm **database** cloudfront_logs_db

- Chọn **Delete** → Xác nhận

![s3](/images/9.deleteglueandlogdata/5.png)

![s3](/images/9.deleteglueandlogdata/6.png)

![s3](/images/9.deleteglueandlogdata/7.png)
