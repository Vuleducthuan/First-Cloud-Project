---
title : "Giới thiệu"
date: "2025-06-14"
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

**Amazon CloudFront** là dịch vụ CDN (Content Delivery Network) mạnh mẽ của AWS, được thiết kế để phân phối nội dung với độ trễ thấp và hiệu suất cao trên toàn cầu. Tuy nhiên, CloudFront không chỉ đơn thuần là tốc độ — mà còn cung cấp hai năng lực chiến lược: **Caching nâng cao** và **Bảo mật**, giúp tối ưu lưu lượng, giảm chi phí và bảo vệ hệ thống khỏi các mối đe dọa hiện đại.

---
![](/images/2.prerequisite/0.png)
## Caching Nâng Cao

CloudFront cung cấp nhiều chiến lược cache có thể tùy biến nhằm giảm tải cho origin và cải thiện thời gian phản hồi:

- **Cache theo tham số tùy chỉnh**: Có thể cấu hình cache riêng biệt dựa trên `query strings`, `cookies`, `headers` hoặc loại thiết bị (mobile/desktop).
- **Cache Policies & Origin Request Policies**: Phân tách rõ ràng giữa các yếu tố ảnh hưởng đến cache key và các dữ liệu được gửi về origin → giảm thiểu cache miss không cần thiết.
- **Lambda@Edge / CloudFront Functions**: Cho phép chạy logic tại các edge location (ví dụ: redirect, xác thực token, rewrite URL...) mà không cần gọi đến origin.
- **Field-Level Encryption**: Mã hóa các trường dữ liệu nhạy cảm ngay tại edge → chỉ origin mới có thể giải mã.

*Cache hiệu quả = Phản hồi nhanh hơn + Giảm tải server + Tiết kiệm chi phí.*

---

## Tính Năng Bảo Mật

CloudFront được tích hợp chặt chẽ với hệ sinh thái bảo mật của AWS, mang lại sự bảo vệ toàn diện cho nội dung và người dùng của bạn:

- **AWS WAF**: Tường lửa ứng dụng web giúp chặn các cuộc tấn công như SQL injection, XSS, bot, và DDoS layer 7.
- **Geo Restriction**: Hạn chế quyền truy cập nội dung theo khu vực địa lý — phù hợp với kiểm soát bản quyền hoặc phân phối vùng.
- **HTTPS & TLS (Chứng chỉ SSL)**: Hỗ trợ HTTPS đầy đủ với chứng chỉ tùy chỉnh và các phiên bản TLS mới nhất.
- **Signed URLs / Signed Cookies**: Cung cấp nội dung riêng tư một cách an toàn thông qua các cơ chế truy cập có thời hạn.
- **AWS Shield Standard**: Bảo vệ chống lại các cuộc tấn công DDoS tầng 3 và 4 miễn phí cho mọi distribution.

*CloudFront không chỉ nhanh — mà còn được gia cố bằng hệ thống bảo mật mạnh mẽ.*

---

