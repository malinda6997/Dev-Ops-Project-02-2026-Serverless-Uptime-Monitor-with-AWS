# 🚀 Serverless Website Uptime Monitor & Real-time Alerting System

[මෙහි Banner එකක් හෝ Project එකේ ප්‍රධාන Screenshot එකක් (lambda-monitoring.png)]

## 🌐 Introduction
[Project එක ගැන හැඳින්වීමක් සහ Real-world Use Cases]

---

## 🏗️ System Architecture
[GitHub -> Lambda -> SNS වැඩ කරන විදිහ ගැන කෙටි විස්තරයක්]

---

## 🛠️ Step-by-Step Implementation Guide

### Phase 1: Local Development & GitHub Setup
* Development in VS Code.
* Configuring GitHub Secrets (AWS Keys).
[Screenshots: VS Code setup, project files, GitHub secrets]

### Phase 2: AWS SNS (Notification Backbone)
* Creating a Topic.
* Setting up Email Subscriptions & Confirmation.
[Screenshots: SNS topic creation, subscription steps, email confirm mail]

### Phase 3: AWS IAM (Security & Permissions)
* Creating Execution Roles.
* Attaching SNS and CloudWatch Policies.
[Screenshots: IAM Role creation steps 1-7]

### Phase 4: AWS Lambda & EventBridge Configuration
* Creating the Serverless Function.
* Scheduling the 5-minute Trigger (Cron job).
[Screenshots: Lambda dashboard, adding triggers, trigger success status]

### Phase 5: CI/CD Pipeline (GitHub Actions)
* Automated deployment using workflows.
[Screenshots: Git push process, GitHub Actions success logs]

### Phase 6: Testing & Results
* Simulating a Site Failure.
* Automated Email Alerts.
[Screenshots: Manual test results, "Site Down" email alert]

### Phase 7: Monitoring & Observability
* Analyzing CloudWatch Logs.
* Performance Metrics tracking.
[Screenshots: CloudWatch logs, healthy/unhealthy log streams, metrics dashboard]

---

## 🔓 Open Source Project
[මෙය Open Source එකක් බව සහ දායක විය හැකි ආකාරය]

## 👨‍💻 Developed By
**Malinda Prabath**
* 📧 Email: malindaprabath876@gmail.com
* [LinkedIn / Portfolio Links]