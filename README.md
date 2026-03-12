# AWS EC2 Linux Hardening Lab

## Overview
This project documents the deployment and security hardening of an Ubuntu 24.04 LTS instance in AWS EC2.  
The objective was to implement layered security controls, restrict remote access, and simulate brute-force mitigation within a cloud-hosted Linux environment.

---

## Environment
- AWS EC2 (us-east-1)
- Ubuntu 24.04 LTS
- SSH key-based authentication
- UFW (Uncomplicated Firewall)
- Fail2Ban intrusion prevention

---

## Architecture

Local Machine (macOS)
    ↓ SSH (Key-Based)
AWS EC2 Ubuntu Instance
    ↓
Security Controls:
- AWS Security Group (IP restricted)
- UFW Host Firewall
- Fail2Ban SSH monitoring

---

## Security Controls Implemented

### 1. SSH Hardening
- Disabled password authentication
- Disabled root login
- Enforced key-based authentication
- Validated SSH configuration before restart

## Incident Simulation

To validate intrusion prevention controls:

- Attempted failed SSH logins from test user
- Observed authentication failures in `/var/log/auth.log`
- Verified Fail2Ban monitoring of sshd jail
- Confirmed firewall restrictions via UFW rules

Result:
Layered controls successfully restricted unauthorized access attempts.


Configuration file modified:
```bash
/etc/ssh/sshd_config
## Security Implementation Evidence

### AWS Security Group Configuration
![AWS Security Groups](screenshots/AWS Security Groups.png)

### EC2 Instance Running
![Instance Running](screenshots/Instance Running.png)

### SSH Login from macOS
![SSH Login](screenshots/SSH login from MAC.png)

### Firewall Protection (UFW)
![Firewall](screenshots/Firewall protection.png)

### SSH Defense Rules
![UFW](screenshots/ufw-ssh-defense-restricted.png)

### Fail2Ban Intrusion Prevention
![Fail2Ban](screenshots/fail2Ban service.png)

### SSH Brute Force Monitoring
![Brute Force](screenshots/SSH monitoring for brute attacks.png)

### Authentication Log Monitoring
![Logs](screenshots/logs activity.png)

### Patch Management
![Updates](screenshots/Systems update patch mangement.png)
