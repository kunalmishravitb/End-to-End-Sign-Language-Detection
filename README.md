# 🤟🏻 End-to-End Sign Language Detection

### 🛠️ Setup Environment
```bash
conda create -n sign python=3.12 -y
conda activate sign
pip install -r requirements.txt
```

## 📂 Project Structure
1. 📜 **constants**
2. 🏗️ **entity**
3. ⚙️ **components**
4. 🔄 **pipelines**
5. 🚀 **app.py**

---

# 🚀 AWS CICD Deployment with GitHub Actions

## 1️⃣ 🔐 Login to AWS Console

## 2️⃣ 👤 Create IAM User for Deployment

### 🎯 With Specific Access:
1. 💻 **EC2 Access** – Virtual machine setup
2. 📦 **ECR (Elastic Container Registry)** – Store Docker images in AWS

### 🔄 Deployment Workflow:
1. 🏗️ Build Docker image of the source code
2. 📤 Push Docker image to **ECR**
3. 🚀 Launch **EC2** instance
4. 📥 Pull image from **ECR** in EC2
5. 🔄 Launch Docker image in EC2

### 🔑 Required Policies:
1. 🔧 **AmazonEC2ContainerRegistryFullAccess**
2. 🏢 **AmazonEC2FullAccess**

## 3️⃣ 📦 Create ECR Repo to Store Docker Image
   - Save the URI: `315865595366.dkr.ecr.us-east-1.amazonaws.com/sign`

## 4️⃣ 🖥️ Create EC2 Machine (Ubuntu)

## 5️⃣ 🛠️ Install Docker in EC2 Machine
```bash
# Optional
sudo apt-get update -y
sudo apt-get upgrade

# Required
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker
```

## 6️⃣ 🔄 Configure EC2 as Self-Hosted Runner
Go to **Settings > Actions > Runner > New Self-Hosted Runner**, choose OS, then run the provided commands.

## 7️⃣ 🔐 Setup GitHub Secrets
```plaintext
AWS_ACCESS_KEY_ID=xxxxx
AWS_SECRET_ACCESS_KEY=xxxxx
AWS_REGION=us-east-1
AWS_ECR_LOGIN_URI=566373416292.dkr.ecr.ap-south-1.amazonaws.com
ECR_REPOSITORY_NAME=simple-app
```
