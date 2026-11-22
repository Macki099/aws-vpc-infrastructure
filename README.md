# aws-vpc-infrastructure
Demonstrate your understanding of AWS networking, subnet design, network security, and infrastructure provisioning.



# AWS Secure VPC Infrastructure

A hands-on cloud engineering project focused on designing a secure and highly available network infrastructure using Amazon Virtual Private Cloud (VPC) and AWS CloudFormation.

## Project Overview

This project demonstrates how to design and provision a structured AWS network environment using Infrastructure as Code (IaC).

The proposed architecture separates internet-facing resources from private workloads using public and private subnets distributed across multiple Availability Zones.

The infrastructure is designed to demonstrate network segmentation, controlled traffic flow, and secure resource communication.

## Objectives

- Design a custom AWS VPC.
- Configure public and private subnets across multiple Availability Zones.
- Implement Internet Gateway and NAT Gateway connectivity.
- Configure route tables and subnet associations.
- Apply security groups and network access controls.
- Automate infrastructure provisioning using AWS CloudFormation.
- Document network architecture and security decisions.

## Proposed Architecture

The infrastructure is designed around the following components:

| Component | Purpose |
|---|---|
| Amazon VPC | Isolated virtual network |
| Public Subnets | Host internet-facing resources |
| Private Subnets | Isolate internal workloads |
| Internet Gateway | Provide internet connectivity to public resources |
| NAT Gateway | Allow private resources to initiate outbound internet connections |
| Route Tables | Control network traffic routing |
| Security Groups | Control instance-level traffic |
| Network ACLs | Apply subnet-level traffic rules |
| Amazon EC2 | Simulate application workloads |
| CloudFormation | Automate infrastructure provisioning |

## Architecture Diagram

![AWS VPC Architecture](architecture/vpc-architecture.png)

> Replace this image with the actual architecture diagram once created.

## Repository Structure

```text
aws-vpc-infrastructure/
├── architecture/
│   └── vpc-architecture.png
├── templates/
│   └── vpc-infrastructure.yaml
├── documentation/
│   ├── network-design.md
│   ├── security-design.md
│   └── deployment-guide.md
├── scripts/
│   └── validate-template.sh
├── screenshots/
└── README.md
```

## Technologies and Tools

- Amazon VPC
- Amazon EC2
- AWS IAM
- AWS CloudFormation
- Linux
- YAML
- Git and GitHub
- cfn-lint

## Implementation Plan

1. Design the network topology.
2. Define VPC and subnet configurations.
3. Configure gateways, route tables, and security controls.
4. Develop CloudFormation templates.
5. Validate infrastructure templates.
6. Document architecture and implementation decisions.
7. Deploy and test the infrastructure when AWS account access is available.

## Testing and Validation

The project will use local template validation and static analysis to identify configuration and syntax issues.

Planned validation includes:

- CloudFormation template linting.
- Resource configuration review.
- Network architecture review.
- Security configuration review.

Actual AWS deployment and connectivity testing will be documented separately once AWS account access is available.

## Project Status

**Status:** In Progress  
**AWS Deployment:** Pending AWS account access

This project is currently being developed using local tools and Infrastructure as Code templates.

## Learning Outcomes

- AWS networking fundamentals.
- VPC and subnet architecture.
- Network segmentation and traffic control.
- Infrastructure as Code.
- Cloud security fundamentals.

## Author

**Miguel Mayor**

Computer Engineering Graduate | AWS re/Start Graduate | Aspiring Cloud Engineer

- GitHub: https://github.com/Macki099
- LinkedIn: https://www.linkedin.com/in/miguel-salvador-mayor-a1172a2ba/
