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

Example SSH command:

```bash
ssh -i "Linux-file-transfer.pem" ec2-user@<EC2-Public-IP>
```

### 2. File transfer using WinSCP

- Configured WinSCP to connect over SFTP on TCP port 22.
- Used the EC2 private key (converted to PuTTY `.ppk` format for WinSCP).
- Transferred four text files from Windows to `/home/ec2-user/`.
- Verified the files and their contents from the Linux terminal.

Files transferred:
- `final1.txt`
- `final2.txt`
- `final3.txt`
- `final4.txt`

Verification commands:

```bash
ls -lh /home/ec2-user/

for f in final1.txt final2.txt final3.txt final4.txt; do
    echo "---- $f ----"
    head -n 3 "$f"
done
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

Created a custom HTML page at:

```text
/var/www/html/index.html
```

The page identified the AWS & DevOps Internship practical and displayed the EC2, Amazon Linux 2023, and Apache deployment details.

The webpage was successfully opened in a laptop browser using the instance's public IPv4 address over HTTP.

**Verification note:** Mobile-browser access was attempted but returned `ERR_CONNECTION_TIMED_OUT`; mobile access is therefore not claimed as verified.

## Evidence

Screenshots captured during the practical are available in the `evidence/` folder.

| # | Evidence |
|---:|---|
| 1 | [EC2 instance details](evidence/01_EC2_Instance_Details.png) |
| 2 | [Elastic IP association](evidence/02_Elastic_IP_Association.png) |
| 3 | [Security group inbound rules](evidence/03_Security_Group_Rules.png) |
| 4 | [SSH connection and Linux details](evidence/04_SSH_Connection.png) |
| 5 | [WinSCP file transfer](evidence/05_WinSCP_File_Transfer.png) |
| 6 | [Linux file verification](evidence/06_Linux_File_Verification.png) |
| 7 | [Apache service status](evidence/07_Apache_Service_Status.png) |
| 8 | [Custom webpage deployment](evidence/08_Custom_Webpage_Deployment.png) |
| 9 | [EC2 termination](evidence/09_EC2_Termination.png) |
| 10 | [Elastic IP release](evidence/10_Elastic_IP_Release.png) |

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

*This documentation records the practical tasks performed and the evidence captured during the Day 2 internship session.*
