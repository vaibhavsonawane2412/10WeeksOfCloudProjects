
# Week1 Challenge: Design a 3-Tier Architecture 🚀

For this task, your objective is to design a 3-tier architecture in a cloud platform, such as AWS, Azure, or GCP, with a focus on the following key considerations:

1. **High Availability**: Ensure your architecture is highly available, capable of withstanding failures, and can provide uninterrupted service.

2. **Scalability**: Design your architecture to be highly scalable, allowing for easy and efficient resource scaling as your application's demands increase.

3. **Fault Tolerance**: Implement fault-tolerant mechanisms to minimize downtime and service interruptions during failures.

4. **Custom VPC/VNET**: Consider using a custom Virtual Private Cloud (VPC) for AWS or GCP, a Virtual Network (VNET) for Azure, or a similar network customization instead of relying on the default configurations.

5. **Security**: Prioritize security by adhering to best practices for Identity and Access Management (IAM) and implementing robust security measures.


# Project Documentation for Three-Tier Web Architecture in AWS

## Introduction
The objective of this project is to create a scalable and available three-tier web architecture on Amazon Web Services (AWS). This architecture consists of a network tier, an application tier, and a database tier. The aim is to manually configure and deploy each component to ensure the proper functioning of the architecture.

## Step-by-Step Guide

1. **Setting Up the Network Tier:**
   - Create a Virtual Private Cloud (VPC) with appropriate CIDR block.
   - Create public and private subnets within the VPC.
   - Configure route tables for public and private subnets.
   - Set up an internet gateway and attach it to the VPC.
   - Create security groups for web tier EC2 instances, application tier instances, and database instances.

2. **Deploying the Web Tier:**
   - Launch EC2 instances for the web tier with Nginx installed.
   - Configure Nginx to serve the React.js website and redirect API calls to the application tier's internal facing load balancer.
   - Configure security groups to allow traffic from the public internet through the ALB to the web tier EC2 instances.

3. **Configuring the Application Tier:**
   - Set up an internal facing Application Load Balancer (ALB) for the application tier.
   - Launch EC2 instances for the application tier running Node.js applications.
   - Configure load balancing, health checks, and autoscaling groups to maintain availability and scalability.

4. **Setting Up the Database Tier:**
   - Create an Aurora MySQL multi-AZ database instance.
   - Configure security groups to allow communication between the application tier and the database tier.

5. **Testing and Monitoring:**
   - Test the connectivity between different tiers.
   - Monitor the performance of each component using AWS CloudWatch or other monitoring tools.
   - Implement logging and monitoring for better visibility into the system.

## Challenges Faced
- **Networking Configuration:** Configuring the VPC, subnets, and route tables can be complex, especially ensuring proper routing between tiers while maintaining security.
- **Load Balancing and Autoscaling:** Setting up load balancers and autoscaling groups requires careful configuration to ensure proper distribution of traffic and scaling based on demand.
- **Database Configuration:** Configuring the Aurora MySQL multi-AZ database and ensuring proper security and performance tuning can be challenging.

## Key Takeaways
- Understanding the importance of proper network configuration in a three-tier architecture.
- Learning to utilize AWS services like ALB, EC2, Aurora MySQL, and CloudWatch for building scalable and available architectures.
- Importance of automation and infrastructure as code for managing and deploying complex architectures efficiently.

## Resources
- AWS Documentation: [https://docs.aws.amazon.com/](https://docs.aws.amazon.com/)
- Nginx Documentation: [https://nginx.org/en/docs/](https://nginx.org/en/docs/)
- React.js Documentation: [https://reactjs.org/docs/getting-started.html](https://reactjs.org/docs/getting-started.html)
- Node.js Documentation: [https://nodejs.org/en/docs/](https://nodejs.org/en/docs/)




