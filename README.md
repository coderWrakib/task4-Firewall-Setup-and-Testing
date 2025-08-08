# task4-Firewall-Setup-and-Testing
# Cyber Security Internship Task 4: Firewall Setup and Testing

## Objective
Configure firewall rules to block Telnet (port 23) and allow SSH (port 22), test these rules, and restore the firewall to its original state. This task is performed on both Windows (using GUI) and Linux (using UFW).

---

## Windows Firewall Configuration (Using GUI)

### Steps Performed:

1. Opened **Windows Defender Firewall with Advanced Security** (`wf.msc`).
2. Viewed current inbound rules.  
3. Created a new inbound rule to **block TCP port 23 (Telnet)**.  
4. Tested Telnet connection to localhost on port 23 using Command Prompt. The connection failed, confirming the block.  
5. Created a new inbound rule to **allow TCP port 22 (SSH)** (optional if SSH server is present).  
6. Removed the block rule on port 23 to restore the original state.  

---

## Linux Firewall Configuration (Using UFW)

### Commands and Output:

1. Checked initial UFW status and rules:  
   
   sudo ufw status verbose

Enabled UFW firewall (if it was not enabled):


sudo ufw enable

Blocked inbound traffic on port 23 (Telnet):


sudo ufw deny 23/tcp

Tested Telnet connection to port 23 (expected to fail):


telnet <linux_machine_ip> 23

Allowed inbound SSH port 22:


sudo ufw allow 22/tcp

Removed the block rule on port 23 to restore original state:


sudo ufw delete deny 23/tcp

Verified final UFW status showing all rules:


sudo ufw status verbose

Summary and Conclusion
Successfully added firewall rules on Windows via GUI and on Linux using UFW.

Tested blocking of Telnet (port 23) which failed as expected.

Allowed SSH (port 22) connections successfully.

Removed block rules to restore original firewall configuration.

Gained practical experience in managing firewall rules and understanding network traffic filtering.

