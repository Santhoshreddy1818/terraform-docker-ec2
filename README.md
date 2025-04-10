
# Terraform Docker EC2 Provisioning

This project demonstrates how to use **Terraform** to provision a **Docker container running Nginx** on an **EC2 instance**, using **Infrastructure as Code (IaC)** principles.

---

## 🚀 Objective

Provision a local Docker container on an EC2 instance using Terraform.

---

## 🛠️ Tools Used

- **Terraform** – IaC tool for infrastructure automation  
- **Docker** – To containerize the Nginx server  
- **EC2** – Amazon EC2 instance to host the setup  
- **Ubuntu (on EC2)** – The OS used for running Docker and Terraform

---

## 📂 Files in This Repo

| File         | Description                          |
|--------------|--------------------------------------|
| `main.tf`    | Terraform configuration file         |
| `apply.log`  | Execution log of `terraform apply`   |
| `destroy.log`| Execution log of `terraform destroy` |
| `README.md`  | Project documentation                |

---

## 📦 Setup Instructions

### 1. SSH into Your EC2 Instance

```bash
ssh -i <your-key.pem> ubuntu@<your-ec2-public-ip>
```

### 2. Install Prerequisites

```bash
sudo apt update
sudo apt install -y docker.io unzip curl
sudo systemctl start docker
sudo systemctl enable docker

# Install Terraform
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -
sudo apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
sudo apt update && sudo apt install terraform -y
```

### 3. Clone the Repository

```bash
git clone https://github.com/Santhoshreddy1818/terraform-docker-ec2.git
cd terraform-docker-ec2
```

---

## ⚙️ Terraform Workflow

### Initialize

```bash
terraform init
```

### Preview Changes

```bash
terraform plan
```

### Apply Configuration

```bash
terraform apply
# Type 'yes' to confirm
```

### Check Docker Container

```bash
docker ps
```

> You should see an Nginx container running on port **8080**.

### Access Nginx in Browser

Visit:
```
http://<your-ec2-public-ip>:8080
```

> Make sure port **8080** is open in your EC2 security group.

---

### Destroy Infrastructure (Cleanup)

```bash
terraform destroy
# Type 'yes' to confirm
```

---

## ✅ Outcome

You’ll gain hands-on experience with:

- Using Terraform’s Docker provider
- Managing infrastructure on EC2
- Automating container provisioning via IaC
- Terraform commands like `init`, `plan`, `apply`, and `destroy`

---

## 🙌 Author

**Santhosh Reddy**  
GitHub: [@Santhoshreddy1818](https://github.com/Santhoshreddy1818)


