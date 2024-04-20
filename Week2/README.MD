
# Table of contents

- [List of Services](#list-of-services)
- [Plan of Execution](#plan-of-execution)
- [Two-tier Architecture](#two-tier-architecture)
- [Architecture](#architecture)
- [Local Setup](#local-setup)
- [IAM Secret Key](#iam-secret-key)
- [Write Terraform Files](#write-terraform-files)
- [Best Practices](#best-practices)
- [Outputs](#outputs)
- [Resources](#resources)


## 📃 List of Services

- Amazon Certificate Manager (SSL)
- Amazon Route 53 (DNS service)
- Amazon CloudFront (CDN)
- Amazon EC2 (Server)
- Amazon Auto Scaling group (Scale on demand)
- Amazon VPC (Virtual private cloud: Private Network)
- Amazon RDS (Relational database services: Database)
- Amazon DynamoDB (State-locking for tfstate file)
- Amazon S3 (Storing backend and achieving versioning)
- Amazon CloudWatch (Alarm when CPU utilization increases or decreases)

## 💡 Plan of Execution

### What is Two-Tier Architecture?

Two-tier architecture, also known as client-server architecture, is a software design pattern that divides an application into two main parts or tiers: the client tier and the server tier. Each tier has specific responsibilities and interacts with each other to provide functionality to end-users.

### Architecture 
![Architecture](https://github.com/AnkitJodhani/3rdWeekofCloudOps/raw/main/architecture.gif)
- Diagram credit - AnkitJodhani
Let's see the architecture of today's project. We are going to follow a goal-driven approach that helps us to put in minimum effort and gain lots of results. It's very important to understand what we are going to build, and to understand, you can follow the below architecture. I request you please go through it once. It helps you a lot while building this project.

### Local Setup

#### VS Code

We are going to use VS Code as a code editor. Please download it from [here](https://code.visualstudio.com/). It's very lightweight and easy to use. Now, to boost your productivity, we are going to install the Terraform extension in VS Code. The name of the extension is HashiCorp Terraform.

#### Terraform Install

Please install Terraform on your platform from [this link](https://www.terraform.io/downloads.html). It's very easy, and most importantly, make sure to restart your system after installation.

#### AWS CLI

You need to install AWS CLI to use the AWS functionality from your terminal. Here is the link to download it: [AWS CLI](https://aws.amazon.com/cli/).

### 🚨 IAM Secret Key

I hope you have installed all the software and tools. Now it's time to open the AWS console. Please head over to the IAM service.

#### Create User

Please click on the user tab in the left corner. Now click on the add user button on the top right corner and give the name to the user. Now you need to attach the Policy for the user. Actually, we should follow the Principle of Least Privilege, but we need to use many services, so here you can give AdministratorAccess. But it is not advisable to give AdministratorAccess OR you can follow the above list of services part and attach the policy accordingly. Now click on the next button and click on the Create User button.

#### Create a Secret Key

Select the user that you have just created now. Click on the security credentials tab. Below you will find an option with the name Create Access key, just click on it. After that, select CLI and mark the checkbox below and click on the Next button. Give some description about it, and then click on the Create Access key button. Here you will see your Access Key ID and Secret Key. Make sure you download it because you won't be able to see it once you close your window. And remember DO NOT SHARE THE KEY with anyone.

#### Configure AWS-CLI

Open the terminal on your system and type `aws configure`. It will ask for your Access key ID and secret key id. Please enter what we have just created. Furthermore, it will ask for the output format JSON default region us-east-1. You can enter the region where you want to deploy your app. Follow the below images to get more ideas.

Now we don't need to explicitly mention the key; it prevents us from exposing the access key and secret key on the internet.

### ✍️ Write Terraform Files

Finally, it's time to write your infrastructure. But before you jump on it, let me clarify a few things. We are going to follow best practices while writing code.

### 🤩 Best Practices

- Store state files on a remote location
- Try to keep versioning for backups
- State-locking so that we can keep tfstate file consistent while working on a collaborative project
- Use VCS like Git and GitHub
- Follow modular approach

NOTE: You will get all the code and files on my GitHub repository, and I'll share the link with you at the END of the blog. But let me share a few things that you need to take care of while writing code in the `backend.tf` file.

```sh
terraform {
  backend "s3" {
    bucket = "BUCKET_NAME"
    key    = "backend/FILE_NAME_TO_STORE_STATE.tfstate"
    region = "us-east-1"
    dynamodb_table = "dynamoDB_TABLE_NAME"
  }
}
```
Create one file with the name of terraform.tfvars in the project directory.
```sh
Copy code
REGION                  = ""
PROJECT_NAME            = ""
VPC_CIDR                = ""
PUB_SUB_1_A_CIDR        = ""
PUB_SUB_2_B_CIDR        = ""
PRI_SUB_3_A_CIDR        = ""
PRI_SUB_4_B_CIDR        = ""
PRI_SUB_5_A_CIDR        = ""
PRI_SUB_6_B_CIDR        = ""
DB_USERNAME             = ""
DB_PASSWORD             = ""
CERTIFICATE_DOMAIN_NAME = ""
ADDITIONAL_DOMAIN_NAME  = ""
```

Note: The above file is very important to set up the infrastructure, so make sure you fill all the variable's values carefully.


## ✈️ Now we are ready to deploy our application on cloud ⛅
get into project directory 
```sh
cd book_shop_app
```

type below command to see plan of the exection 
```sh
terraform plan
```

✨Finally, HIT the below command to deploy the application...
```sh
terraform apply 
```

type `yes`, it will prompt you for permission..

**Thank you so much for reading..😅**

# 🖥️ Outputs
Let's see what Terraform created on our AWS console:

- VPC
- Routing table
- NAT gateway
- Internet gateway
- Security groups
- Launch template
- Auto-scaling group
- EC2 servers (Jump server)
- Target group
- Application load balancer
- RDS instance
- CloudFront distribution
- Record in Route 53

