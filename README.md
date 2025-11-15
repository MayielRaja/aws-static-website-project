# Project: Deploying a Static Website on AWS

This project demonstrates how to host a secure, high-performance static website using AWS S3, CloudFront, and IAM. This project was completed as part of the Udacity Cloud Computing training.

**Live Website URL:** `dtsmyvykjt1pw.cloudfront.net`

[![ACCESSING WEBSITE VIA CLOUDFRONT](https://github.com/MayielRaja/aws-static-website-project/assets/157897107/1d063071-6c5d-4034-8b6b-163467b7899a)](https://github.com/MayielRaja/aws-static-website-project/assets/157897107/1d063071-6c5d-4034-8b6b-163467b7899a)


---

## 🏛️ Architecture

This project uses a standard AWS architecture for static website hosting:

1.  **Amazon S3:** Used to store the website's static files (HTML, CSS, JS, images).
2.  **Amazon CloudFront:** Used as the Content Delivery Network (CDN) to distribute the website globally, provide a fast user experience, and secure the site with HTTPS.
3.  **AWS IAM:** An IAM policy is used to grant CloudFront permission to read objects from the S3 bucket, keeping the bucket itself private.

---

## ⚙️ Technologies Used

* **AWS S3:** For object storage and static website hosting.
* **AWS CloudFront:** For content delivery and security.
* **AWS IAM:** For creating a secure bucket policy.
* **HTML/CSS/JavaScript:** For the website content.

---

## 🚀 Project Steps

Here are the high-level steps taken to deploy this website:

### 1. Create S3 Bucket

A new S3 bucket (`my-488048024880-bucket`) was created in the `us-east-1` region.

### 2. Upload Website Files

All static files (HTML, CSS, images) for the "Travel Blog" website were uploaded to the S3 bucket.

### 3. Secure Bucket via IAM

The S3 bucket was kept **private** (Block all public access = On). An IAM bucket policy was created to **only** allow access from the CloudFront distribution.

You can see the policy in the `s3-bucket-policy.json` file.

### 4. Configure S3 for Static Hosting

Static website hosting was enabled on the S3 bucket, with `index.html` as the index document.

### 5. Distribute Website via CloudFront

A new CloudFront distribution (`UdacityProject`) was created.

* **Origin:** The S3 bucket was set as the origin.
* **S3 Bucket Access:** "Origin access control settings (recommended)" was used so that CloudFront could securely access the private S3 bucket.

### 6. Access Website

The final website is now accessible globally via the CloudFront URL: `dtsmyvykjt1pw.cloudfront.net`
