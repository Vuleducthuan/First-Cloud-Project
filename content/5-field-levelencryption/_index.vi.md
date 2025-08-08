---
title : "Field-Level Encryption"
date: "2025-06-14"
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---
Mở Git Bash Chay 2 lenh:

**openssl genrsa -out private_key.pem 2048**

**openssl rsa -pubout -in private_key.pem -out public_key.pem**

![s3](/images/5.fwd/1.png)

![s3](/images/5.fwd/2.png)

![s3](/images/5.fwd/3.png)

Vào **tab Public keys** → nhấn **Create public key**

Dán nội dung trong **public_key.pem** bạn vừa tạo

Đặt tên: **FLE-PublicKey**

Nhấn **Create public key**

![s3](/images/5.fwd/4.png)

![s3](/images/5.fwd/5.png)
