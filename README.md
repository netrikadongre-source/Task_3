# 🚀 Task 3 - Provision Docker Container with Terraform (WSL + EC2)

This project is part of my DevOps Internship (Task 3) focused on **Infrastructure as Code (IaC)** using **Terraform** and **Docker**.  
The goal was to provision a Docker container both **locally (WSL)** and on an **AWS EC2 instance** using Terraform.

---

## 🎯 Objective

- Use the **Docker provider** in Terraform
- Provision a Docker container with:
  - `nginx:latest` image
  - Port exposed for browser access
- Deploy on:
  - **WSL (Windows Subsystem for Linux)**
  - **AWS EC2 (Ubuntu)**

---

## 🧰 Tools & Technologies

- Terraform v1.x
- Docker
- WSL (Ubuntu on Windows)
- AWS EC2 (Ubuntu 22.04 LTS)
- Git & GitHub

---

## 🏗️ Setup Details

### 1. 🔧 Local (WSL)
- Terraform and Docker installed on WSL Ubuntu
- NGINX container exposed on `localhost:9090`
- Jenkins was running on port `8080`, so port conflict was avoided

### 2. ☁️ Cloud (EC2)
- EC2 instance (t2.micro) with Docker & Terraform installed
- Container exposed on port `80` with security group allowing HTTP (inbound rule)
- Used SSH to access and apply Terraform from within the EC2 instance

---

## 📂 Project Structure

```go
├── main.tf # Terraform code to provision Docker container
├── terraform.tfstate # Terraform state file (auto-generated)
├── README.md # Project documentation
```
---

## 🛠 Steps Performed

1. Initialized Terraform with the Docker provider
2. Pulled the `nginx:latest` Docker image
3. Created and ran a Docker container
4. Exposed port `80` on EC2 and `9090` on WSL
5. Verified access:
   - On WSL: `http://localhost:9090`
   - On EC2: `http://<EC2_Public_IP>`
6. Cleaned up using `terraform destroy`

---

## 🖥️ Terraform Commands Used

```bash
terraform init
terraform plan
terraform apply
terraform destroy
docker ps
```
---

*🙋🏻‍♀️ Author
Netrika Dongre
GitHub: netrikadongre-source*

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
