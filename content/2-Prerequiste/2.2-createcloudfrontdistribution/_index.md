---
title: "Create CloudFront Distribution"
date: "2025-06-14"
weight: 2
chapter: false
pre: " <b> 2.2 </b> "
---

## Step 1: Create a CloudFront Distribution

- **Click on**: `Create a CloudFront distribution`  
  ![s3](/images/2.prerequisite/6.png)

- **Distribution name**: `webbadmintonvideo_Distribution`
- **Description**: `CDN for static site hosted on S3`
- **Distribution type**: Select `Single website or app`
- **Click**: `Next`

![s3](/images/2.prerequisite/7.png)

---

## Step 2: Select Origin

- **Choose**: `Amazon S3`

![s3](/images/2.prerequisite/8.png)

- **S3 origin**: `webbadmintonvideo.s3-website-us-east-1.amazonaws.com`
- **Check**: `Enable security protections`

![s3](/images/2.prerequisite/9.png)

---

## Step 3: Review Your Settings

- Distribution name
- Origin
- Security settings

![s3](/images/2.prerequisite/10.png)

![s3](/images/2.prerequisite/11.png)

---

## Step 4: Select Legacy Access Identities

![s3](/images/2.prerequisite/12.png)

![s3](/images/2.prerequisite/13.png)

---

## Step 5: Add Path Pattern for Images

- **Path pattern**: `/images/*`
- **Origin**: `webbadmintonvideo.s3-website-us-east-1.amazonaws.com`
- **Compress objects automatically**: `Yes`
- **Viewer protocol policy**: `Redirect HTTP to HTTPS`
- **Allowed HTTP methods**: `GET, HEAD`
- **Restrict viewer access**: `No`

![s3](/images/2.prerequisite/14.png)

![s3](/images/2.prerequisite/15.png)
