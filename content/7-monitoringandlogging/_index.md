---
title: "Create an S3 Bucket for Logs"
date: "2025-06-14"
weight: 7
chapter: false
pre: "<b> 7. </b>"
---

Go to **AWS S3 Console**

Click **Create bucket**

Enter the **bucket name**, for example: `cloudfront-logs-2025-demo`

Disable **"Block all public access"**

Enable **versioning**

Click **Create bucket**

![s3](/images/7.monitoringandlogging/1.png)

![s3](/images/7.monitoringandlogging/2.png)

## Create a Glue Database

Go to **AWS Glue Console**

Select the **Databases** tab → Click **Add database**

Name it: **cloudfront_logs_db**

Click **Create**

![s3](/images/7.monitoringandlogging/3.png)

![s3](/images/7.monitoringandlogging/4.png)

![s3](/images/7.monitoringandlogging/5.png)