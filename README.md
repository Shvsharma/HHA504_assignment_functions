# HHA504 Assignment - Exploring Serverless Computing and Cron Jobs

## Overview
This assignment explores serverless computing by deploying functions on both Azure and Google Cloud Platform (GCP). Additionally, a cron job is created using GitHub Actions, and GCP Cloud Scheduler is used to automate HTTP-triggered tasks.

---

## 1. Azure Serverless Function Deployment

### Steps:
- Created an HTTP-triggered Azure Function that responds with "Hello, World!".
- Deployed the function via the Azure portal.
- Tested the function by triggering it through its URL.

### Screenshot:
![Screenshot 2024-10-04 164324](https://github.com/user-attachments/assets/e04d1b5c-a833-4bf4-b58b-cb5312dcd496)

![Screenshot 2024-10-04 171532](https://github.com/user-attachments/assets/758fb176-f529-4255-82a7-fdad8883b2e6)


![Screenshot 2024-10-04 171759](https://github.com/user-attachments/assets/80e889d1-41c7-4c7e-89ff-850c0fbe99a7)



---

## 2. GCP Serverless Function Deployment

### Steps:
- Created an HTTP-triggered Google Cloud Function.
- Deployed the function in GCP and tested it by accessing its URL.

### Screenshot:
![Screenshot 2024-10-04 200205](https://github.com/user-attachments/assets/1a5aff28-adf2-4361-b5ff-bc41933bc78e)

![Screenshot 2024-10-04 202245](https://github.com/user-attachments/assets/29f15a26-e807-42f6-ba7f-25f73aebe5f7)

![Screenshot 2024-10-04 202303](https://github.com/user-attachments/assets/2218075d-e961-4f3e-9a0c-d02b62aa7b2b)



---

## 3. GitHub Actions Cron Job

### Steps:
- Configured a GitHub Actions workflow to run a daily cron job at midnight (UTC).
- The workflow logs a scheduled task execution.

### Code (`.github/workflows/cron-job.yml`):
```yaml
name: Daily Cron Job

on:
  schedule:
    - cron: "0 0 * * *"  # Every day at midnight (UTC)
  workflow_dispatch:  # This allows you to manually trigger the workflow

jobs:
  log-message:
    runs-on: ubuntu-latest
    steps:
      - name: Log scheduled task
        run: echo "Scheduled task executed"
 ``` 


![Screenshot 2024-10-04 210100](https://github.com/user-attachments/assets/a598f724-db62-4df2-90b9-952b09be7e49)

## 4. GCP Cloud Scheduler Setup

Steps: 
-Enabled the GCP Cloud Scheduler API.
-Created a Cloud Scheduler job to trigger an HTTP request to the deployed GCP Cloud Function at midnight (EST) daily.
-Verified the job by running it manually and confirming it was scheduled correctly.

![Screenshot 2024-10-04 213041](https://github.com/user-attachments/assets/82a6f2fd-e73b-4a6e-943d-25649170632e)

![Screenshot 2024-10-04 213018](https://github.com/user-attachments/assets/2c79d241-7d7b-4e45-ba81-ec12f1c0c32f)

## 5. Reflection on Serverless Computing
Serverless computing offers significant advantages for modern cloud architectures by providing a scalable, event-driven environment where developers can focus on code without worrying about infrastructure management.

## Benefits:
-Cost Efficiency: Pay only for the execution time, reducing overall infrastructure costs.

-Auto-Scaling: Functions automatically scale up or down based on the number of requests.

-Reduced Operational Complexity: Cloud providers handle the server management, allowing developers to focus purely on writing code.

## Limitations:
-Cold Starts: Functions may have slower initial response times when they haven't been used for a while.

-Execution Time Limits: There are time and resource limits on individual function executions (e.g., memory, CPU).

-Debugging Challenges: Debugging serverless applications can be more complex compared to traditional servers.

## Use Cases:
-Microservices: Each function can be a small, independent unit of a larger application.

-Scheduled Tasks: Ideal for periodic jobs such as sending notifications, performing backups, or cleaning up resources.

-Real-Time Processing: Can process events in real-time, such as responding to HTTP requests or handling messages in a queue.

## Conclusion
In this assignment, serverless functions were deployed successfully on both Azure and Google Cloud Platform. GitHub Actions and GCP Cloud Scheduler were used to implement automated task scheduling, demonstrating how Functions as a Service (FaaS) can be used for event-driven, scalable cloud solutions. Serverless computing is an efficient and cost-effective approach to building modern cloud-native applications.



