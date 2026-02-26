# 🚀 Serverless Website Uptime Monitor & Alerting System
**An automated monitoring solution using AWS Lambda, SNS, and GitHub Actions.**

![Project Banner](./Readme-images/lambda-monitoring.png)

## 📖 Project Introduction
This project is a cloud-native, serverless solution designed to monitor the availability of websites (like your portfolio). It checks the site status every 5 minutes and sends an instant email alert via AWS SNS if any downtime is detected.

---

## 🏗️ How it Works (Architecture)
1. **GitHub Actions:** Automatically deploys your code to AWS when you push to the `main` branch.
2. **AWS EventBridge:** Triggers the Lambda function every 5 minutes.
3. **AWS Lambda:** Runs the Python script to check if the website is "UP" (HTTP 200).
4. **AWS SNS:** Sends an email notification if the site is "DOWN".
5. **CloudWatch:** Records all logs and metrics for troubleshooting.

---

## 🛠️ Step-by-Step Setup Guide (For Cloners)

### Step 1: Local Environment Setup
1. Clone this repository to your local machine.
2. Open the project in **VS Code**.
3. Update the `SITES` list in `lambda_function.py` with your own website URLs.
![VS Code Environment](./Readme-images/image_bec09a.jpg)
![Code Structure](./Readme-images/lambda-our-code.png)
![Project Structure](./Readme-images/Screenshot%202026-02-26%20151901.jpg)

### Step 2: Configure AWS SNS (Notifications)
1. Log in to your AWS Console and search for **SNS**.
2. Create a **Standard Topic** (e.g., `VercelMonitorAlert`).
3. Create a **Subscription**:
   - Protocol: `Email`
   - Endpoint: `Your Email Address`
4. **Important:** Go to your email inbox and click **"Confirm Subscription"** in the mail from AWS.
![SNS Topic Creation](./Readme-images/SNS-1.png)
![SNS Dashboard](./Readme-images/SNS-3.png)
![Confirm Email](./Readme-images/SNS-6-aws-confirm-mail.png)

### Step 3: Configure AWS IAM (Permissions)
Create an IAM Role for your Lambda function with the following permissions:
1. `AWSLambdaBasicExecutionRole` (for CloudWatch logs).
2. A custom policy to allow `sns:Publish` to your SNS Topic ARN.
![IAM Role Step 1](./Readme-images/IAM%20Role-1.png)
![IAM Policy Attachment](./Readme-images/IAM%20Role-5.png)
![IAM User Keys](./Readme-images/IAM%20Role-7.png)

### Step 4: AWS Lambda & Trigger Setup
1. Create a Lambda function using **Python 3.x**.
2. Assign the IAM Role created in Step 3.
3. Add a **Trigger**: Select **EventBridge (CloudWatch Events)**.
4. Schedule expression: `rate(5 minutes)`.
![Lambda Setup](./Readme-images/lambda-1.png)
![Add Trigger](./Readme-images/lambda-add-trigger.png)
![Trigger Confirmation](./Readme-images/lambda-successfull-add-trigger.jpg)

### Step 5: CI/CD with GitHub Actions
To enable auto-deployment:
1. In your GitHub repo, go to **Settings > Secrets and variables > Actions**.
2. Add two secrets:
   - `AWS_ACCESS_KEY_ID`
   - `AWS_SECRET_ACCESS_KEY`
3. Push your changes to GitHub.
![GitHub Secrets](./Readme-images/git-action-variables.png)
![Deployment Success](./Readme-images/successful-deploy-gitaction-to-lambda.png)

---

## 🔍 Verification & Testing
1. **Successful Run:** If the site is up, logs will show `Portfolio is UP`.
2. **Alert Simulation:** Change the URL to a wrong one. You will receive an email like the one below.
3. **Log Monitoring:** View detailed execution steps in CloudWatch.

![Manual Test Success](./Readme-images/lambda-test-pass.jpg)
![CloudWatch Success Log](./Readme-images/beforecloudwall%20log%20expand.jpg)
![Downtime Alert Log](./Readme-images/site%20down%20after%20cloud%20watch%20logs%20expand.jpg)
![Real Email Alert](./Readme-images/site%20down%20email.png)

---

## 🛠️ Troubleshooting
* **Permission Denied:** If CloudWatch logs are not appearing, check the IAM role policies.
![Troubleshooting Logs](./Readme-images/image_c16c2a.png)
* **High Latency:** Check the **Monitoring** tab in Lambda for performance metrics.
![Performance Metrics](./Readme-images/image_c16452.jpg)

---

### 👨‍💻 Developed by
**[Your Name]** - [LinkedIn] | [Portfolio]