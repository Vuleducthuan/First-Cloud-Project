---
title: "Tối ưu TTL và giới hạn Logging"
date: "2025-06-14"
weight: 4
chapter: false
pre: "<b> 6.4 </b>"
---
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
