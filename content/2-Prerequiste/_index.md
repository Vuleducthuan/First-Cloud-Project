---
title: "Preparation Steps"
date: "2025-06-14"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

To implement CloudFront Advanced Caching and Security, we need to prepare the basic infrastructure, including an S3 bucket to store the static website and a CloudFront Distribution to deliver content through AWS’s global edge network. In addition, we need to configure appropriate IAM Roles and Policies to ensure that CloudFront, Lambda@Edge, and S3 can interact securely.
![](/images/2.prerequisite/16.png)

### Contents
  - [Create S3](2.1-createbucket/)
  - [Create CloudFront Distribution](2.2-createcloudfrontdistribution/)
