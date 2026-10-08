# AWS Static Website Hosting with CloudFront CDN & SSL

This project demonstrates a static website deployment on AWS as part of my DevOps learning hands-on practice.

The objective was to configure a static site using Amazon S3 and distribute it securely using AWS CloudFront CDN.

## Architecture Overview

- **Storage:** Amazon S3 (Static Website Hosting)
- **CDN & Security:** AWS CloudFront (Global Content Delivery, SSL/TLS Encryption, HTTP to HTTPS redirection)
- **Access Control:** IAM Custom Policies (Least Privilege) & S3 Bucket Policies

## Key Project Steps

### 1. S3 Bucket & Static Hosting Setup
- Created an S3 bucket (`udi-s3-static-website`) configured for static website hosting.
- Uploaded `index.html` to serve as the default index document.
- Configured public read permissions via S3 Bucket Policy (`s3:GetObject`).

### 2. IAM Security & Least Privilege
- Applied IAM principles of Least Privilege for deployment access.
- Created a custom deployment policy restricting actions strictly to needed operations (`s3:PutObject`, `s3:DeleteObject`).

### 3. Performance & Optimization
- Enabled **Gzip compression** on static assets prior to upload to reduce transfer size.
- Configured object metadata headers in S3:
  - `Content-Encoding: gzip`
  - `Content-Type: text/html`
  - `Cache-Control: max-age=3600`

### 4. CloudFront CDN & SSL Configuration
- Configured a CloudFront Global Distribution backed by the S3 Origin Endpoint.
- Enforced **SSL/TLS encryption** with **HTTP to HTTPS redirection**.
- Configured `index.html` as the **Default Root Object**.

## Screenshots & Verification

*(Environment was destroyed after testing to manage AWS costs. Below are implementation screenshots)*

<img width="1588" height="443" alt="image" src="https://github.com/user-attachments/assets/0396bffb-3c64-4231-8a78-11e6cc041f96" />
