# 10 Weeks of Cloud Project Challenge

## Week 1: Three-Tier Web Architecture on AWS

### Project Overview
For the first week of the challenge, I completed the implementation of a three-tier web architecture on Amazon Web Services (AWS). The architecture consists of a network tier, an application tier, and a database tier. The main objectives were to create a scalable and available web application infrastructure utilizing various AWS services.

### Key Features
- Public-facing Application Load Balancer (ALB) for web tier
- Nginx web servers serving a React.js website in the web tier
- Internal-facing ALB for application tier
- Node.js applications running in the application tier
- Aurora MySQL multi-AZ database in the database tier

### Technologies Used
- Amazon Web Services (AWS) services:
  - EC2
  - VPC
  - ALB
  - Aurora MySQL
- Nginx
- React.js
- Node.js

### Project Demo
Unfortunately, I don't have a live demo available for this project at the moment. However, you can view the architecture diagram and configuration files in the repository.

### Challenges Faced
- Configuring the network architecture, including VPC, subnets, and route tables, required careful planning to ensure proper communication between tiers while maintaining security.
- Setting up load balancing and autoscaling for both the web and application tiers was challenging but essential for scalability and availability.
- Configuring and optimizing the Aurora MySQL database for performance and high availability posed challenges, but it was crucial for data integrity and reliability.

### Lessons Learned
- Importance of proper network configuration in a three-tier architecture.
- Utilizing AWS services like EC2, ALB, and Aurora MySQL for building scalable and available architectures.
- Challenges and best practices for load balancing, autoscaling, and database optimization in a cloud environment.

