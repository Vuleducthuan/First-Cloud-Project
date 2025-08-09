---
title: "Bật Compression và Redirect HTTPS"
date: "2025-06-14"
weight: 6
chapter: false
pre: "<b> 6. </b>"
---

Vào tab **Behaviors**

Tìm dòng có **Path pattern** = Default (\*)

Nhấn **Edit**

![s3](/images/6.clean/1.png)

![s3](/images/6.clean/2.png)

Cuộn xuống phần Response headers policy

- Chọn: **Managed-SecurityHeadersPolicy**

- Nhấn **Save changes**

![s3](/images/6.clean/3.png)

![s3](/images/6.clean/4.png)

## Tạo Custom Cache Policy

Vào **CloudFront** → **Policies** > **Cache policies**

Nhấn **Create cache policy**

![s3](/images/6.clean/5.png)

```
Name:CustomLongTTLPolicy
Description:Long-lived cache for static content
Minimum TTL: 1
Default TTL:86400
Maximum TTL:31536000
Headers:None
Query strings:None
Cookies:None
Compression:Gzip, Brotli

```
![s3](/images/6.clean/6.png)

![s3](/images/6.clean/7.png)

## Gán Cache Policy vào các Behavior

Truy cập **CloudFront** > **Distributions**

Vào **tab Behaviors**

Nhấn **Edit** ở behavior

**Cache policy name:**

Chọn: **CustomLongTTLPolicy**

Nhấn **Save changes**

⚠️ Lưu ý: Không nên gán policy này cho /index.html nếu bạn cần nội dung luôn cập nhật.

![s3](/images/6.clean/8.png)

![s3](/images/6.clean/9.png)

## Tối ưu TTL và giới hạn Logging

## Bước 1: Truy cập bucket log

1.	Vào **AWS Console** → **S3**

2.	Tìm và nhấn vào **bucket** : **webbadmintonvideo**

![s3](/images/6.clean/10.png)

## Bước 2: Mở tab Management
1.	Trong **bucket** → chọn **tab Management**

2.	Nhấn nút **Create lifecycle rule**

![s3](/images/6.clean/11.png)

## Bước 3: Đặt tên rule: ExpireCloudFrontLogs

Tick: Limit the scope of this rule using one or more filters

AWSLogs/your-account-id/CloudFront/

**Lưu ý**: Thay” your-account-id” bằng mã tài khoản AWS

**Lifecycle rule actions**, tick: Expire current versions of objects

Nhập số ngày:30

![s3](/images/6.clean/12.png)

Giao diện xác nhận Lifecycle Rule đã được cấu hình thành công

![s3](/images/6.clean/13.png)