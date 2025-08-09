---
title: "Create CloudFront Key Pair"
date: "2025-06-14"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

## Step 1: Create a CloudFront Key Pair

Go to the **Security** tab → **Key management**

Click **Create public key**

Name: **CloudFrontPublicKey**

**Download the .pem file (public key)**

![s3](/images/4.s3/1.png)

![s3](/images/4.s3/2.png)

![s3](/images/4.s3/3.png)

![s3](/images/4.s3/4.png)

![s3](/images/4.s3/5.png)

## Step 2: Paste into the key

**After creating the public key**

![s3](/images/4.s3/6.png)

![s3](/images/4.s3/7.png)

## Create a Key Group

![s3](/images/4.s3/8.png)

1. Fill in the details:

**Name:** my-key-group

**Description (optional):** Key group for signed URL

**Public keys:** Select the public key you just created (e.g., my-signed-url-key)

2. Click **Create key group**

![s3](/images/4.s3/9.png)

## Assign the Key Group to a CloudFront Behavior

Go to **CloudFront** > **Distributions**  
Open the **Behaviors** tab

![s3](/images/4.s3/10.png)

![s3](/images/4.s3/11.png)

- Scroll down to **Restrict viewer access (use signed URLs or signed cookies)**
- Select **Yes**
- In **Trusted key groups**
- Check the key group you just created (**my-key-group**)
- Click **Save changes**

![s3](/images/4.s3/12.png)

## Generate a Signed URL with Python

**Install Python first**

`link: https://www.python.org/downloads/windows/`

![s3](/images/4.s3/13.png)

After installation,

Open the terminal and run the following command to install the library:

**pip install cryptography**

![s3](/images/4.s3/14.png)

![s3](/images/4.s3/15.png)

Navigate to the folder containing **private_key.pem**, then open VS Code

![s3](/images/4.s3/16.png)

```python
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
**Notes:

- The domain name must match the one in AWS CloudFront

- Use the correct Key Pair ID

In the folder containing the **.py** file, run:

![s3](/images/4.s3/17.png)

It will output:

![s3](/images/4.s3/18.png)