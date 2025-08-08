---
title: "Tạo Glue Crawler"
date: "2025-06-14"
weight: 3
chapter: false
pre: "<b> 7.3 </b>"
---
Vào **Glue** → **tab Crawlers** → **click Create crawler**

 1. Crawler info
-	Name: cf-log-crawler
-	Description – optional: Crawler to scan CloudFront access logs in S3 and build Athena table.

![s3](/images/7.monitoringandlogging/6.png)

![s3](/images/7.monitoringandlogging/7.png)

Dán đường dẫn đến thư mục chứa CloudFront logs của bạn

![s3](/images/7.monitoringandlogging/8.png)

![s3](/images/7.monitoringandlogging/9.png)

![s3](/images/7.monitoringandlogging/10.png)

![s3](/images/7.monitoringandlogging/11.png)

![s3](/images/7.monitoringandlogging/12.png)

Nhấn nút **Run crawler**

Đợi khoảng **1–3 phút**

![s3](/images/7.monitoringandlogging/13.png)
