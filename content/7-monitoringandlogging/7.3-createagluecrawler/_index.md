---
title: "Create Glue Crawler"
date: "2025-06-14"
weight: 3
chapter: false
pre: "<b> 7.3 </b>"
---

Go to **Glue** → **Crawlers tab** → **Click Create crawler**

### 1. Crawler info

- **Name**: cf-log-crawler
- **Description (optional)**: Crawler to scan CloudFront access logs in S3 and build an Athena table.

![s3](/images/7.monitoringandlogging/6.png)

![s3](/images/7.monitoringandlogging/7.png)

Paste the path to the folder that contains your CloudFront logs

![s3](/images/7.monitoringandlogging/8.png)

![s3](/images/7.monitoringandlogging/9.png)

![s3](/images/7.monitoringandlogging/10.png)

![s3](/images/7.monitoringandlogging/11.png)

![s3](/images/7.monitoringandlogging/12.png)

Click the **Run crawler** button

Wait about **1–3 minutes**

![s3](/images/7.monitoringandlogging/13.png)
