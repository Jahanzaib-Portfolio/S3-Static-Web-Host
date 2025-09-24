# 🌐 S3 Static Website Hosting

## 📖 Project Overview
This project demonstrates how to host a static website on **Amazon S3** using AWS services.  
With this setup, you can serve HTML and image files directly from an S3 bucket, making your website **scalable, cost-effective, and highly available**.

---

## 🛠️ Services Used
- **Amazon S3** → To store and host static website files (HTML and Images).

---

## 🚀 Steps to Implement

### 1. Create an S3 Bucket
- Go to **AWS Console → S3 → Create Bucket**.  
- Give it a unique name, for example: `static-website-hosting-1510`.  
- Choose the region closest to your audience.  

![Create Bucket](images/screenshot1.png)

- **Uncheck** “Block all public access” (to make the website publicly available).  

![Block Public Access](images/screenshot2.png)

- Upload your `index.html`, `404.html` (error file), and image files into the bucket.  

![Upload Files](images/screenshot3.png)

---

### 2. Enable Static Website Hosting
- Go to the **Properties** tab of the bucket.  

![Properties Tab](images/screenshot4.png)

- Scroll to **Static website hosting → Enable**.  
- Select **Host a static website**.  
- Set `index.html` as the **Index Document**.  
- Set `404.html` as the **Error Document**.  

![Enable Hosting](images/screenshot5.png)  
![Set Documents](images/screenshot6.png)

---

### 3. Copy the Website Endpoint
- After enabling hosting, copy the **Bucket Website Endpoint** (this is your site URL).  

![Website Endpoint](images/screenshot7.png)

- You might see an error — this happens because the bucket policy isn’t configured yet.  

![Access Denied](images/screenshot8.png)

---

### 4. Configure Bucket Policy
- Go to **Permissions → Bucket Policy**.  

![Bucket Policy Tab](images/screenshot9.png)

- Use your **bucket ARN number** in the policy.  

![Bucket ARN](images/screenshot10.png)

- Open the **Policy Generator** to create a policy.  

![Policy Generator](images/screenshot11.png)  
![Generated Policy](images/screenshot12.png)

- Apply the policy → Now public users can access your files.  

![Policy Applied](images/screenshot13.png)

---

### 5. Verify the Website
- Open the bucket endpoint in a browser → your webpage is live!  

![Live Website](images/screenshot14.png)

- Try visiting a missing page → you should see the error page.  

![Error Page](images/screenshot15.png)

- Now both index and error pages are working correctly.  

![Both Pages](images/screenshot16.png)

- Final confirmation of website running.  

![Final Result](images/screenshot17.png)

---

## 🎯 Benefits
- No servers to manage.  
- Highly scalable and durable.  
- Low-cost static site hosting.  

---

## 🧑‍💻 Key Learnings

### Amazon S3 Basics
- How to create and configure an S3 bucket.  
- Understanding bucket naming rules and region selection.  

### Static Website Hosting
- Enabling Static Website Hosting in S3.  
- Setting up `index.html` as the default root document.  
- Adding an error page (e.g., `404.html`) for better user experience.  

### Bucket Policy & Permissions
- Writing and applying an S3 bucket policy to allow public read access.  
- Understanding the difference between **Block Public Access** settings and bucket policies.  

### File Upload & Access
- Uploading website files to S3.  
- Accessing the website via the S3 website endpoint URL.  

### Security Considerations
- Limiting permissions only to necessary actions.  
- Understanding why **HTTPS is not supported** directly on S3 website endpoints, and how **CloudFront** can solve it.  

### Practical Cloud Skills
- Hands-on experience with AWS Management Console.  
- Realizing how cloud services can replace traditional web servers.  
