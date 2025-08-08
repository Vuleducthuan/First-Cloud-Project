---
title : "Field-Level Encryption"
date: "2025-06-14"
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---
Open Git Bash and run the following two commands:

``openssl genrsa -out private_key.pem 2048``

``openssl rsa -pubout -in private_key.pem -out public_key.pem``

![s3](/images/5.fwd/1.png)

![s3](/images/5.fwd/2.png)

![s3](/images/5.fwd/3.png)

Go to the **Public keys tab** → click **Create public key**

Paste the content from the **public_key.pem** file you just created

Name it: **FLE-PublicKey**

Click **Create public key**

![s3](/images/5.fwd/4.png)

![s3](/images/5.fwd/5.png)
