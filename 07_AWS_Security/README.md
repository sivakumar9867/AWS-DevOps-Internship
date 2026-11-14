# Day 7 – IAM: Identity and Access Management

**Internship:** AWS & DevOps Internship  
**Internship Day:** 7  
**Class Number:** 4  
**Class date:** 9 November 2026

## Overview

This was a learning session covering AWS Identity and Access Management (IAM). No hands-on lab was completed as part of this session.

The session introduced how IAM controls who can access AWS resources and what actions they are permitted to perform.

## Topics Learned

### The three A's
- **Authentication:** proving who you are.
- **Authorization:** determining what you are allowed to do after signing in.
- **Accountability:** tracking user activity and actions.

### Root user and IAM users
- The **root user** is the account owner identity with full privileges. It should not be used for routine daily work.
- **IAM users** are separate identities created for people and assigned permissions for their tasks.
- Credentials should never be shared.

### IAM components

| Component | Purpose |
|---|---|
| Users | Individual identities |
| Groups | Organize users who need the same permissions |
| Policies | JSON documents that define allowed or denied actions |
| Roles | Provide temporary credentials when assumed |

### Policy versus role

A policy defines permissions. A role is an identity that can be assumed to obtain temporary credentials.

### Principle of least privilege

Grant only the permissions required to perform a specific task. The class discussion illustrated this with EC2 access being allowed while an ungranted S3 action was denied.

## Study Resource

- [IAM – Day 7, Class 4 PDF](IAM_Day_7_Class_4.pdf)

---

*This entry documents the learning content from Class 4 on 9 November 2026. It does not claim that a practical lab or hands-on implementation was completed.*
