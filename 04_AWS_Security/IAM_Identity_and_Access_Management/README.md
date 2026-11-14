# Day 4 – IAM: Identity and Access Management

**Internship:** AWS & DevOps Internship  
**Class date:** Thursday, 5 November 2026

## Overview

IAM (Identity and Access Management) decides who can log in to an AWS account and what they are allowed to do. This session covered authentication, authorization, accountability, root and IAM users, IAM components, permissions, and the principle of least privilege.

## Study Resource

- [Day 4 IAM study notes PDF](resources/IAM_Identity_and_Access_Management_Day_4.pdf)

The study notes were prepared from the supplied Class 4 handout and whiteboard reference. The original source handout and whiteboard image were used during preparation but are not included in this repository upload.

## Topics Covered

### The three A's

- **Authentication:** proving who you are, using a username and password.
- **Authorization:** what you are allowed to do after you log in. Being authenticated does not mean every action is permitted.
- **Accountability:** tracking who did what, monitoring logins and activity, and reporting suspicious activity.

### Root user and IAM user

- The **root user** is the account owner and has full privileges. The class notes advise not using it for daily work.
- **IAM users** are separate identities created for people. Each user receives only the permissions needed for their task.
- Never share credentials. The class notes identify credential sharing as a compliance breach.

### IAM components

| Component | Meaning in the class notes |
|---|---|
| Users | Individual identities |
| Groups | A team of users who receive the same permissions together |
| Policies | JSON documents listing which resources and actions are allowed or denied |
| Roles | Provide temporary credentials so a person or service can perform a task; access ends afterward |

### Policy versus role

A policy grants permissions; it does not create credentials. A role provides temporary credentials when assumed for a task. The class notes contrast IAM users (long-term credentials) with roles (temporary credentials).

### Principle of least privilege

Give users only the permissions they need for their task. In the class demonstration, a user allowed to launch EC2 instances could perform that action but was denied other actions, such as accessing S3.

## Console Practice

The class handout's home practice is to create an IAM user and group, attach a policy that allows only EC2 read access, then try to open S3 as that user and observe the Deny message.

Follow [the IAM practical lab guide](practical/IAM_Lab_Guide.md). Complete the lab in your own AWS account before marking it as done.

## Interview and Exam Revision

- IAM stands for Identity and Access Management.
- IAM policies are written in JSON.
- The root user has full control of the account.
- A policy grants permissions; a role provides temporary credentials.
- Least privilege means granting only the access needed for the task.

## Quick Quiz

See [Day 4 Quiz](practical/Day_4_Quiz.md) for revision questions and answers.

## Evidence

Store screenshots of the completed lab in the `evidence/` folder. Do not include passwords, access keys, secret keys, recovery codes, or other credentials in screenshots.

---

*This documentation is based on the supplied Class 4 handout and whiteboard reference. The practical guide expands the handout into a suggested console workflow; it does not claim that the lab has already been completed.*
