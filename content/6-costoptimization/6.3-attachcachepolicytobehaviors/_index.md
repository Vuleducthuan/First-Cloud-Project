---
title: "Attach Cache Policy to Behaviors"
date: "2025-06-14"
weight: 3
chapter: false
pre: "<b> 6.3 </b>"
---

Go to **CloudFront** > **Distributions**

Open the **Behaviors** tab

Click **Edit** on the desired behavior

**Cache policy name:**  
Select: **CustomLongTTLPolicy**

Click **Save changes**

⚠️ Note: Do not assign this policy to `/index.html` if you need the content to always stay updated.

![s3](/images/6.clean/8.png)

![s3](/images/6.clean/9.png)
