# DevOps Automation: Provisioning AWS EC2 with Shell Scripting

This project demonstrates how to **automate the provisioning of an AWS EC2 instance** using a Bash shell script and AWS CLI. It includes checks for the CLI installation, downloads it if necessary, and then launches an EC2 instance using user-specified parameters.

---

## 📌 Features

- ✅ Checks if AWS CLI is installed; installs it if missing
- ✅ Automates EC2 instance creation using AWS CLI
- ✅ Waits for the EC2 instance to reach the "running" state
- ✅ Uses clean, error-safe Bash scripting (`set -euo pipefail`)
- ✅ Lightweight and beginner-friendly DevOps automation

---

## 🛠 Technologies Used

- **AWS EC2**
- **AWS CLI v2**
- **Bash Shell**
- **Ubuntu/Linux**
- **IAM Access Keys (for authentication)**

---

## 📂 Project Structure

ec2-provisioning/
│
├── cli.sh # Main shell script
├── README.md # Project documentation
└── ... # (Other optional files or scripts)
                     
---

## 🔧 How It Works (Steps)

1. Launch and connect to a base Ubuntu EC2 instance using SSH.
2. Create a new directory and inside it, create `cli.sh` using:
   ```bash
   touch cli.sh && vim cli.sh
Paste the automation script (see below) into cli.sh.

Make it executable:

bash
Copy
Edit
chmod +x cli.sh
Run the script to automate:

AWS CLI installation

EC2 instance creation with parameters like AMI ID, key name, subnet, and security group

The script waits until the instance is in the running state.

🧠 Script Logic Summary
bash
Copy
Edit
#!/bin/bash
set -euo pipefail

# 1. Check if AWS CLI is installed, install if missing
# 2. Use aws ec2 run-instances to launch instance with input parameters
# 3. Wait until the new EC2 instance is in 'running' state
# 4. Output instance details to the user
⚙️ Required Parameters
Make sure to replace these variables in the script before running:

bash
Copy
Edit
AMI_ID=""             # e.g., "ami-0abcdef1234567890"
INSTANCE_TYPE="t2.micro"
KEY_NAME=""           # Your key pair name
SUBNET_ID=""          # Your subnet ID
SECURITY_GROUP_IDS="" # One or more security group IDs
INSTANCE_NAME="Shell-Script-EC2-Demo"
🔐 Prerequisites
AWS IAM credentials configured (aws configure)

Valid key pair and security group already set up in your AWS account

unzip and curl installed on your machine
