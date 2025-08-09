---
title: "Tạo CloudFront Key Pair"
date: "2025-06-14"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

## Bước 1: Tạo CloudFront Key Pair

Vào tab **Security** → **Key management**

Nhấn **Create public key**

Đặt tên: **CloudFrontPublicKey**

**Tải file .pem (public key)**

![s3](/images/4.s3/1.png)

![s3](/images/4.s3/2.png)

![s3](/images/4.s3/3.png)

![s3](/images/4.s3/4.png)

![s3](/images/4.s3/5.png)

## Bước 2: Dán vào key

**Xong creat public key**

![s3](/images/4.s3/6.png)

![s3](/images/4.s3/7.png)

## Tạo key group

![s3](/images/4.s3/8.png)

1. Điền thông tin:

**Name: my-key-group**

**Description (optional): Key group for signed URL**

**Public keys: Tick chọn public key bạn vừa tạo (ví dụ: my-signed-url-key)**

2. Nhấn Create key group

![s3](/images/4.s3/9.png)

## Gán Key Group vào CloudFront Behavior

Vào **CloudFront** > **Distributions**
Chọn tab **Behaviors**

![s3](/images/4.s3/10.png)

![s3](/images/4.s3/11.png)

- Cuộn xuống phần **Restrict viewer access (use signed URLs or signed cookies)**

- Chọn **Yes**

- Phần **Trusted key groups**

- Tick chọn **key group bạn vừa tạo (my-key-group)**

- Nhấn **Save changes**

![s3](/images/4.s3/12.png)

## Tạo Signed URL bằng Python

**Cần cài Python**

`link :https://www.python.org/downloads/windows/`

![s3](/images/4.s3/13.png)

Sau khi xong buoc cai dat tren

Mở terminal

**Chạy lệnh sau để cài thư viện:**

**pip install cryptography**

![s3](/images/4.s3/14.png)

![s3](/images/4.s3/15.png)

Vào thư mục chứa file **private_key.pem**, mở VS Code

![s3](/images/4.s3/16.png)

```
import base64
import time
from cryptography.hazmat.primitives import serialization, hashes
from cryptography.hazmat.primitives.asymmetric import padding
cloudfront_url = "https://dwlpqynbljc1b.cloudfront.net/index.html"
key_pair_id = "K31UET7UCHMLP6"
private_key_file = "private_key.pem"
expire_time = int(time.time()) + 3600
policy = f'''{{"Statement":[{{"Resource":"{cloudfront_url}","Condition":{{"DateLessThan":{{"AWS:EpochTime":{expire_time}}}}}}}]}}'''
with open(private_key_file, "rb") as key_file:
    private_key = serialization.load_pem_private_key(
        key_file.read(),
        password=None,
    )
signature = private_key.sign(
    policy.encode(),
    padding.PKCS1v15(),
    hashes.SHA1()
)
def url_safe_b64encode(data):
    return base64.b64encode(data).decode("utf-8")\
        .replace("+", "-")\
        .replace("=", "_")\
        .replace("/", "~")
encoded_signature = url_safe_b64encode(signature)
encoded_policy = url_safe_b64encode(policy.encode())

signed_url = f"{cloudfront_url}?Policy={encoded_policy}&Signature={encoded_signature}&Key-Pair-Id={key_pair_id}"
print("🎯 Signed URL:")
print(signed_url)

```

**Luu y**:

- Domain name trong AWS CloudFront

- Key pair ID

thư mục chứa file **.py**, bạn chạy:

![s3](/images/4.s3/17.png)

Nó sẽ in ra:

![s3](/images/4.s3/18.png)
