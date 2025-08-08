---
title: "Create a Custom Cache Policy"
date: "2025-06-14"
weight: 2
chapter: false
pre: "<b> 6.2 </b>"
---

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