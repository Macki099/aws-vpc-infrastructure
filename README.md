# AWS VPC Networking Lab: Public and Private Subnets with EC2

## 📌 Project Overview

This project demonstrates the implementation of a custom Amazon Virtual Private Cloud (VPC) environment using AWS. It includes the creation of public and private subnets, route tables, an Internet Gateway, Network ACLs, Security Groups, and an EC2 instance.

The objective is to gain hands-on experience with AWS networking fundamentals, infrastructure configuration, and secure access to cloud resources.

## 🏗️ Architecture

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/986fade0-ae76-4537-9f52-408588fa4adb" />


```text
                         INTERNET
                             |
                             |
                    Internet Gateway
                             |
                             |
                    VPC: 10.0.0.0/16
                             |
              +--------------+--------------+
              |                             |
              |                             |
        PUBLIC SUBNET                 PRIVATE SUBNET
        10.0.1.0/24                   10.0.2.0/24
              |                             |
        Public Route Table            Private Route Table
              |                             |
        0.0.0.0/0 -> IGW                Local Route
              |
              |
         EC2 INSTANCE
              |
        Security Group
           SSH: 22
              |
      EC2 Instance Connect
```

## ☁️ AWS Services Used

| AWS Service | Purpose |
|---|---|
| Amazon VPC | Creates an isolated virtual network |
| Subnets | Separates public and private resources |
| Route Tables | Controls network traffic routing |
| Internet Gateway | Provides internet connectivity |
| Network ACL | Controls inbound and outbound subnet traffic |
| Security Groups | Controls instance-level network traffic |
| Amazon EC2 | Hosts the virtual machine |
| EC2 Instance Connect | Provides browser-based SSH access |

## ⚙️ Implementation Steps

### 1. Create a VPC

Created a custom VPC with the following configuration:

| Configuration | Value |
|---|---|
| VPC Name | VPC-lab |
| IPv4 CIDR | `10.0.0.0/16` |

### 2. Create Two Subnets

Created two subnets within the custom VPC.

**Public Subnet**

| Configuration | Value |
|---|---|
| Subnet Name | Public-subnet |
| IPv4 CIDR | `10.0.1.0/24` |

**Private Subnet**

| Configuration | Value |
|---|---|
| Subnet Name | Private-subnet |
| IPv4 CIDR | `10.0.2.0/24` |

The public subnet is intended for resources requiring direct internet connectivity, while the private subnet is intended for resources that should not be directly accessible from the internet.

### 3. Create Two Route Tables

Created separate route tables for the public and private subnets.

**Public Route Table**
- Created a public route table.
- Added a default route pointing to the Internet Gateway.
- Configured the destination as `0.0.0.0/0`.
- Associated the route table with the public subnet.

| Destination | Target |
|---|---|
| `10.0.0.0/16` | Local |
| `0.0.0.0/0` | Internet Gateway |

**Private Route Table**
- Created a separate private route table.
- Intended to be associated with the private subnet.
- Retained the default local VPC route.
- No Internet Gateway route was configured.

### 4. Create and Attach an Internet Gateway

- Created an Internet Gateway.
- Attached the Internet Gateway to `VPC-lab`.
- Added the Internet Gateway as the target of the public route table's default route.

### 5. Configure Network ACL (NACL)

Created a Network ACL to control inbound and outbound traffic at the subnet level.

For this initial lab configuration:
- Allowed all inbound traffic.
- Allowed all outbound traffic.

This configuration was used to simplify connectivity testing.

### 6. Create a Security Group

Created a Security Group named `SG-lab`.

Configured the following inbound rule:

| Type | Protocol | Port Range | Purpose |
|---|---|---|---|
| SSH | TCP | 22 | Remote instance access |

Attached `SG-lab` to the EC2 instance.

**Security Note:** For production environments, SSH access should be restricted to trusted IP addresses.

### 7. Launch an EC2 Instance

Created an EC2 instance with the following networking configuration:

- Selected the custom VPC (`VPC-lab`).
- Selected the appropriate subnet.
- Attached the `SG-lab` Security Group.
- Configured the instance for SSH connectivity.

### 8. Connect to EC2 Using EC2 Instance Connect

Used EC2 Instance Connect through the AWS Management Console to establish an SSH connection to the EC2 instance.

**Result:** Successfully accessed the EC2 instance through the browser-based terminal.

## 📸 Screenshots and Documentation

Screenshots documenting the implementation will be uploaded to the repository.

```text
screenshots/
├── vpc-configuration.png
├── subnet-configuration.png
├── route-tables.png
├── internet-gateway.png
├── nacl-configuration.png
├── security-group.png
└── ec2-instance-connect.png
```

## 🧠 Skills Demonstrated

- AWS VPC Configuration
- IPv4 CIDR Block Planning
- Public and Private Subnet Design
- Route Table Configuration
- Internet Gateway Configuration
- Network ACL Configuration
- Security Group Management
- EC2 Instance Deployment
- SSH Fundamentals
- EC2 Instance Connect

## 🚀 Future Improvements

- [ ] Verify public and private subnet route table associations.
- [ ] Test outbound internet connectivity from the public EC2 instance.
- [ ] Deploy another EC2 instance in the private subnet.
- [ ] Configure a Bastion Host for private EC2 access.
- [ ] Configure a NAT Gateway for private subnet outbound internet access.
- [ ] Implement more restrictive Network ACL and Security Group rules.
- [ ] Document connectivity and security testing.
- [ ] Create a detailed AWS architecture diagram.

## 📚 Key Learnings

Through this project, I gained practical experience in building a custom AWS networking environment and understanding how VPCs, subnets, route tables, Internet Gateways, NACLs, and Security Groups work together.

I also gained hands-on experience deploying an EC2 instance and accessing it through EC2 Instance Connect.

---

**Project Category:** AWS Networking / Cloud Infrastructure  
**Cloud Provider:** Amazon Web Services (AWS)  
**Status:** Initial Implementation Completed
