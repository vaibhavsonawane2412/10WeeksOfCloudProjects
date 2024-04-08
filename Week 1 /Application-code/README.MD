
# Download Code from Github

Download the code from this repository  into your local environment by running the command `git clone ` . If you don't have git installed, you can just download the zip. Save it somewhere you can easily access.

[GitHub Repository](https://github.com/aws-samples/aws-three-tier-web-architecture-workshop.git)


# Three-Tier Web Architecture in AWS

This repository contains the code and configurations for deploying a three-tier web architecture on Amazon Web Services (AWS). The architecture consists of separate tiers for the application and web components.

## Application Tier

The `app-tier` folder contains the configurations and code for the application tier of the architecture. This tier is responsible for running Node.js applications and handling business logic.

### Setup Instructions
1. Navigate to the `app-tier` directory.
2. Follow the README instructions within the `app-tier` folder to set up the application tier components.

### Features
- Internal facing load balancer for routing traffic to application instances.
- Autoscaling groups for maintaining availability and scalability.
- Integration with Aurora MySQL multi-AZ database.

## Web Tier

The `web-tier` folder contains the configurations and code for the web tier of the architecture. This tier is responsible for serving the React.js website and acting as a gateway for client traffic.

### Setup Instructions
1. Navigate to the `web-tier` directory.
2. Follow the README instructions within the `web-tier` folder to set up the web tier components.

### Features
- Public-facing Application Load Balancer (ALB) for routing client traffic.
- Nginx web servers for serving the React.js website and redirecting API calls to the application tier.
- Integration with the application tier's internal facing load balancer.

## Usage
Ensure that both the application tier and web tier components are deployed and configured properly to enable the three-tier architecture's full functionality.
