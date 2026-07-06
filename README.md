README.md - Firewall Configuration Lab
# 🛡️ Windows & Linux Firewall Configuration Lab
### Configure • Test • Secure • Validate Firewall Rules

Badges:
Windows 10 | Ubuntu | Windows Defender Firewall | UFW | Status: Completed

Overview
This project demonstrates configuring and validating firewall rules on Windows Defender Firewall and Ubuntu UFW in a VMware-based lab. The objective is to strengthen host security by controlling inbound and outbound traffic and verifying firewall behavior.
Objectives
- Configure Windows Defender Firewall
- Configure UFW
- Block unnecessary ports
- Allow trusted services
- Test and validate firewall rules
- Understand host hardening
Lab Environment
Host OS: Windows 10
Linux: Ubuntu
Firewall: Windows Defender Firewall
Linux Firewall: UFW
Virtualization: VMware Workstation
Test Port: TCP 23 (Telnet)
Tools Used
Windows Defender Firewall
UFW
Command Prompt
Linux Terminal
Firewall Concepts
A firewall filters network traffic according to security rules. Inbound rules control incoming connections while outbound rules control outgoing traffic. Host firewalls reduce the attack surface and improve endpoint security.
Windows Firewall Configuration
Commands:
netsh advfirewall firewall add rule name="Block Telnet port 23" dir=in action=block protocol=TCP localport=23

netsh advfirewall firewall show rule name="Block Telnet port 23"

netsh advfirewall firewall delete rule name="Block Telnet port 23"

Explanation:
• Add a rule to block inbound Telnet.
• Verify the rule exists.
• Remove the rule after testing.
Linux UFW Configuration
Commands:
sudo ufw enable
sudo ufw status verbose
sudo ufw deny 23/tcp
sudo ufw allow ssh

Explanation:
• Enable UFW.
• Verify firewall status.
• Block Telnet.
• Allow SSH access.
Testing & Validation
Tested inbound Telnet after applying rules. Verified blocked traffic on TCP 23 while allowing required services such as SSH. Confirmed firewall status using Windows Defender Firewall and UFW commands.
Results
Windows firewall successfully blocked Telnet traffic.
UFW denied TCP 23.
Firewall status verified.
Host remained accessible through allowed services.
Security Benefits
Reduced attack surface.
Prevented unauthorized inbound access.
Improved endpoint security.
Demonstrated host hardening.
Skills Demonstrated
Windows Firewall
Linux UFW
Port Blocking
Host Hardening
Network Security
Command-Line Administration
Learning Outcomes
Configured Windows Defender Firewall.
Configured Ubuntu UFW.
Validated firewall rules.
Understood inbound/outbound filtering.
Improved practical firewall administration skills.
References
Microsoft Defender Firewall Documentation
Ubuntu UFW Documentation
NIST SP 800-41
CIS Controls
License
MIT License
Author
Abhiram Rapothula
GitHub: https://github.com/abhiramyadav03
LinkedIn: https://www.linkedin.com/in/rapothulaabhiram/
