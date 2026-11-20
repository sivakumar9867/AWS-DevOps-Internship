# Mini Project 1 – AWS VPC Peering

**Internship:** AWS & DevOps Internship  
**Project:** Mini Project 1  
**Project date:** 18 November 2026  
**AWS Region:** Asia Pacific (Mumbai) – `ap-south-1`

## Overview

This project demonstrates private IPv4 connectivity between two Amazon Virtual Private Clouds (VPCs) using VPC Peering. VPC A contains a public bastion host and a private application instance. VPC B contains a second private application instance. The bastion provides the administration entry point, while route tables and security groups control access between the networks.

## Architecture and Network Design

| Component | Configuration |
|---|---|
| VPC A | `ewb-vpc-a` – `10.10.0.0/16` |
| VPC B | `ewb-vpc-b` – `10.20.0.0/16` |
| Public subnet | `ewb-a-public` – `10.10.1.0/24` |
| Private subnet A | `ewb-a-private` – `10.10.2.0/24` |
| Private subnet B | `ewb-b-private` – `10.20.1.0/24` |
| Peering connection | `ewb-a-b-peer` |
| Compute | One public bastion and two private EC2 instances |

The VPC CIDR ranges are non-overlapping. VPC A has an internet gateway for the public subnet. VPC B has no internet gateway.

## Implementation

1. Created two VPCs with non-overlapping IPv4 CIDR ranges.
2. Created one public subnet and two private subnets.
3. Attached an internet gateway to VPC A and configured route-table associations.
4. Configured security groups to restrict SSH and ICMP inbound access to the designated hosts.
5. Launched three Amazon Linux 2023 EC2 instances: one public bastion and two private application instances.
6. Established SSH administration through the bastion host.
7. Created and accepted the VPC peering connection.
8. Added the required forward and return routes to the route tables.
9. Tested private connectivity in both directions, captured a connectivity interruption, and verified recovery.
10. Removed the lab resources after testing and evidence collection.

## Verification Results

- VPC peering reached **Active** state.
- App-A (`10.10.2.10`) successfully reached App-B (`10.20.1.10`): 4 packets received, 0% packet loss.
- App-B successfully reached App-A: 4 packets received, 0% packet loss.
- SSH access to both private application instances was demonstrated through the bastion.
- The report also records a connectivity interruption (100% packet loss) followed by successful recovery (0% packet loss).
- Cleanup evidence records termination and removal actions for the lab resources.

## Evidence and Report

The implementation report contains the architecture, configuration tables, explanations, verification results, viva preparation, resource inventory, and 40 numbered evidence figures.

- [Open the evidence folder](evidence/)

## Key Learning

- VPC CIDR planning and subnet design
- Public and private subnet routing
- VPC peering and non-transitive connectivity
- Forward and return route configuration
- Security group source restrictions
- Bastion-host administration of private EC2 instances
- Private connectivity verification and troubleshooting
- AWS lab cleanup
