---
title: "Tạo CloudFront Distribution"
date: "2025-06-14"
weight: 2
chapter: false
pre: " <b> 2.2 </b> "
---

## Bước 1: Tạo CloudFront Distribution

- **Click vào**: **Create a CloudFront distribution**

  ![S3](/images/2.prerequisite/6.png)

- **Distribution name**: **webbadmintonvideo_Distribution**
- **Description**: **CDN for static site hosted on S3**
- **Distribution type**: Chọn **Single website or app**
- **Nhấn**: **Next**

![s3](/images/2.prerequisite/7.png)

---

## Bước 2: Chọn Origin

- **Chọn**: **Amazon S3**

![s3](/images/2.prerequisite/8.png)

- **S3 origin**: **webbadmintonvideo.s3-website-us-east-1.amazonaws.com**
- **Chọn**: **Enable security protections**

![s3](/images/2.prerequisite/9.png)

---

## Bước 3: Kiểm tra lại các thông tin

- Tên Distribution
- Origin
- Các cài đặt bảo mật

![s3](/images/2.prerequisite/10.png)

![s3](/images/2.prerequisite/11.png)

---

## Bước 4: Chọn Legacy access identities

![s3](/images/2.prerequisite/12.png)

![s3](/images/2.prerequisite/13.png)

---

## Bước 5: Thêm Path Pattern cho hình ảnh

- **Path pattern**: __/images/__*
- **Origin**: `webbadmintonvideo.s3-website-us-east-1.amazonaws.com`
- **Compress objects automatically**: `Yes`
- **Viewer protocol policy**: `Redirect HTTP to HTTPS`
- **Allowed HTTP methods**: `GET, HEAD`
- **Restrict viewer access**: `No`

![s3](/images/2.prerequisite/14.png)

![s3](/images/2.prerequisite/15.png)
