---
title: "Enable Compression and Redirect to HTTPS"
date: "2025-06-14"
weight: 6
chapter: false
pre: "<b> 6. </b>"
---

Go to the **Behaviors** tab

Find the row with **Path pattern** = Default (\*)

Click **Edit**

![s3](/images/6.clean/1.png)

![s3](/images/6.clean/2.png)

Scroll down to the **Response headers policy** section

- Select: **Managed-SecurityHeadersPolicy**

- Click **Save changes**

![s3](/images/6.clean/3.png)

![s3](/images/6.clean/4.png)

## Create a Custom Cache Policy

Go to **CloudFront** → **Policies** > **Cache policies**

Click **Create cache policy**

![s3](/images/6.clean/5.png)

```

Name: CustomLongTTLPolicy
Description: Long-lived cache for static content
Minimum TTL: 1
Default TTL: 86400
Maximum TTL: 31536000
Headers: None
Query strings: None
Cookies: None
Compression: Gzip, Brotli

```

![s3](/images/6.clean/6.png)

![s3](/images/6.clean/7.png)

## Assign the Cache Policy to Behaviors

Go to **CloudFront** > **Distributions**

Open the **Behaviors** tab

Click **Edit** on the desired behavior

**Cache policy name:**

Select: **CustomLongTTLPolicy**

Click **Save changes**

⚠️ **Note:** Do not assign this policy to `/index.html` if you require the content to always be up to date.

![s3](/images/6.clean/8.png)

![s3](/images/6.clean/9.png)

## Optimize TTL and Limit Logging

### Step 1: Access the log bucket

1. Go to **AWS Console** → **S3**
2. Locate and click on the **bucket**: **webbadmintonvideo**

![s3](/images/6.clean/10.png)

### Step 2: Open the Management tab

1. Inside the **bucket**, select the **Management** tab
2. Click **Create lifecycle rule**

![s3](/images/6.clean/11.png)

### Step 3: Name the rule: ExpireCloudFrontLogs

Check: *Limit the scope of this rule using one or more filters*

Enter: `AWSLogs/your-account-id/CloudFront/`

**Note:** Replace `your-account-id` with your AWS account ID.

In **Lifecycle rule actions**, check: *Expire current versions of objects*

Enter number of days: **30**

![s3](/images/6.clean/12.png)

Confirmation screen showing that the Lifecycle Rule has been successfully configured

![s3](/images/6.clean/13.png)