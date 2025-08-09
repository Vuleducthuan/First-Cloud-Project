---
title: "Delete CloudFront Distribution"
date: "2025-06-14"
weight: 8
chapter: false
pre: "<b> 8. </b>"
---

- Go to **CloudFront Console**

![s3](/images/8.cleanupawsresources/1.png)

- Select the created Distribution → **Disable**

![s3](/images/8.cleanupawsresources/2.png)

- After the status changes to **Disabled**, select **Delete**

![s3](/images/8.cleanupawsresources/3.png)

![s3](/images/8.cleanupawsresources/4.png)

## Delete S3 Buckets

- Includes:
  - The bucket containing the static website
  - The bucket containing CloudFront logs
- Go to **S3 Console** → **Empty bucket** → **Delete bucket**

![s3](/images/8.cleanupawsresources/5.png)

**Type: permanently delete**

![s3](/images/8.cleanupawsresources/6.png)

![s3](/images/8.cleanupawsresources/7.png)

Select: **Delete**

![s3](/images/8.cleanupawsresources/8.png)

Bucket name: **webbadmintonvideo**

![s3](/images/8.cleanupawsresources/9.png)

Successfully deleted

![s3](/images/8.cleanupawsresources/10.png)

## Delete Lambda@Edge Functions

- Go to **Lambda Console** in `us-east-1`

- Find the `AddSecurityHeaders` function or other functions used in the lab

- **Delete the published versions**

- Then **Delete function**

![s3](/images/8.cleanupawsresources/11.png)

![s3](/images/8.cleanupawsresources/12.png)

![s3](/images/8.cleanupawsresources/13.png)

## Delete IAM Roles and Policies created for the lab

- Examples:
  - `LambdaEdgeSecurityRole`
  - IAM user/role used for Signed URLs
- Go to **IAM Console** → Delete role

![se3](/images/8.cleanupawsresources/14.png)

![se3](/images/8.cleanupawsresources/15.png)

![se3](/images/8.cleanupawsresources/16.png)

## Delete CloudFront Key Groups and Public Keys

- Go to **CloudFront** → **Key management**
- Delete:
  - Public key (`CloudFrontPublicKey`, `FLE-PublicKey`)
  - Key group (`my-key-group`)

![s3](/images/8.cleanupawsresources/17.png)

![s3](/images/8.cleanupawsresources/18.png)

![s3](/images/8.cleanupawsresources/19.png)

![s3](/images/8.cleanupawsresources/20.png)

![s3](/images/8.cleanupawsresources/21.png)

![s3](/images/8.cleanupawsresources/22.png)

![s3](/images/8.cleanupawsresources/23.png)

![s3](/images/8.cleanupawsresources/24.png)

## Delete Glue and Log Data

- **Glue Crawler (`cf-log-crawler`) → Delete**

- **Glue Database (`cloudfront_logs_db`) → Delete**

![s3](/images/9.deleteglueandlogdata/1.png)

Action: **Delete Crawlers**

![s3](/images/9.deleteglueandlogdata/2.png)

![s3](/images/9.deleteglueandlogdata/3.png)

![s3](/images/9.deleteglueandlogdata/4.png)

## Delete Glue Database

- In **Glue Console** → **Databases** tab

- Find the **database** `cloudfront_logs_db`

- Select **Delete** → Confirm

![s3](/images/9.deleteglueandlogdata/5.png)

![s3](/images/9.deleteglueandlogdata/6.png)

![s3](/images/9.deleteglueandlogdata/7.png)
