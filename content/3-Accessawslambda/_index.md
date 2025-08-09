---
title: "Access AWS Lambda"
date: "2025-06-14"
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Introduction:  
In this step, we will deploy AWS Lambda@Edge to perform advanced processing on requests and responses of the CloudFront Distribution.  
The main goal is to add security headers to the responses returned to the users, thereby enhancing the security of the website distributed via CloudFront.

![](/images/3.connect/27.png)

### Content
3.1. [Create a Lambda function](3.1-createalambdafunction/)

3.2. [Add code to handle security headers](3.2-addcodetohandlesecurityheaders/)

3.3. [Grant IAM permissions to the Lambda function](3.3-grantiampermissionstothelambdafunction/)

3.4. [Attach the Lambda to a Behavior in CloudFront](3.4-attachlambdatoabehaviorincloudfront/)

3.5. [Create and assign an Origin Access Identity](3.5-createandassignoriginaccessidentity/)
