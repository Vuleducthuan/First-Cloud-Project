---
title : "Truy cập AWS Lambda"
date: "2025-06-14"
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---

Giới thiệu:
Trong bước này, chúng ta sẽ triển khai AWS Lambda@Edge để thực hiện xử lý nâng cao trên request và response của CloudFront Distribution. Mục tiêu chính là thêm các security headers vào phản hồi trả về cho người dùng, giúp tăng cường bảo mật website phân phối qua CloudFront.

![](/images/3.connect/27.png)

### Nội dung
3.1. [Tạo Lambda function](3.1-createalambdafunction/)

3.2. [Thêm mã nguồn xử lý security headers](3.2-addcodetohandlesecurityheaders/)

3.3. [Cấp quyền IAM cho Lambda function](3.3-grantiampermissionstothelambdafunction/)

3.4. [Gán Lambda vào Behavior trong CloudFront](3.4-attachlambdatoabehaviorincloudfront/)

3.5[Tạo và gán Origin Access Identity](3.5-createandassignoriginaccessidentity/)