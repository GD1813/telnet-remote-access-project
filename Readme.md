# Telnet Remote Access Project (Cisco Packet Tracer)

## 📌 Project Overview
This project demonstrates how to configure **remote access to a router** using Cisco Packet Tracer, starting with Telnet (insecure) and upgrading to SSH (secure).

The project highlights the transition from **plain text communication (Telnet)** to **encrypted communication (SSH)**, reflecting real-world networking practices.

---

## 🧱 Network Design
- 1 Router
- 1 PC
- Direct connection between PC and Router

### 📡 Connection
- PC (FastEthernet0) → Router (GigabitEthernet0/0)

---

## ⚙️ Telnet Configuration(Initial)

### 1. Router Interface Configuration
- Assigned IP address to router interface
- Enabled the interface using `no shutdown`

### 2. Telnet Configuration (VTY Lines)
- Configured password for remote login
- Enabled login on VTY lines

### 3. Enable Password Configuration
- Configured enable password for privileged access

### 4. PC Configuration
- Assigned IP address in the same network as router
- Configured default gateway

### 5. Remote Access using Telnet
- Accessed router from PC using Telnet command

## ⚙️ SSH Configuration (Upgrade)

### 1. Router Interface Configuration
- Assigned IP address to router interface  
- Enabled the interface using `no shutdown`  

### 2. Basic SSH Requirements
- Configured hostname  
- Configured domain name  
- Created local user credentials  

### 3. SSH Configuration
- Generated RSA keys for encryption  
- Enabled SSH version 2  
- Configured VTY lines for SSH access only  

### 4. PC Configuration
- Assigned IP address in the same network  
- Configured default gateway  

### 5. Remote Access using SSH
- Accessed router securely from PC using SSH command  


---

## 🖥️ IP Addressing

### Router
- Interface: g0/0  
- IP Address: 192.168.1.1  
- Subnet Mask: 255.255.255.0  

### PC
- IP Address: 192.168.1.2  
- Subnet Mask: 255.255.255.0  
- Default Gateway: 192.168.1.1  

---

## 💻 CLI Configuration

### 🔹 Telnet Configuration (Initial)
```bash
enable
configure terminal

interface g0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit

line vty 0 4
password cisco
login
exit

enable password cisco

end
write memory
```
### 🔹 SSH Configuration (Upgrade)
```bash
enable
configure terminal

hostname R1
ip domain-name lab.local

interface g0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit

username admin password cisco

crypto key generate rsa
1024

ip ssh version 2

line vty 0 4
login local
transport input ssh
exit

end
write memory
```
### 🔹 Verification Command

- Check Connectivity (from PC)
```bash
ping 192.168.1.1
```

- Access Router using Telnet (from PC - Initial)
```bash
telnet 192.168.1.1
```
- Access Router using SSH (from PC - Upgraded)
```bash
ssh -l admin 192.168.1.1
```
- Verify SSH
```bash
enable
show ip ssh
```

## 📸 Network Topology
![Topology](Image/Topology.png)

---
## ✅ Testing & Verification
- Successfully accessed router using Telnet (initial phase)
- Successfully accessed router using SSH (upgrade phase)
- Verified connectivity using ping
- Verified secure login using username and password
- Confirmed Telnet access is disabled after SSH configuration
- Verified SSH configuration using CLI commands

---

## 🧠 Skills Learned
- Remote access using Telnet
- Secure remote access using SSH
- Difference between Telnet and SSH
- RSA key generation for encryption
- VTY line configuration for remote access
- Authentication using username and password
- Disabled Telnet access for improved security
- Network troubleshooting
---

## 🔄 Project Evolution
- Version 1: Telnet Remote Access (Insecure)
- Version 2: Upgraded to SSH (Secure Remote Access)

---

## 📂 Project File
- telnet-project.pkt
- ssh-remote-access-project.pkt
- Image/Topology.png

---

## 📌 Conclusion
This project demonstrates the transition from Telnet to SSH for remote access. It highlights the importance of encryption and secure authentication in modern networking, providing practical experience in configuring both insecure and secure remote management methods.



