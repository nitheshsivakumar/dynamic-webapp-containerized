# 🚗 RentZone - Car Rental Application on AWS with Docker, ECR, and ECS

## 📌 Project Overview

RentZone is a **dynamic car rental application** hosted on **AWS**, utilizing **Docker containers**, **Amazon Elastic Container Registry (ECR)**, and **Amazon Elastic Container Service (ECS) with AWS Fargate**. This project ensures **scalability, high availability, and security** while offering an optimized deployment pipeline.

## 🎯 Problem Statement

### Challenges in Hosting a Car Rental Web App
- **Scalability**: Handling varying loads as customers book vehicles.
- **Reliability**: Ensuring high availability with minimal downtime.
- **Security**: Protecting user and payment data.
- **Infrastructure Management**: Avoiding manual server provisioning.
- **Efficient Deployment**: Automating CI/CD workflows for rapid releases.

✅ **Solution Implemented:**  
This project leverages **Docker** for containerization, **ECR** for image storage, and **ECS with AWS Fargate** for **serverless, containerized application hosting**.

---

## 🏗️ Architecture Overview

### 🔹 Key AWS Services Used
- **Amazon ECR** - Storing container images.
- **AWS Fargate** - Running containers without managing EC2 instances.
- **Amazon ECS** - Orchestrating containerized workloads.
- **Amazon RDS (MySQL)** - Storing rental data and transactions.
- **Amazon S3** - Storing environment variables and static assets.
- **Application Load Balancer** - Distributing traffic to containers.
- **VPC** - Custom networking with private and public subnets.
- **NAT Gateway** - Enabling internet access for private instances.
- **Bastion Host** - Secure SSH access to internal resources.
- **AWS Certificate Manager** - Encrypting web traffic with HTTPS.
- **Amazon Route 53** - Managing DNS records for domain resolution.
- **IAM** - Managing permissions and access control.

---

## 🚀 Deployment Steps

### 1️⃣ Prerequisites
- Install **Git**, **Visual Studio Code**, **AWS CLI**, and **Docker**.
- Create a **GitHub repository** and add a **Dockerfile**.
- Set up **Flyway** for SQL migration into **Amazon RDS**.

### 2️⃣ Containerization & Image Storage
- Clone the repository and create a **Dockerfile**.
- Build the **Docker container image**.
- Run and test the container locally.
- Push the image to **Docker Hub**.

### 3️⃣ Push Image to AWS ECR
- Create an **IAM User** with appropriate permissions.
- Create an **Amazon ECR repository**.
- Authenticate Docker with AWS and push the image to ECR.

### 4️⃣ Deploy to AWS ECS with Fargate
- Set up a **VPC** with public and private subnets.
- Create an **Application Load Balancer** for traffic distribution.
- Define **security groups** to restrict access.
- Create an **ECS cluster** using AWS Fargate.
- Define a **Task Definition** for the container.
- Deploy the container as an **ECS service**.

### 5️⃣ Configure Database & Security
- Deploy **Amazon RDS (MySQL)** in private subnets.
- Set up a **Bastion Host** for secure SSH tunneling.
- Register a **domain** using **Amazon Route 53**.
- Set up an **SSL certificate** using **AWS Certificate Manager**.

---

## 🔧 How to Set Up Locally

1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/rentzone.git
   cd rentzone

2. Build and run the Docker container:
   ```sh
    docker build -t rentzone-app .
    docker run -p 8080:80 rentzone-app

3. Push the image to AWS ECR:
   ```sh
    aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin <your-ecr-url>
    docker tag rentzone-app:latest <your-ecr-url>:latest
    docker push <your-ecr-url>:latest

4. Deploy to ECS via AWS Fargate.

📊 Key Benefits

✅ Fully Managed - No need to manage EC2 instances with AWS Fargate.
✅ Scalable - Automatically adjusts resources based on booking demand.
✅ Secure - IAM roles, private subnets, and HTTPS encryption.
✅ Optimized Costs - Serverless hosting with pay-as-you-go billing.
✅ Automated Deployment - CI/CD integration with Docker and ECR.
