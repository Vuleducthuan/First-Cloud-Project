---
title: "Cấp quyền IAM cho Lambda function"
date: "2025-06-14"
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

Vào **Roles**
Tìm role có tên: **LambdaEdgeSecurityRole**

![s3](/images/3.connect/6.png)

Chọn tab **Trust relationships** -> **Edit trust policy**

![s3](/images/3.connect/7.png)

**Thay nội dung trust policy**

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

**Version descripsion: V1-> Publish**

![s3](/images/3.connect/9.png)

![s3](/images/3.connect/10.png)