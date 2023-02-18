[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

# FloWave Infrastructure

It is a set of infrastructure code which intends to be reusable, scalable, testable, customizable, secure and well-documented. In a first moment, this repo works as base for the opensource project FloWave. It can used in other projects with the apropriate reference.

# Getting Started
To deploy the FloWave infrastructure, you will need to set up the following prerequisites:

An AWS account
AWS CLI installed and configured
Terraform installed
Git installed

Once you have set up the prerequisites, follow these steps to deploy the infrastructure:

1. Clone this repository to your local machine: <br>
`git clone https://github.com/Demians12/FloWave-infrastructure.git`

2. Navigate to the terraform directory:<br>
`cd FloWave-infrastructure/terraform`

3. Initialize the Terraform environment:<br>
`terraform init`

4. Modify the terraform.tfvars file to include your own values for the variables defined in variables.tf.

5. Create an execution plan for the Terraform configuration and review the configuration:<br>
`terraform plan`

6. Apply the Terraform configuration:<br>
`terraform apply`

# What's Included
The infrastructure code in this repository includes the following resources:

-   A virtual private cloud (VPC) with public and private subnets
-   An Amazon Elastic Kubernetes Service (EKS) cluster for hosting the FloWave microservices
-   A set of AWS Identity and Access Management (IAM) roles and policies for granting permissions to the EKS cluster
-   An Amazon Elastic File System (EFS) for storing persistent data used by the FloWave microservices
-   An Amazon Relational Database Service (RDS) instance for storing metadata related to ocean wave data
-   A set of Amazon Simple Notification Service (SNS) topics and subscriptions for sending notifications related to the FloWave platform
-   An Amazon CloudFront distribution for caching and serving static assets used by the FloWave platform

In addition to the infrastructure code, this repository includes a set of AWS Lambda functions for automating certain tasks related to the FloWave platform, such as sending notifications based on data in the RDS database.

Contributing
If you wish to contribute to the FloWave infrastructure code, please follow these guidelines:

Fork this repository to your own GitHub account.

Clone your fork of the repository to your local machine:
