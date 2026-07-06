<div align="center">

# 🛡️ Windows & Linux Firewall Configuration Lab

### Configure • Test • Secure • Validate Firewall Rules

![Windows](https://img.shields.io/badge/Windows-10-0078D6?style=for-the-badge&logo=windows)
![Ubuntu](https://img.shields.io/badge/Ubuntu-22.04-E95420?style=for-the-badge&logo=ubuntu)
![Windows Defender](https://img.shields.io/badge/Firewall-Windows%20Defender-success?style=for-the-badge)
![UFW](https://img.shields.io/badge/UFW-Enabled-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Level](https://img.shields.io/badge/Level-Beginner--Intermediate-blueviolet?style=for-the-badge)

<a href="https://github.com/abhiramyadav03">
<img src="https://img.shields.io/badge/GitHub-abhiramyadav03-181717?style=for-the-badge&logo=github"/>
</a>

<a href="https://www.linkedin.com/in/rapothulaabhiram/">
<img src="https://img.shields.io/badge/LinkedIn-Abhiram%20Rapothula-0A66C2?style=for-the-badge&logo=linkedin"/>
</a>

</div>

---

# 📖 Overview

This project demonstrates the configuration, testing, and validation of **Windows Defender Firewall** and **Ubuntu Uncomplicated Firewall (UFW)** in a controlled virtual lab environment.

The objective is to understand how host-based firewalls protect systems by filtering network traffic, blocking unnecessary services, and allowing trusted communications. During this lab, firewall rules were created, verified, tested, and removed to understand their impact on endpoint security.

This project develops practical firewall administration skills that are essential for **SOC Analysts, Security Analysts, System Administrators, Blue Team Engineers, and Cybersecurity Professionals**.

---

# 🎯 Objectives

- Configure Windows Defender Firewall
- Configure Ubuntu UFW
- Create inbound firewall rules
- Block unnecessary network services
- Verify firewall configurations
- Test firewall functionality
- Understand host-based security
- Reduce attack surface
- Practice system hardening

---

# 📑 Table of Contents

- Overview
- Objectives
- Lab Environment
- Tools Used
- Firewall Concepts
- Windows Defender Firewall
- Ubuntu UFW
- Testing & Validation
- Results
- Security Benefits
- Skills Demonstrated
- Learning Outcomes
- References
- License
- Author

---

# 🖥️ Lab Environment

| Component | Details |
|-----------|----------|
| Host Operating System | Windows 10 |
| Linux Virtual Machine | Ubuntu |
| Virtualization Platform | VMware Workstation |
| Windows Firewall | Windows Defender Firewall |
| Linux Firewall | UFW |
| Test Port | TCP 23 (Telnet) |

---

# 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| Windows Defender Firewall | Configure Windows firewall rules |
| UFW | Linux firewall management |
| Command Prompt | Execute Windows firewall commands |
| Linux Terminal | Configure UFW |
| VMware Workstation | Virtual Lab Environment |

---

# 🔥 Firewall Concepts

## What is a Firewall?

A firewall is a security mechanism that monitors and controls incoming and outgoing network traffic based on predefined security rules.

Firewalls protect systems by allowing trusted traffic while blocking unauthorized or potentially malicious connections.

---

## Types of Firewalls

- Host-Based Firewall
- Network Firewall
- Stateful Firewall
- Next-Generation Firewall (NGFW)

This project focuses on **Host-Based Firewalls**.

---

## Inbound Rules

Inbound rules control traffic entering the computer.

Examples include:

- Allow Remote Desktop
- Block Telnet
- Allow HTTP
- Allow HTTPS

---

## Outbound Rules

Outbound rules control traffic leaving the computer.

Examples include:

- Block specific applications
- Allow trusted software
- Restrict internet access

---

## Why Firewalls Matter

Proper firewall configuration helps:

- Prevent unauthorized access
- Reduce attack surface
- Protect exposed services
- Improve endpoint security
- Enforce network security policies

---

# 🪟 Windows Defender Firewall Configuration

## Step 1 – Open Windows Defender Firewall

1. Open **Control Panel**
2. Navigate to **System and Security**
3. Select **Windows Defender Firewall**
4. Open **Advanced Settings**
5. Select **Inbound Rules**

---

## Step 2 – Create a New Rule

Select:

```
New Rule
```

Choose:

```
Port
```

Protocol:

```
TCP
```

Port Number:

```
23
```

Action:

```
Block the Connection
```

Apply the rule to:

- Domain
- Private
- Public

Rule Name:

```
Block Telnet Port 23
```

---

## Step 3 – Using Command Prompt

### Create Rule

```cmd
netsh advfirewall firewall add rule name="Block Telnet port 23" dir=in action=block protocol=TCP localport=23
```

### Verify Rule

```cmd
netsh advfirewall firewall show rule name="Block Telnet port 23"
```

### Remove Rule

```cmd
netsh advfirewall firewall delete rule name="Block Telnet port 23"
```

---

## Explanation

### Create Rule

Creates a new inbound firewall rule that blocks TCP traffic on Port 23.

### Verify Rule

Displays the firewall rule to ensure it was created successfully.

### Delete Rule

Removes the firewall rule after testing to restore the original configuration.

---

# 🐧 Ubuntu UFW Configuration

## Enable UFW

```bash
sudo ufw enable
```

## Check Firewall Status

```bash
sudo ufw status verbose
```

## Default Policies

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

## Block Telnet

```bash
sudo ufw deny 23/tcp
```
## Allow SSH

```bash
sudo ufw allow ssh
```

### Disable UFW (Optional)

```bash
sudo ufw disable
```

### Explanation

| Command | Description |
|---------|-------------|
| `sudo ufw enable` | Enables the firewall. |
| `sudo ufw status verbose` | Displays the current firewall status and configured rules. |
| `sudo ufw default deny incoming` | Blocks all incoming connections by default. |
| `sudo ufw default allow outgoing` | Allows all outgoing connections. |
| `sudo ufw deny 23/tcp` | Blocks Telnet traffic on TCP Port 23. |
| `sudo ufw allow ssh` | Allows SSH connections for remote administration. |
| `sudo ufw disable` | Disables the firewall if required. |

---

# 🧪 Testing & Validation

After configuring both firewalls, validation was performed to verify that the rules were applied correctly.

## Windows Firewall Testing

| Test | Expected Result | Status |
|------|-----------------|--------|
| Firewall Enabled | Enabled | ✅ |
| Rule Created | Successful | ✅ |
| Rule Verified | Visible in Firewall Rules | ✅ |
| Port 23 | Blocked | ✅ |
| Rule Removed | Successful | ✅ |

---

## Ubuntu UFW Testing

| Test | Expected Result | Status |
|------|-----------------|--------|
| UFW Enabled | Active | ✅ |
| Status Verified | Successful | ✅ |
| Incoming Traffic | Denied by Default | ✅ |
| Outgoing Traffic | Allowed | ✅ |
| Port 23 | Blocked | ✅ |
| SSH | Allowed | ✅ |

---

# 📊 Results

The firewall configuration was successfully implemented on both Windows and Ubuntu systems.

### Windows

- Successfully created inbound firewall rules.
- Blocked Telnet traffic on TCP Port 23.
- Verified firewall configuration.
- Removed test rule after validation.

### Ubuntu

- Successfully enabled UFW.
- Configured default security policies.
- Blocked Telnet traffic.
- Allowed SSH connections.
- Verified firewall status.

---

# 🛡️ Security Benefits

Implementing host-based firewalls provides several security advantages.

| Benefit | Description |
|---------|-------------|
| Attack Surface Reduction | Blocks unnecessary network services. |
| Access Control | Allows only authorized traffic. |
| Endpoint Protection | Protects individual systems from unwanted connections. |
| Network Segmentation | Restricts communication between hosts when required. |
| Defense in Depth | Adds an additional layer of security. |

---

# 📌 Key Findings

- Windows Defender Firewall successfully blocked inbound Telnet traffic.
- Ubuntu UFW denied connections to TCP Port 23.
- Firewall rules were successfully verified after creation.
- Firewall configurations improved endpoint protection.
- Host-based firewalls play a critical role in system hardening.

---

# 💡 Skills Demonstrated

- Windows Defender Firewall Administration
- Ubuntu UFW Configuration
- Firewall Rule Management
- Host-Based Security
- Network Security Fundamentals
- Windows Command Line
- Linux Terminal Administration
- Port Blocking
- Security Validation
- System Hardening

---

# 🎓 Learning Outcomes

After completing this project, I gained practical experience in:

- Configuring Windows Defender Firewall.
- Managing Ubuntu UFW.
- Creating inbound firewall rules.
- Blocking unnecessary network services.
- Testing firewall configurations.
- Understanding firewall concepts.
- Strengthening endpoint security.
- Applying host-based security controls.

---

# 🚀 Future Improvements

Potential enhancements for this lab include:

- Configure outbound firewall rules.
- Create application-based firewall policies.
- Implement logging and monitoring.
- Test firewall behavior using Nmap.
- Integrate firewall logs into a SIEM platform such as Splunk or Wazuh.
- Explore advanced Windows Firewall policies using Group Policy.

---

# 📚 References

- Microsoft Defender Firewall Documentation  
  https://learn.microsoft.com/windows/security/

- Ubuntu UFW Documentation  
  https://help.ubuntu.com/community/UFW

- NIST SP 800-41 Rev.1 — Guidelines on Firewalls and Firewall Policy

- CIS Controls v8

---

# 📄 License

This project is intended for educational and learning purposes.

You are free to use this repository for personal learning and cybersecurity practice.

---

# 👨‍💻 Author

**Abhiram Rapothula**

🎓 B.Tech – Computer Science & Engineering (Cybersecurity)

📍 Hyderabad, Telangana, India

### Connect with Me

- GitHub: https://github.com/abhiramyadav03
- LinkedIn: https://www.linkedin.com/in/rapothulaabhiram/
- TryHackMe: https://tryhackme.com/p/rapothula1907

---

<div align="center">

## ⭐ If you found this project helpful, consider giving it a Star!

**Happy Learning & Stay Secure! 🔐**

</div>
