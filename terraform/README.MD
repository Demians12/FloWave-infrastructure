#  Terraform

You have noticed the terraform folder is divided by layers and a module folder. Here a brief explanation of each folder:

Dividing the infrastructure into layers makes easier to manage and maintain the infrastructure, and allows for greater reusability and modularity. Each layer can be developed and tested independently, and changes can be applied incrementally without affecting the entire infrastructure. Additionally, this approach can help to reduce the risk of errors and inconsistencies by enforcing clear boundaries and responsibilities for each layer.

 - **`Layer1:`** This directory contains the Terraform code for creating the basic infrastructure layer, which includes the VPC, subnets, security groups, and other resources that form the foundation of the infrastructure. This layer is independent of the applications or services that run on top of it, and is designed to be reusable across multiple environments.
 - **`Layer2:`** This directory contains the Terraform code for creating the application layer, which includes the EKS cluster, worker nodes, and other resources that are specific to the applications or services that run on top of the infrastructure. This layer depends on the resources created in the `layer1` directory, and is designed to be environment-specific, with separate configurations for each environment.
 - **`Modules:`** This directory contains the reusable Terraform modules that are used in the `layer1` and `layer2` directories. These modules encapsulate the common patterns and best practices for creating specific types of resources, and can be shared across multiple projects.

Some important topics such as security are clearly implemented in Modules which represents the most advanced requirements for large-scale projects. 
Here a more detailed explanation about these topics and its respective folders:

 - **`aws-iam-eks-trusted`:** This module is used to create the IAM roles and policies that are required to allow the EKS cluster to access other AWS services, such as CloudWatch logs and S3 buckets. The module creates an IAM role for the EKS cluster and a policy that allows the role to access the necessary resources.
 - **`aws-pritunl:`** This module is used to create a Pritunl VPN server in the VPC, which can be used to access the Kubernetes API server and other resources in the VPC from a remote location. The module creates an EC2 instance for the Pritunl server, and sets up the necessary security groups and other resources.
 - **`aws-wafv2-top-10-owasp-rules:`** This module is used to create a set of AWS WAF (Web Application Firewall) rules that protect against the top 10 OWASP (Open Web Application Security Project) security risks. The module creates the WAF rules, and sets up the necessary resources, such as rule groups and conditions.
 - **`eks-kubernetes-namespace:`** This module is used to create a Kubernetes namespace in the EKS cluster. The module creates a namespace and sets up the necessary RBAC (Role-Based Access Control) rules to control access to the namespace.
 - **`self-signed-certificate:`** A Terraform module that provides an easy way to generate a self-signed TLS certificate and private key for use with an application or service. The module is useful in cases where a public SSL certificate from a certificate authority is not required or cannot be obtained.


 
