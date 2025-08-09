---
title : "Các bước chuẩn bị"
date: "2025-06-14"
weight : 2 
chapter : false
pre : " <b> 2. </b> "
---


Để triển khai CloudFront Advanced Caching và Security, chúng ta cần chuẩn bị hạ tầng cơ bản bao gồm S3 bucket để lưu trữ website tĩnh và CloudFront Distribution để phân phối nội dung qua mạng lưới edge toàn cầu của AWS. Ngoài ra, chúng ta cũng cần thiết lập IAM Role và Policy phù hợp để đảm bảo CloudFront, Lambda@Edge và S3 có thể tương tác an toàn.
![](/images/2.prerequisite/16.png)

### Nội dung
  - [Tạo S3](2.1-createbucket/)
  - [Tạo CloudFront Distribution](2.2-createcloudfrontdistribution/)

  
