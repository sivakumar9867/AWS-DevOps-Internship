# Day 4 – IAM Quick Quiz

Questions are based on the supplied Class 4 notes.

## Questions

1. What are the three A's discussed in IAM?
2. What is authentication?
3. What is authorization?
4. What does accountability mean in the context of IAM?
5. Who is the root user?
6. Why should the root user not be used for daily work?
7. What is an IAM user?
8. What is the purpose of an IAM group?
9. In what format are IAM policies written?
10. What does an IAM policy specify?
11. What is the purpose of an IAM role?
12. What is the difference between a policy and a role?
13. Which provides temporary credentials: an IAM user or a role?
14. Explain the principle of least privilege.
15. In the class demonstration, why could the test user access EC2 but receive a Deny message for S3?

## Answer Key

1. Authentication, Authorization, and Accountability.
2. Proving who you are, for example with a username and password.
3. Defining what actions you are allowed to perform after you log in.
4. Tracking who did what, monitoring logins and activity, and reporting suspicious activity.
5. The account owner identity with full privileges.
6. The notes advise not using it for daily work.
7. A separate identity created for a person, with permissions assigned for their tasks.
8. To manage a team of users who receive the same permissions together.
9. JSON.
10. Which resources and actions are allowed or denied.
11. To provide temporary credentials so a person or service can perform a task.
12. A policy grants permissions; a role provides temporary credentials when assumed.
13. A role.
14. Give users only the permissions they need for their task.
15. The user's permissions allowed the EC2 action but did not grant S3 access.

## Short scenario

A user can sign in to AWS but receives Access Denied when opening S3. Has authentication failed?

**Answer:** No. The user has authenticated, but authorization to perform the S3 action has not been granted.
