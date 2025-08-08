---
title: "Enable Compression and Redirect to HTTPS"
date: "2025-06-14"
weight: 1
chapter: false
pre: "<b> 6.1 </b>"
---

Go to the **Behaviors** tab

Find the row with **Path pattern** = Default (`*`)

Click **Edit**

![s3](/images/6.clean/1.png)

![s3](/images/6.clean/2.png)

Scroll down to the **Response headers policy** section

- Select: `Managed-SecurityHeadersPolicy`  
Click **Save changes**

![s3](/images/6.clean/3.png)

![s3](/images/6.clean/4.png)