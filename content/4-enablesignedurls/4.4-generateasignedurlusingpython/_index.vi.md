---
title: "Tạo Signed URL bằng Python"
date: "2025-06-14"
weight: 4
chapter: false
pre: " <b> 4.4 </b> "
---

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
