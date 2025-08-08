---
title: "Optimize TTL and Limit Logging"
date: "2025-06-14"
weight: 4
chapter: false
pre: "<b> 6.4 </b>"
---

## Step 1: Access the log bucket

1. Go to **AWS Console** → **S3**

2. Find and click on the **bucket**: **webbadmintonvideo**

![s3](/images/6.clean/10.png)

## Step 2: Open the Management tab

1. Inside the **bucket**, go to the **Management** tab

2. Click the **Create lifecycle rule** button

![s3](/images/6.clean/11.png)

## Step 3: Name the rule: ExpireCloudFrontLogs

Check: **Limit the scope of this rule using one or more filters**

Prefix: `AWSLogs/your-account-id/CloudFront/`  
**Note**: Replace `your-account-id` with your actual AWS account ID.

Under **Lifecycle rule actions**, check:  
**Expire current versions of objects**

Enter number of days: **30**

![s3](/images/6.clean/12.png)

The confirmation screen shows that the Lifecycle Rule has been successfully configured:

![s3](/images/6.clean/13.png)
