

# Deploy a Secure Three-Tier Application on AWS Using Terraform

## Project Overview
This project focuses on deploying a secure and scalable cloud infrastructure on Amazon Web Services (AWS) using Terraform. It demonstrates Infrastructure as Code (IaC), network segmentation, application hosting, load balancing, and cloud security monitoring.

The infrastructure is designed using a three-tier architecture consisting of a public-facing layer, a private application layer, and a private database layer.

## Objectives
- Build AWS infrastructure using Terraform.
- Configure a Virtual Private Cloud (VPC).
- Create public and private subnets across multiple Availability Zones.
- Deploy an Application Load Balancer (ALB).
- Host an application on a private EC2 instance.
- Configure security groups and network access restrictions.
- Enable VPC Flow Logs and AWS CloudTrail for monitoring and auditing.

## Architecture

```text
                    Internet
                       |
                Internet Gateway
                       |
          Application Load Balancer
                 (Public Subnets)
                       |
              Private App Subnet
                       |
                EC2 Instance
                       |
              Private DB Subnets
                       |
                 RDS MySQL
             (Planned - Not Deployed)
```

## AWS Services Used

| Service | Purpose |
|---|---|
| Amazon VPC | Isolated cloud network |
| Public Subnets | Host the internet-facing ALB |
| Private Subnets | Host application and database tiers |
| Internet Gateway | Internet connectivity for public subnet |
| Amazon EC2 | Application server |
| Application Load Balancer | Distributes incoming HTTP traffic |
| Security Groups | Control inbound and outbound traffic |
| Amazon S3 | Stores security logs |
| VPC Flow Logs | Capture network traffic metadata |
| AWS CloudTrail | Record AWS API activity |
| Amazon RDS | Planned database tier |
| Terraform | Infrastructure as Code |

## Implementation

1. Created the VPC using Terraform.
2. Configured six subnets across multiple Availability Zones.
3. Created and attached an Internet Gateway.
4. Configured public and private route tables.
5. Created security groups for ALB, application, and database tiers.
6. Deployed an EC2 application server in a private subnet.
7. Configured an Application Load Balancer in public subnets.
8. Created a target group and verified target health.
9. Enabled VPC Flow Logs and configured S3 log storage.
10. Created and enabled AWS CloudTrail for auditing.

## Security Features

- Network segmentation using public and private subnets.
- Application server deployed in a private subnet.
- Security groups configured for controlled traffic flow.
- Database tier designed for private network access.
- VPC Flow Logs enabled for network monitoring.
- CloudTrail enabled for AWS API auditing.
- S3 server-side encryption enabled for log storage.
- EC2 root volume encrypted.

## Testing and Validation

- Terraform configuration validated successfully.
- Infrastructure deployed successfully using Terraform.
- EC2 instance status checks passed.
- Application Load Balancer state verified as Active.
- Target group health verified as Healthy.
- Application successfully accessed through ALB DNS.
- VPC Flow Logs status verified as Active.
- CloudTrail logging status verified as enabled.

## Project Status

The application server and load balancer are deployed and functional. The RDS MySQL database configuration has been added to Terraform but was not deployed due to cost considerations.

## Future Scope

- Deploy and integrate Amazon RDS MySQL.
- Configure HTTPS using AWS Certificate Manager.
- Implement Auto Scaling for the application tier.
- Add AWS WAF for web application protection.
- Configure CloudWatch alarms and dashboards.
- Implement automated CI/CD using GitHub Actions.

## Conclusion

This project demonstrates the practical implementation of secure AWS cloud infrastructure using Terraform. It provides hands-on experience with VPC design, subnet segmentation, EC2 deployment, load balancing, security groups, and cloud security monitoring through VPC Flow Logs and CloudTrail.

