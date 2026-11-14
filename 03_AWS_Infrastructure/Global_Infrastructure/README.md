# Class 3 – AWS Global Infrastructure

**Class date:** 4 November 2026  
**Internship:** AWS & DevOps Internship

## Overview

This class introduced the three building blocks of AWS global infrastructure—Regions, Availability Zones, and Edge Locations—and the factors to consider when choosing an AWS Region.

## Topics Covered

### AWS Regions

- A Region is a separate geographic area where AWS operates its services.
- Examples covered in class include Mumbai, Singapore, Tokyo, Sydney, Frankfurt, London, and North Virginia.
- The class notes state that AWS has more than 25 Regions.
- Regions are independent, so an issue in one Region does not directly affect another.
- The AWS console provides a Region selector at the top right.

### Availability Zones (AZs)

- Each Region contains several Availability Zones.
- An AZ consists of one or more data centres.
- AZs are separated to reduce the chance that a disaster in one zone affects another.
- Distributing an application across multiple AZs can improve availability and support recovery if one zone fails.

### Edge Locations and Points of Presence

- Edge Locations are placed closer to users, including in major cities.
- Amazon CloudFront is a content delivery network (CDN).
- CloudFront keeps copies of popular content at nearby Edge Locations to reduce latency and deliver content faster.

### Choosing an AWS Region

The class identified these considerations:

- Proximity to users and resulting latency
- Regional pricing differences
- Availability of required AWS services
- Network bandwidth
- Legal and compliance requirements

### Free Tier Account

The class notes covered the basic requirements for creating an AWS account:

- A valid email address
- A phone number that can receive OTPs
- A valid debit or credit card

The notes also emphasize staying within Free Tier limits and terminating resources that are no longer needed.

## Remember for Interviews and Exams

- A Region contains Availability Zones.
- An Availability Zone contains one or more data centres.
- Edge Locations help deliver content closer to users; CloudFront uses them.
- Using more than one AZ can support backup and disaster recovery.
- Latency means delay.

## Quick Quiz

**1. What is an Availability Zone?**  
One or more data centres inside a Region, isolated from other zones.

**2. Why are AZs placed far apart?**  
So a disaster in one zone does not affect the others.

**3. What does CloudFront do?**  
It delivers content from a nearby Edge Location to reduce latency.

**4. Name two factors for choosing a Region.**  
Latency to users and cost. Service availability and compliance are also factors.

**5. Where do you change the Region in the console?**  
Using the Region drop-down at the top right.

## Practice

Log in to the AWS console, switch the selected Region to Mumbai and then Singapore, and observe that resources are separate in each Region.

## LinkedIn Update

[View the published Day 3 LinkedIn post](https://lnkd.in/p/gGZVW7sc)

## Class Material

The original class notes and prepared learning PDF are available in the [resources folder](resources/).

---

*Documentation prepared from the Class 3 notes supplied for the internship. The topics above reflect the class material; this entry does not claim a practical deployment.*
