---
title: "Grant IAM Permissions to Lambda Function"
date: "2025-06-14"
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

Go to **Roles**  
Search for the role named: **LambdaEdgeSecurityRole**

![s3](/images/3.connect/6.png)

Select the **Trust relationships** tab -> **Edit trust policy**

![s3](/images/3.connect/7.png)

**Replace the trust policy content**:

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": {
                "Service": [
                    "lambda.amazonaws.com",
                    "edgelambda.amazonaws.com"
                ]
            },
            "Action": "sts:AssumeRole"
        }
    ]
}

```

![s3](/images/3.connect/8.png)

**Version description: V1 -> Publish**

![s3](/images/3.connect/9.png)

![s3](/images/3.connect/10.png)