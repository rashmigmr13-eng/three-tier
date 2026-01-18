# Multi-Tier AWS Infrastructure using Terraform

This project provisions a **multi-tier AWS architecture** using **Terraform**, including:

* AWS networking (VPC, subnets, security groups)
* EC2 Web Server
* RDS (MySQL) Database
* Public access to the web tier

---

## 📌 Prerequisites

* Ubuntu / Debian / Amazon Linux
* AWS Account
* IAM User with required permissions
* Terraform
* AWS CLI

---

## 🔧 Installation Steps

### 1️⃣ Update System

```bash
sudo apt update
```

---

### 2️⃣ Install Terraform

Install Terraform using the **official documentation**:
👉 [https://developer.hashicorp.com/terraform/downloads](https://developer.hashicorp.com/terraform/downloads)

Verify installation:

```bash
terraform -version
```

---

### 3️⃣ Install AWS CLI

```bash
sudo apt install awscli -y
```

Configure AWS credentials:

```bash
aws configure
```

Provide:

* AWS Access Key
* AWS Secret Key
* Region (e.g. `us-east-1`)
* Output format (`json`)

---

## 📁 Project Setup

Create project directory:

```bash
mkdir multi-tier-aws
cd multi-tier-aws
```

Create Terraform files:

* `provider.tf`
* `variables.tf`
* `main.tf`
* `outputs.tf`

---

## 🚀 Terraform Commands

Initialize Terraform:

```bash
terraform init
```

Validate configuration:

```bash
terraform validate
```

Preview infrastructure changes:

```bash
terraform plan
```

Create infrastructure:

```bash
terraform apply
```

Type `yes` when prompted.

---

## 🌐 Access Web Server

After successful apply, Terraform will output the **public IP** of the EC2 instance.

Open browser:

```
http://<PUBLIC_IP>
```

---

## 🗄️ Database (RDS – MySQL)

### Install MySQL Client

**Ubuntu / Debian:**

```bash
sudo apt install mysql-client -y
```

**Amazon Linux:**

```bash
sudo yum install mysql -y
```

---

### Connect to RDS

```bash
mysql -h terraform-20251217130721309500000002.cs9aowaawyga.us-east-1.rds.amazonaws.com \
-u admin -p
```

Password:

```
Admin12345
```

---

### MySQL Commands

Show databases:

```sql
SHOW DATABASES;
```

Use database:

```sql
USE mydb;
```

---

## 🧹 Destroy Infrastructure (Optional)

To delete all AWS resources:

```bash
terraform destroy
```

---

## 📌 Notes

* Never hardcode secrets in production
* Use `terraform.tfvars` or AWS Secrets Manager for credentials
* Restrict security group access

---

## ✅ Author

**Rashmi**

Happy Terraforming 🚀
