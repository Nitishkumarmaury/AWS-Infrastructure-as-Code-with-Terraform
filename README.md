# 3-Tier AWS Architecture with Terraform

This project deploys a complete 3-tier architecture on AWS using Terraform, consisting of:

## Architecture Overview
- **Presentation Layer**: Application Load Balancer (ALB) in public subnets
- **Application Layer**: Auto Scaling Group with EC2 instances in private subnets
- **Database Layer**: RDS MySQL 8.0 instance in database subnets

## Infrastructure Components
- **VPC**: Custom VPC with CIDR 10.0.0.0/16
- **Subnets**: Public, private, and database subnets across 3 availability zones
- **Security Groups**: Configured for web servers, load balancer, and database
- **Auto Scaling**: Configurable scaling between 1-3 instances
- **Load Balancer**: Application Load Balancer with health checks
- **Database**: MySQL 8.0 on db.t3.micro instance

## Deployment Status
✅ **Successfully Deployed**: 40 resources created
- Load Balancer DNS: `my-3-tier-architecture-1371552020.us-west-2.elb.amazonaws.com`
- Database: MySQL 8.0 with db.t3.micro instance class
- Region: us-west-2 (Oregon)

## Key Features
- High availability across multiple AZs
- Auto scaling based on demand
- Secure database in private subnets
- CloudInit configuration for EC2 setup
- IAM roles with appropriate permissions

## Usage
```bash
terraform init
terraform plan
terraform apply
```

Access your application via the load balancer DNS name provided in the output.
