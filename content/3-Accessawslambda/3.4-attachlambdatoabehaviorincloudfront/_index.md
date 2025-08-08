---
title: "Associate Lambda with a Behavior in CloudFront"
date: "2025-06-14"
weight: 4
chapter: false
pre: " <b> 3.4. </b> "
---

Go to CloudFront -> Select the **distribution** -> Open the **Behaviors** tab -> Click on **/index.html** -> Click **Edit**.

![s3](/images/3.connect/11.png)

Function type: ``Lambda@Edge``  
Function ARN: ``arn:aws:lambda:us-east-1:806361468439:function:AddSecurityHeaders:3``  
Click: **Save changes**

![s3](/images/3.connect/12.png)
