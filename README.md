# aws-vpc-private-subnet-bastion-alb-project
AWS VPC project with private EC2 instances, bastion host, NAT Gateway, Application Load Balancer, Target Groups, and secure multi-subnet networking.
# AWS VPC with Private EC2 Instances, Bastion Host, NAT Gateway, and Application Load Balancer

## Project Overview

This project demonstrates a production-style AWS VPC architecture with public and private subnets across multiple Availability Zones. The architecture includes a bastion host for secure SSH access, private EC2 instances running a simple web application, and an Application Load Balancer to distribute traffic to backend servers.

This project is based on the AWS VPC reference architecture for private subnets and NAT gateway.

## Architecture

The architecture includes:

- Custom VPC
- Public subnets
- Private subnets
- Internet Gateway
- Bastion host in public subnet
- Two private EC2 instances
- Application Load Balancer
- Target Group
- Security Groups
- Route Tables
- NAT Gateway
- HTTP server running on port 8000

## Architecture Diagram

architecture/architecture-diagram.png

## Services Used

- Amazon VPC
- Amazon EC2
- Application Load Balancer
- Target Groups
- Security Groups
- Internet Gateway
- NAT Gateway
- Route Tables
- SSH / PuTTY
- Python HTTP Server

## Project Flow

1. Created a custom VPC.
2. Created public and private subnets.
3. Launched a bastion host in the public subnet.
4. Launched two Ubuntu EC2 instances in private subnets.
5. Connected to the bastion host using PuTTY.
6. Connected from bastion host to private EC2 instances using private IP addresses.
7. Created simple `index.html` files on both private servers.
8. Started Python HTTP server on port 8000.
9. Created an Application Load Balancer.
10. Registered both private EC2 instances in a Target Group.
11. Configured Security Groups to allow traffic from Load Balancer to private EC2 instances.
12. Tested application access using the Load Balancer DNS name.

## SSH Connection Flow

```text
Local Laptop
    ↓
PuTTY SSH
    ↓
Bastion Host - Public Subnet
    ↓
Private EC2 Instance 1 - 10.0.142.111
Private EC2 Instance 2 - 10.0.150.159
