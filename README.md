# Infrastructure as Code using Terraform and Ansible

## Project Overview
This project provisions an EC2 instance on AWS using Terraform and then configures it using Ansible.

```
#### Project Structure
Infrastructure-as-Code-using-Terraform/
│── terraform/
│   ├── main.tf
│   ├── providers.tf
│   ├── outputs.tf
│   ├── variables.tf
│── ansible/
│   ├── inventory.ini
│   ├── playbook.yml
│── README.md

```

### Technologies Used
- **Terraform** for Infrastructure as Code (IaC)
- **AWS** for Cloud Services
- **Ansible** for Configuration Management
- **Nginx** as a Web Server

---

## Setup Instructions

### Prerequisites
- AWS CLI installed and configured with appropriate IAM permissions
- Terraform installed
- Ansible installed
- A valid AWS Key Pair (update `variables.tf` with your key name)

---

### Steps to Deploy

#### 1. Clone the Repository
```bash
git clone https://github.com/your-github-username/Infrastructure-as-Code-using-Terraform.git
cd Infrastructure-as-Code-using-Terraform

#### 2. Initialize Terraform
cd terraform
terraform init

#### 3. Apply Terraform Configuration
terraform apply -auto-approve

This will output the public IP of the EC2 instance.

#### 4. Configure Ansible Inventory
Update ansible/inventory.ini with the public IP.

##### 5. Run Ansible Playbook
cd ../ansible
ansible-playbook -i inventory.ini playbook.yml

#### 6. Verify Nginx Installation
Open a browser and visit http://<your-instance-public-ip> to check if Nginx is running.

Cleanup
To destroy the infrastructure, run:
cd terraform
terraform destroy -auto-approve

GitHub Commands to Store Project
git init
git add .
git commit -m "Initial commit - Terraform and Ansible setup"
git branch -M main
git remote add origin https://github.com/your-github-username
git push -u origin main

Notes
Replace your-github-username with your actual GitHub username before running Git commands.
Make sure the SSH key path in inventory.ini is correct.


