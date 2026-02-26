# 🚀 Serverless Website Uptime Monitor & Alerting System
**A fully automated, cloud-native monitoring solution built with AWS and CI/CD integration via GitHub Actions.**

![Project Overview](./images/lambda-monitoring.png)

## 📖 Introduction
This project provides a robust, serverless solution for monitoring website availability. It automatically checks the health of specified URLs every 5 minutes and sends instant email notifications if a downtime is detected. This demonstrates the implementation of **Infrastructure as Code (IaC)** principles and **Automated DevOps pipelines**.

---

## 🏗️ System Architecture & Workflow
The system architecture follows a modern serverless design:

1. **Automation (GitHub Actions):** Every code change pushed to the `main` branch is automatically deployed to AWS Lambda.
2. **Scheduling (Amazon EventBridge):** A cron-job trigger executes the function every 5 minutes.
3. **Compute (AWS Lambda):** A Python-based function checks for HTTP 200 status codes.
4. **Notifications (Amazon SNS):** If a site is unreachable, an alert is published to an SNS Topic.
5. **Monitoring (Amazon CloudWatch):** All logs and performance metrics are stored for real-time analysis.



---

## 🛠️ Tech Stack
* **Cloud Platform:** AWS (Lambda, SNS, EventBridge, IAM, CloudWatch)
* **DevOps:** GitHub Actions (CI/CD), GitHub Secrets
* **Language:** Python (utilizing Boto3 and Urllib)
* **IDE:** VS Code

---

## 📸 Comprehensive Project Walkthrough

### 1. Development & Environment Setup
The core logic is developed locally using VS Code. The project structure is optimized for GitHub Actions deployment.
![VS Code Setup](./images/image_bec09a.jpg)
![Project Files](./images/Screenshot%202026-02-26%20151901.jpg)

### 2. Identity & Access Management (IAM)
Security is implemented using the **Principle of Least Privilege**. A dedicated IAM Role was created with specific policies allowing Lambda to interact with SNS and CloudWatch Logs.
*(Includes IAM Roles for Permission handling and User access keys)*

### 3. Notification Service Configuration (SNS)
An SNS Topic named `VercelMonitorAlert` was created. Email subscriptions were confirmed to ensure instant delivery of alerts.
![SNS Confirmation](./images/SNS-6-aws-confirm-mail.png)

### 4. Serverless Logic & Trigger (Lambda & EventBridge)
The Lambda function is the heart of the system. An EventBridge trigger ensures the function runs autonomously without manual intervention.
![Lambda Configuration](./images/lambda-successfull-add-trigger.jpg)
![Trigger Setup](./images/lambda-add-trigger.png)

### 5. CI/CD Integration (GitHub Actions)
The deployment is fully automated. AWS credentials are securely stored in GitHub Secrets to maintain a secure pipeline.
![GitHub Actions Success](./images/successful-deploy-gitaction-to-lambda.png)

### 6. Real-world Testing & Results
To verify the system, a downtime scenario was simulated.
* **Alert Triggered:** The system successfully identified the "Down" status.
* **Email Received:** A real-time email alert was sent to the administrator.
* **Log Verification:** CloudWatch Logs provided a detailed execution trace.

![CloudWatch Success Log](./images/beforecloudwall%20log%20expand.jpg)
![Site Down Alert Log](./images/site%20down%20after%20cloud%20watch%20logs%20expand.jpg)
![Email Alert Received](./images/site%20down%20email.png)

### 7. Troubleshooting & Monitoring
The project also demonstrates handling permission issues and monitoring function performance metrics.
![Missing Permissions Error](./images/image_c16c2a.png)
![Performance Metrics](./images/image_c16452.jpg)

---

## 🚀 Key Learnings & Competencies
* **Serverless Engineering:** Building scalable applications without managing servers.
* **Cloud Security:** Mastering IAM Roles, Policies, and Secret Management.
* **Observability:** Utilizing CloudWatch for proactive debugging and monitoring.
* **DevOps Excellence:** Implementing automated CI/CD workflows for reliable deployments.

---

### 👨‍💻 Developer
**[Your Name]**
*Passionate about Cloud Engineering, DevOps, and Automation.*

---