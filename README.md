# 🌐 Static Website Hosting with Amazon S3

This project demonstrates how to host a static website on **Amazon S3** using simple HTML, CSS. It's part of my AWS Restart Journey.

### 1. Create an S3 Bucket
- Use a globally unique bucket name (e.g., zoefitness123).
- Select your preferred AWS region.
- Disable “Block all public access” under permissions.

### 2. Upload Website Files
- Add your static files (HTML, CSS) to the bucket.
- Make sure your main file is named `index.html`.

### 3. Enable Static Website Hosting
- Go to the bucket **Properties** tab.
- Enable **Static Website Hosting**.
- Set:
  - **Index document**: `index.html`
  - **Error document** (optional): `error.html`

### 4. Configure Bucket Policy
Add a policy to make your site publicly accessible:
```json
{
  "Version": "2012-10-17",
  "Statement": [{
    "Sid": "PublicReadGetObject",
    "Effect": "Allow",
    "Principal": "*",
    "Action": "s3:GetObject",
    "Resource": "arn:aws:s3:::zoefitness123*"
  }]
}

