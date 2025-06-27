# AWS EC2 Instance Setup with Security Group Configuration

This guide outlines how to launch an Amazon EC2 instance and configure Security Groups to manage inbound and outbound traffic effectively. This setup is fundamental for deploying and securing virtual machines in AWS.

---

## Contents

- [Prerequisites](#prerequisites)  
- [Step 1: Launch EC2 Instance](#step-1-launch-ec2-instance)  
- [Step 2: Configure Key Pair](#step-2-configure-key-pair)  
- [Step 3: Create Security Group](#step-3-create-security-group)  
- [Step 4: Launch and Connect](#step-4-launch-and-connect)  
- [Resources](#resources)

---

## Prerequisites

- Active [AWS Account](https://aws.amazon.com/free)
- Basic knowledge of networking (IP, ports, protocols)
- SSH client or PuTTY installed locally

---

## Step 1: Launch EC2 Instance

1. Sign in to the [AWS Management Console](https://console.aws.amazon.com/).
2. Navigate to **EC2** from the Services menu.
3. Click **Launch Instance** and fill out the following:
   - **Name**: Descriptive name for the instance (e.g., `web-server`)
   - **Amazon Machine Image (AMI)**: Select *Ubuntu Server 22.04 LTS* (Free Tier eligible)
   - **Instance Type**: Choose `t2.micro`
   - **Network Settings**:
     - VPC: Default or custom
     - Subnet: Choose a public subnet
     - Auto-assign Public IP: Enable

---

## Step 2: Configure Key Pair

When prompted to choose a key pair:

- **Create new key pair** (if none exists)
  - Key pair type: RSA
  - Private key format: `.pem` (for OpenSSH) or `.ppk` (for PuTTY)
  - Download and securely store the key
    - Linux/macOS: Move to `~/.ssh/` and run `chmod 400 key.pem`
    - Windows: Use with PuTTY or WSL

---

## Step 3: Create Security Group

Security Groups are used to allow or deny traffic to your instance.

### Inbound Rules

| Purpose          | Protocol | Port | Source           | Description            |
|------------------|----------|------|------------------|------------------------|
| SSH              | TCP      | 22   | My IP / 0.0.0.0/0 | SSH access             |
| HTTP (Optional)  | TCP      | 80   | 0.0.0.0/0        | Web traffic            |
| HTTPS (Optional) | TCP      | 443  | 0.0.0.0/0        | Secure web traffic     |

> It is recommended to restrict SSH access to your own IP for security.

### Outbound Rules

By default, all outbound traffic is allowed. Keep this unless you have specific restrictions.

---

## Step 4: Launch and Connect

### Final Launch

1. Review all instance configurations
2. Click **Launch**
3. Wait until the instance shows status **Running**

### Connect via SSH

```bash
chmod 400 path/to/your-key.pem
ssh -i "path/to/your-key.pem" ubuntu@your-instance-public-ip

Replace your-instance-public-ip with the public IP address listed in the EC2 dashboard
```

## Resources

- [AWS EC2 Documentation](https://docs.aws.amazon.com/ec2/)

- [AWS Security Groups Guide](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html)


