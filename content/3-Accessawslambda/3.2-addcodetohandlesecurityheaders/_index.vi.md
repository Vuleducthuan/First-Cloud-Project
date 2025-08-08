---
title: "Thêm mã nguồn xử lý security headers"
date: "2025-06-14"
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

Thêm mã vào Lambda

```
'use strict';
export const handler = async (event) => {
    const response = event.Records[0].cf.response;
    const headers = response.headers;
    headers['strict-transport-security'] = [
        { key: 'Strict-Transport-Security', value: 'max-age=63072000; includeSubDomains; preload' }
    ];
    headers['content-security-policy'] = [
        { key: 'Content-Security-Policy', value: "default-src 'self'" }
    ];
    headers['x-content-type-options'] = [
        { key: 'X-Content-Type-Options', value: 'nosniff' }
    ];
    headers['x-frame-options'] = [
        { key: 'X-Frame-Options', value: 'DENY' }
    ];
    headers['x-xss-protection'] = [
        { key: 'X-XSS-Protection', value: '1; mode=block' }
    ];
    return response;
};
```
![s3](/images/3.connect/3.png)

![s3](/images/3.connect/4.png)


Nhấn nút **Deploy (Ctrl + Shift + U)** để cập nhật function.

![s3](/images/3.connect/5.png)
