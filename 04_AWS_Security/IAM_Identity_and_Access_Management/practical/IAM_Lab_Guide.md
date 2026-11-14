# Day 4 Practical – IAM User, Group and EC2 Read-Only Access

## Objective

Follow the Class 4 home-practice task: create an IAM user and group, grant EC2 read access, then test that the user cannot access S3.

**Important:** Perform this only in your own AWS training account. Do not share passwords, access keys, secret keys, or MFA recovery codes. Do not use the root user for routine lab work.

## Before starting

- Sign in to the AWS Management Console using your authorized account.
- Keep the root account credentials private.
- If this is a personal account, ensure root MFA is enabled.
- Use a unique lab username, for example `day4-ec2-readonly-user`.

## Part A – Create a customer-managed read-only policy

1. Open **IAM → Policies → Create policy**.
2. Choose the **JSON** editor.
3. Use this minimal example policy for EC2 describe/read operations:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowEC2Describe",
      "Effect": "Allow",
      "Action": "ec2:Describe*",
      "Resource": "*"
    }
  ]
}
```

4. Review the policy and name it `Day4-EC2-ReadOnly`.
5. Create the policy.

This example grants EC2 `Describe*` actions. It is a practical interpretation of EC2 read access for this exercise, not a claim that it covers every possible read operation in every AWS service.

## Part B – Create an IAM group and attach the policy

1. Open **IAM → User groups → Create group**.
2. Name the group `Day4-EC2-Readers`.
3. Attach `Day4-EC2-ReadOnly`.
4. Create the group.

## Part C – Create the IAM user

1. Open **IAM → Users → Create user**.
2. Enter `day4-ec2-readonly-user`.
3. For console practice, enable AWS Management Console access and set a strong temporary password.
4. Add the user to `Day4-EC2-Readers`.
5. Complete creation.
6. Store any sign-in details securely. Never add them to GitHub or screenshots.

For this exercise, do not create programmatic access keys unless a separate task explicitly requires them.

## Part D – Test the permissions

1. Open a private/incognito browser window.
2. Sign in as the new IAM user using the account's IAM sign-in URL and the credentials you securely stored.
3. Open the EC2 console.
4. Confirm that EC2 information pages using describe/list operations can be viewed.
5. Open the S3 console.
6. Confirm that the user receives an Access Denied message when attempting to list buckets or access S3 resources.

An IAM user can authenticate successfully and still be denied access to services for which no permission has been granted. This illustrates the difference between authentication and authorization.

## Part E – Record evidence

Capture screenshots only after the lab works. Suggested filenames:

1. `01_IAM_Policy_JSON.png` – policy JSON before creation; hide account-sensitive details.
2. `02_IAM_Policy_Created.png` – policy summary.
3. `03_IAM_Group_Created.png` – group and attached policy.
4. `04_IAM_User_Created.png` – user listed in IAM; do not show credentials.
5. `05_EC2_Read_Access.png` – EC2 console page accessible to the test user.
6. `06_S3_Access_Denied.png` – S3 denial message.
7. `07_IAM_Permissions_Summary.png` – final group/user permissions overview.

Do not capture or publish passwords, access keys, secret keys, MFA QR codes, recovery codes, private email addresses, or other secrets.

## Part F – Cleanup

After recording evidence:

1. Sign out of the test IAM user.
2. Delete the temporary IAM user if it is no longer needed.
3. Delete the test group after removing its members.
4. Delete the custom policy only after detaching it from all identities.
5. Keep your account's normal security configuration intact.

Do not delete or modify the root user or any pre-existing IAM identities/policies.

## Completion checklist

- [ ] Created `Day4-EC2-ReadOnly` policy.
- [ ] Created `Day4-EC2-Readers` group.
- [ ] Attached the policy to the group.
- [ ] Created the test IAM user and added it to the group.
- [ ] Confirmed EC2 read/describe access.
- [ ] Confirmed S3 access is denied.
- [ ] Captured safe evidence screenshots.
- [ ] Cleaned up temporary lab identities if no longer needed.

**Status:** This is a lab guide. Mark tasks complete only after performing and verifying them in the AWS console.
