# Day 8 – EC2 Launch Concepts, Instance Types, Pricing and Security Groups

**Internship:** AWS & DevOps Internship  
**Internship Day:** 8  
**Class date:** 10 November 2026  
**Source:** Day 02 – EC2 Instances: Launch Steps, Types, Pricing, Key Pairs and Security Groups (15-page step-by-step class guide)

## Overview

This session introduced Amazon EC2 and the process of launching an EC2 instance. The class covered the eight launch steps, AMI choices, instance types and families, pricing categories, key pairs, security groups, and EC2 instance states.

## 1. What is an EC2 instance?

An EC2 instance is a virtual server in the AWS cloud that provides CPU, RAM, storage, networking, and an operating system to run applications. EC2 belongs to the Compute category and is an example of Infrastructure as a Service (IaaS).

The class described the pay-as-you-go model: users pay for the service they use, while deploying code, running applications, and securing their resources.

## 2. Eight steps to launch an EC2 instance

The class presented this sequence:

1. Choose an AMI.
2. Choose an instance type.
3. Configure the instance.
4. Add storage.
5. Add tags.
6. Configure security groups.
7. Review the configuration.
8. Add a key pair.

The trainer demonstrated opening EC2 from the AWS Console and selecting a Region before launching. The class demonstration used US East (N. Virginia).

## 3. Amazon Machine Images (AMIs)

AMI stands for **Amazon Machine Image**. Selecting an AMI means choosing the operating system and setup for the instance.

The guide covered these AMI categories:

- **Quickstart AMI:** the default images.
- **Marketplace AMI:** images from third-party vendors, potentially with pre-configured security tools or database software.
- **Community AMI:** images shared by the public.
- **My AMI:** a customised image created by the user.

The class demonstration used Amazon Linux 2023.

## 4. Instance types and sizes

An instance type combines a **family and a size**. For example, in `t3.micro`, `t3` is the family and `micro` is the size.

The guide used these size examples: nano, micro, small, medium, and large. It explained that a larger size provides more virtual CPU and memory. The console examples shown were:

| Instance type | vCPU | Memory |
|---|---:|---:|
| t3.micro | 2 | 1 GB |
| t3.large | 2 | 8 GB |

Choose a type based on the CPU and memory requirements of the workload.

## 5. Instance families

The guide grouped instance families into:

- **General purpose:** mixed-use workloads.
- **Compute:** compute-focused applications.
- **Memory:** memory-focused applications.
- **Storage:** storage-focused applications.
- **Accelerated compute:** applications requiring accelerated processing.

The guide also notes that instance types are classified by both family category and pricing category.

## 6. EC2 pricing categories

The class introduced these pricing categories:

- On-Demand
- Reserved
- Scheduled Reserved
- Dedicated Host
- Dedicated Instances
- Spot

The trainer described On-Demand as allowing an instance to be launched immediately without advance reservation. Reserved options were discussed with upfront, partial-upfront, and no-upfront payment choices. Scheduled Reserved was explained as choosing when an instance runs. Dedicated Hosts and Dedicated Instances were also introduced.

The guide described Spot Instances as lower-cost instances that can be interrupted.

## 7. Key pairs for secure access

A key pair is used to connect to an EC2 instance securely over SSH. It consists of a public key and a private key. The class demonstration created an RSA key pair and downloaded the private key in `.pem` format.

Keep the private key safe. The guide highlights losing the private key as a mistake to avoid.

## 8. Security groups

Security groups act as the firewall for an EC2 instance.

- The guide explains that inbound traffic is blocked by default.
- Rules can be added to allow required traffic.
- The class example allowed HTTP traffic on port 80 from Anywhere IPv4.
- Security groups are stateful, as described in the class.

Only open the ports and sources required for the intended access.

## 9. Launching and EC2 instance states

Before launching, review the configuration and then select **Launch instance**.

The guide covered these instance states and transitions:

- **Running:** the instance is started.
- **Stopping → Stopped:** the instance is being stopped and has stopped.
- **Shutting down → Terminated:** the instance is being terminated.
- **Restarting → Running:** the instance is restarting and returns to running.

The console's Instance state menu can be used to stop, restart, or terminate an instance.

## 10. User data script shown in class

Example web-server start-up script:

```bash
#!/bin/bash
yum -y install httpd
systemctl enable httpd
systemctl start httpd
echo '<html><h1>Hello From Your Web Server!</h1></html>' > /var/www/html/index.html
```

## Console settings shown in the demonstration

| Setting | Value shown |
|---|---|
| Region | US East (N. Virginia) |
| AMI | Amazon Linux 2023 |
| Instance type | t3.micro (2 vCPU, 1 GB) |
| Storage | 8 GiB gp3 |
| Key pair | test kp |
| Key pair type | RSA |
| Private key format | .pem |
| Security group example | HTTP, port 80, Anywhere IPv4 |



## Common mistakes highlighted in the guide

- Exceeding the 30 GB storage amount discussed for the free-tier account.
- Forgetting to delete practice resources after use.
- Launching multiple instances with the same name without using tags to distinguish them.
- Expecting inbound traffic to reach an instance without an inbound security group rule.
- Losing the private key file.
- Confusing the pricing categories discussed in class.

## Key learning outcomes

- Explain what an EC2 instance provides and why it is an IaaS service.
- Recall the eight-step EC2 launch workflow.
- Distinguish AMI categories.
- Read an instance type as family plus size.
- Identify the instance family and pricing categories introduced in class.
- Explain the purpose of an EC2 key pair.
- Describe security groups as stateful instance firewalls.
- Recognise the main EC2 instance states.

## Study Resource

[EC2 Launch Concepts – Day 8 PDF](EC2_Day_8.pdf)

