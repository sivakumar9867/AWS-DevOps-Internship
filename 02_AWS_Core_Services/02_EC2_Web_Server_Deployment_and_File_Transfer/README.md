# Day 2 – EC2 Web Server Deployment and File Transfer

**Internship:** AWS & DevOps Internship  
**Practical environment:** AWS Console, Amazon EC2, Amazon Linux 2023, Apache HTTP Server, SSH, WinSCP (SFTP)

## Overview

This practical focused on connecting to a Linux EC2 instance, transferring files from a Windows computer to the instance, assigning an Elastic IP, and deploying a custom webpage using Apache HTTP Server.

## Tasks Performed

### 1. EC2 instance and SSH access

- Used an Amazon Linux 2023 EC2 instance (`t2.micro`).
- Connected from Windows using the instance key pair and the `ec2-user` account.
- Verified the Linux environment with `whoami`, `hostname`, and `/etc/os-release`.

```bash
ssh -i "Linux-file-transfer.pem" ec2-user@<EC2-Public-IP>
```

### 2. File transfer using WinSCP

- Configured WinSCP to connect over SFTP on TCP port 22.
- Used the EC2 private key (converted to PuTTY `.ppk` format for WinSCP).
- Transferred four text files from Windows to `/home/ec2-user/`.
- Verified the files and their contents from the Linux terminal: `final1.txt`, `final2.txt`, `final3.txt`, and `final4.txt`.

```bash
ls -lh /home/ec2-user/
```

### 3. Elastic IP and security group

- Allocated an Elastic IP and associated it with the Linux EC2 instance.
- Configured the instance security group to allow HTTP traffic on TCP port 80 from `0.0.0.0/0`.
- Restricted SSH access on TCP port 22 to the user's public IP address.

| Type | Protocol | Port | Source |
|---|---|---:|---|
| SSH | TCP | 22 | User's public IP (`/32`) |
| HTTP | TCP | 80 | `0.0.0.0/0` |

### 4. Apache installation and webpage deployment

Installed and enabled Apache on Amazon Linux 2023:

```bash
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
sudo systemctl status httpd --no-pager
```

Created a custom HTML page at `/var/www/html/index.html`. The page identified the AWS & DevOps Internship practical and displayed the EC2, Amazon Linux 2023, and Apache deployment details.

The webpage was successfully opened in a laptop browser using the instance's public IPv4 address over HTTP.

**Verification note:** Mobile-browser access was attempted but returned `ERR_CONNECTION_TIMED_OUT`; mobile access is therefore not claimed as verified.

## Evidence

The Day 2 evidence PDF and ten supporting screenshots are included in the downloadable Day 2 GitHub package. They have not yet been uploaded as binary files to this repository.

## Cleanup

After evidence collection:
- The Linux EC2 instance was selected for termination.
- The Elastic IP was released.
- The separate Windows EC2 instance was left untouched.

## Key Learning Outcomes

- Connecting to a Linux EC2 instance using SSH.
- Transferring files securely with WinSCP over SFTP.
- Associating and releasing an Elastic IP.
- Configuring inbound security group rules for SSH and HTTP.
- Installing, enabling, and checking Apache with `systemctl`.
- Publishing and verifying a custom HTML webpage on EC2.
- Cleaning up project resources after completing the practical.

---

*This documentation records the practical tasks performed during the Day 2 internship session.*
