# 🚀 Serverless Website Uptime Monitor & Real-time Alerting System

![Project Banner](./Readme-images/lambda-monitoring.png)

## 🌐 Introduction
This is a professional, cloud-native uptime monitoring solution. It autonomously tracks the availability of websites and sends instant email notifications if a downtime occurs. Built using a serverless architecture, it ensures 24/7 reliability with zero server maintenance.

### 🌍 Real-World Use Cases
* **E-commerce Monitoring:** Ensure online stores never miss a sale due to undetected downtime.
* **Portfolio Protection:** Keep a constant eye on personal portfolios or client websites.
* **SaaS Health Checks:** Monitor API endpoints and service status for software applications.

---

## 🛠️ Step-by-Step Implementation Guide

### 1. Initial Environment & GitHub Access
The foundation starts with setting up the local development environment in VS Code and configuring GitHub secrets for secure AWS communication.
![VS Code Environment](./Readme-images/image_bec09a.jpg)
![Project Structure](./Readme-images/Screenshot%202026-02-26%20151901.jpg)
![GitHub Secrets](./Readme-images/git-action-variables.png)

### 2. AWS SNS Configuration (Messaging Backbone)
Setting up the Simple Notification Service to handle email alerts.
![SNS Topic Setup](./Readme-images/SNS-1.png)
![SNS Subscription](./Readme-images/SNS-2.png)
![Email Confirmation](./Readme-images/SNS-6-aws-confirm-mail.png)

### 3. AWS IAM Role & Permissions (Security)
Configuring Identity and Access Management (IAM) to ensure the Lambda function has exact permissions.
![IAM Step 1](./Readme-images/IAM%20Role-1.png)
![IAM Step 2](./Readme-images/IAM%20Role-2.png)
![IAM Step 3](./Readme-images/IAM%20Role-3.png)
![IAM Step 4](./Readme-images/IAM%20Role-4.png)
![IAM Step 5](./Readme-images/IAM%20Role-5.png)
![IAM Step 6](./Readme-images/IAM%20Role-6.png)
![IAM Step 7](./Readme-images/IAM%20Role-7.png)

### 4. AWS Lambda & EventBridge Integration
Creating the serverless function and scheduling it to run every 5 minutes.
![Lambda Function](./Readme-images/lambda-1.png)
![Code Preview](./Readme-images/lambda-our-code.png)
![Add Trigger](./Readme-images/lambda-add-trigger.png)
![Trigger Success](./Readme-images/lambda-successfull-add-trigger.jpg)

### 5. Deployment via GitHub Actions (CI/CD)
Pushing the code to GitHub and watching the automated deployment pipeline.
![Git Push](./Readme-images/lambda-permission.png)
![CI/CD Success](./Readme-images/successful-deploy-gitaction-to-lambda.png)

### 6. Rigorous Testing & Downtime Alerts
Verifying the system by simulating downtime.
![Lambda Test Result](./Readme-images/lambda-test-pass.jpg)
![Email Alert](./Readme-images/site%20down%20email.png)

### 7. Monitoring & Observability (CloudWatch)
Analyzing logs and metrics to ensure long-term health.
![CloudWatch Overview](./Readme-images/cloudwatch%20log.jpg)
![Healthy Logs](./Readme-images/beforecloudwall%20log%20expand.jpg)
![Downtime Log Detail](./Readme-images/site%20down%20after%20cloud%20watch%20logs%20expand.jpg)
![Detailed Stream](./Readme-images/after%20cloud%20watch%20logs.jpg)
![Troubleshooting Permissions](./Readme-images/image_c16c2a.png)
![Execution Metrics](./Readme-images/image_c16452.jpg)

---

## 🔓 Open Source & Contributions
This is an **Open Source** project. Feel free to clone, fork, and enhance the code.

## 👨‍💻 Developed By
**Malinda Prabath**
* 📧 Email: [malindaprabath876@gmail.com](mailto:malindaprabath876@gmail.com)
* 💼 Cloud & DevOps Enthusiast