# 🌐 AWS S3 Setup Guide
This guide demonstrates how to host the Serverless Superhero Gallery on AWS S3 using both the AWS Management Console (manual approach) and AWS CLI (programmatic approach). Screenshots and explanations are included to showcase understanding.

## 🛠️ Steps for AWS S3 Hosting (Manual Approach)
### 1️⃣ Creating an S3 Bucket
Steps:
- **Log in to the AWS Management Console.**
- **Go to S3 → Click Create bucket.**
- **Enter the bucket name (e.g., superherogalleryvs).**
- **Select the desired region e.g., Africa (Cape Town).**
- **Uncheck Block all public access.**
- **Complete the process by clicking Create bucket.**

Screenshot: S3_Bucket_Created
- **"Created an S3 bucket using the AWS Management Console."**

### 2️⃣ Uploading Files to S3 Bucket
Steps:
- **Open the newly created bucket in the S3 console.**
- **Click Upload → Add files → Select your website files (HTML, CSS, JS, images).**
- **Click Upload to add the files.**

Screenshot: File_Upload
- **"Uploaded all files to the S3 bucket manually."**

### 3️⃣ Enabling Static Website Hosting
Steps:
- **Navigate to the Properties tab of the bucket.**
- **Scroll to Static website hosting → Click Edit.**
- **Enable Static website hosting.**
- **Enter index.html as the Index document.**
- **Save the changes.**

Screenshot: Static_Website_Hosting
- **"Configured static website hosting via the AWS Console."**

### 4️⃣ Setting Permissions 
Steps:
-**Go to the Permissions tab of the bucket.**
-**Under Bucket policy, edit "Block public access (bucket settings)" and enable public:**

Screenshot: Permission_Access
- **"Added a bucket policy to allow public access manually."**

---

## 🛠️ Steps for AWS S3 Hosting (CLI Approach)
## 1️⃣ Creating an S3 Bucket
```bash
aws s3 mb s3://superherogalleryvs
###What it does: Creates a bucket named superherogalleryvs using AWS CLI.
```
Screenshot: VS_S3_Bucket

## 2️⃣&3️⃣ Uploading Files to S3 Bucket & Enabling Static Website Hosting
```bash
aws s3 website s3://superherogalleryvs --index-document index.html
###What it does: Configures the bucket for static website hosting and sets index.html as the default landing page.
```
```bash
aws s3 cp . s3://superherogalleryvs --recursive
###What it does: Uploads all project files in the current directory to the S3 bucket via CLI.
```

Screenshot: Uploading&Website_Hosting

## 4️⃣ Adding a Bucket Policy
Steps:
- **Create a file named bucket-policy.json with this content: "refer to bucket-policy.json"**
Apply the policy using:
```bash
aws s3api put-bucket-policy --bucket superherogalleryvs --policy file://bucket-policy.json
```
Screenshot: Bucket_policy

---

## 📸 Visuals
All screenshots are stored in the /screenshots

---

## ✅ Next Steps
Integrate AWS Lambda for dynamic functionality.
Add CI/CD pipeline using GitHub Actions.