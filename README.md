```markdown
# Deploying a Python Application on AWS Elastic Beanstalk

## Overview
AWS Elastic Beanstalk is a fully managed service that allows you to quickly deploy and manage applications in the AWS Cloud without worrying about the infrastructure. This guide provides detailed step-by-step instructions to deploy a Python web application using AWS Elastic Beanstalk.

## Prerequisites
Before getting started, ensure you have the following:
- An **AWS account** with the necessary permissions.
- **AWS CLI** installed and configured on your system.
- A **Python application** ready for deployment.
- A **requirements.txt** file listing all dependencies.
- A **Procfile** defining how to run your application.

## Steps to Deploy

### 1. Create an Application
1. Navigate to the **AWS Elastic Beanstalk** console.
2. Click **Create Application**.
3. Enter an **Application Name** (e.g., `my-first-app`).
4. Choose a **Platform** (e.g., Python).
5. (Optional) Add tags for better management.
6. Click **Create**.

📌 ![Application setup](https://github.com/user-attachments/assets/55d7f13e-8d4e-4c01-9888-937896c14750)

### 2. Create an Environment
1. Click **Create Environment**.
2. Select **Web Server Environment**.
3. Choose **Python** as the platform.
4. Upload your **sample application** or select an existing one.
5. Select **Single Instance (Free Tier Eligible)** to minimize costs.
6. Click **Next**.

📌 ![Environment setup](https://github.com/user-attachments/assets/d0aba272-7711-4007-88dd-c6336bf57183)
### 3. Configure Service Access
1. Create a new **Service Role** for Elastic Beanstalk.
2. Assign the necessary IAM permissions.
3. Choose or create an **EC2 Instance Profile** with the required policies.
4. Ensure that the role has permissions for EC2, S3, CloudWatch, and Elastic Beanstalk.

📌 ![IAM role](https://github.com/user-attachments/assets/ccb09105-1765-4f07-9f6d-bf38570fbbfd)

### 4. Configure Networking and Security
1. Select a **VPC** and at least two **subnets**.
2. Choose or create a **Security Group**.
3. Set inbound and outbound rules to allow HTTP/HTTPS traffic.
4. (Optional) Configure Database settings if required.


### 5. Launch the Environment
1. Review all settings and configurations.
2. Click **Submit** to deploy the application.
3. Wait for the deployment process to complete.
4. Once deployed, access your application using the provided URL.

📌 ![Image](https://github.com/user-attachments/assets/fc5c92ef-96d2-441b-acc1-9e5ef7696f75)

### 6. Monitor the Application
1. Open the **Elastic Beanstalk Dashboard**.
2. Navigate to the **Monitoring** tab.
3. Check **CPU, Network, and Health** metrics.
4. Configure **Alarms** if necessary to track performance issues.


### 7. Update Your Application
1. Make necessary changes to your code.
2. Commit changes to your version control system.
3. Run the following AWS CLI commands to deploy:
   ```bash
   eb init  # Initialize the project
   eb create my-env  # Create environment
   eb deploy  # Deploy new version
   ```



## Notes
- **Elastic Beanstalk is free**, but associated resources (EC2, S3, RDS) may incur costs.
- You can automate deployments using **AWS CodePipeline**.
- Use the **AWS CLI** for faster command-line deployments:
  ```bash
  eb init
  eb create
  eb deploy
  eb status
  ```
- Refer to the **AWS documentation** for additional configurations.

```

