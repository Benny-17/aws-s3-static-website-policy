# 🌐 AWS S3 Static Website Policies  

> Secure S3 bucket setup with restricted access and public read for static website hosting.  

---

## 🏆 **Overview**  
This repository contains two AWS S3 bucket policies for setting up a secure static website:  

- ✅ **Root-Only Access Policy** – Ensures only the root user can modify or delete objects.  
- ✅ **Static Website Read Policy** – Allows public read-only access to bucket objects for static hosting.  

---

## ### 📁 **Folder Structure**  

aws-s3-static-website-policy/
├── README.md
└── policies
    ├── root-only-access-policy.json
    └── static-website-read-policy.json


---

## 🚀 **Setup Guide**  
### **1. Create an S3 Bucket**
- Go to AWS Management Console → S3 → Create Bucket.  
- Enable static website hosting under **Properties**.  

### **2. Apply Policies**
- Open the **Permissions** tab in the S3 bucket settings.  
- Copy the contents of each policy file and add them under **Bucket Policy**:  
  - `policies/root-only-access-policy.json`  
  - `policies/static-website-read-policy.json`  

### **3. Upload Your Static Website Files**
- Use the AWS CLI or console to upload files:  
```bash
aws s3 sync ./my-website/ s3://your-bucket-name

🌟 How It Works

Policy 

Root-Only Access Policy:	Restricts modification, deletion, and object ACL changes to root user only	Even full-access IAM users cannot modify/delete objects

Static Website Read Policy:	Allows public GET requests for static files	Website files are readable to the public

🔒 Security Best Practices
✔️ Keep the bucket private except for s3:GetObject for public access.
✔️ Enable MFA Delete for extra protection.
✔️ Use CloudTrail to monitor access logs.

