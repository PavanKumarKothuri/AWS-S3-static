# AWS-S3-static

# Static Website Hosting on AWS S3 with Custom Domain

This project demonstrates how to host a static website on AWS S3 and map it to a custom domain using Route 53. It is a beginner-friendly project designed to showcase AWS cloud capabilities and create an impressive portfolio item for job applications.

---

## **Project Overview**

- **Technology Stack**:  
  - AWS S3: For static website hosting.  
  - Route 53: For domain name system (DNS) management.  
  - HTML: For static website content.

- **Features**:  
  - Simple static website hosting.  
  - Custom domain integration.  
  - Public access configuration via bucket policy.  
  - Error handling with a custom error page.

---

## **Steps to Reproduce**

Follow these steps to replicate the project:

### **1. Create and Configure an S3 Bucket**
1. Log in to [AWS Management Console](https://aws.amazon.com/console/).  
2. Create an S3 bucket with a unique name and uncheck “Block all public access.”  
3. Enable **Static website hosting** in the bucket properties.  
4. Add an `index.html` (main page) and `error.html` (error page) to the bucket.  

### **2. Configure Bucket Policy**
Add the following bucket policy to allow public access to the website:  
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::BUCKET_NAME/*"
        }
    ]
}
```

Replace `BUCKET_NAME` with your actual bucket name.

### **3. Set Up a Custom Domain**
1. Purchase a domain or use an existing one.  
2. Configure a **Hosted Zone** in Route 53 for your domain.  
3. Add an Alias record to link your domain to the S3 bucket’s website endpoint.  

---

## **HTML Files**

### **index.html**  
This file serves as the main page of the website:  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Static Website</title>
</head>
<body>
    <h1>Welcome to My Static Website!</h1>
    <p>This website is hosted on AWS S3.</p>
</body>
</html>
```

### **error.html**  
This file serves as the error page for the website:  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Error</title>
</head>
<body>
    <h1>Oops! Something went wrong.</h1>
    <p>Please try again later.</p>
</body>
</html>
```

---

## **Testing**
1. Access the website using your custom domain (e.g., `http://mywebsite.com`).  
2. Test error handling by visiting a non-existent page (e.g., `http://mywebsite.com/nonexistent`).  

---

## **Learning Outcomes**
- Setting up AWS S3 for static website hosting.  
- Configuring Route 53 for DNS management.  
- Writing and applying bucket policies for public access.  
- Deploying a fully functional website with a custom domain.  

---

## **License**
This project is open-source and free to use under the [MIT License](LICENSE).

---

## **📫 Author**
- PavanKumar Kothuri
- **Email:** pavankumarkothuri9@gmail.com
- [GitHub Profile](https://github.com/PavanKumarKothuri)
- [LinkedIn Profile](https://www.linkedin.com/in/iamkpk/)
Feel free to connect with me or open an issue or pull request on this repository for further discussions or contributions.

