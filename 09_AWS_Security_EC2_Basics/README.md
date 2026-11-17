# Day 9 – IAM, MFA, Shared Responsibility Model and EC2 Basics

**Internship:** AWS & DevOps Internship  
**Internship Day:** 9  
**Class date:** 11 November 2026

## Overview

This session revisited AWS Identity and Access Management (IAM) and introduced multi-factor authentication (MFA), the AWS Shared Responsibility Model, encryption with AWS Key Management Service (KMS), managed services, AWS service categories and Amazon EC2 fundamentals.

## Topics Learned

### IAM and least privilege
- IAM users, groups, policies and roles.
- The principle of least privilege: grant only the permissions required.
- Authentication, authorization and accountability.

### Multi-Factor Authentication (MFA)
- MFA adds another verification layer beyond a username and password.
- A six-digit one-time password (OTP) was used as the class example.

### AWS Shared Responsibility Model
- **Security OF the cloud:** AWS is responsible for the underlying infrastructure, including physical data centres, hardware, networking and virtualisation.
- **Security IN the cloud:** Customers are responsible for securing their data, IAM configuration, operating systems, applications and network controls.

### Encryption, KMS and data integrity
- Encryption protects readable information using cryptographic keys.
- AWS KMS stands for Key Management Service and supports key management.
- Data integrity concerns whether information remains accurate and unaltered.

### Core and managed services
- Core services highlighted: IAM, EC2 and S3.
- Managed services handle more of the underlying operational work through AWS.
- Operational examples discussed include health checks, scaling, load balancing, deployment, patch management and data replication.

### AWS service categories
- **Compute:** EC2, Elastic Beanstalk, Lambda, Lightsail and Outposts.
- **Storage:** S3, EBS and EFS.
- Other categories discussed: networking, databases, management and governance, monitoring and security.

### Amazon EC2 and IaaS
EC2 stands for **Elastic Compute Cloud**. It is an AWS compute service and an example of Infrastructure as a Service (IaaS). An EC2 instance is a virtual server that provides computing resources such as CPU, memory, storage and networking to run applications.

## Key Learning

AWS secures the underlying cloud infrastructure, while customers secure the identities, data, operating systems, network configurations and workloads they place in AWS. Least privilege, MFA and encryption are important parts of a secure cloud environment.

## Study Resource

- [IAM, MFA, Shared Responsibility Model and EC2 Basics – Day 9 PDF](Day_09_IAM_MFA_Shared_Responsibility_EC2_Basics.pdf)
