# Telnet Remote Access Project (Cisco Packet Tracer)

## 📌 Project Overview
This project demonstrates how to configure Telnet for remote access to a router using Cisco Packet Tracer. Telnet allows a user to remotely access and manage a network device through the command line over a network.

---

## 🧱 Network Design
- 1 Router
- 1 PC
- Direct connection between PC and Router

### 📡 Connection
- PC (FastEthernet0) → Router (GigabitEthernet0/0)

---

## ⚙️ Configuration Steps

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

### 🔹 Router Configuration
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

### 🔹 Verification Command

- Check Connectivity (from PC)
```bash
ping 192.168.1.1
```

- Access Router using Telnet (from PC)
```bash
telnet 192.168.1.1
```

Enter Privileged Mode
```bash
enable
```
## 📸 Network Topology
![Topology](images/topology.png)

---
## ✅ Testing & Verification
- Verified connectivity using ping  
- Successfully accessed router from PC using Telnet  
- Entered privileged mode using enable password  
- Confirmed remote access functionality  

---

## 🧠 Skills Learned
- Remote access using Telnet  
- Router interface configuration  
- VTY line configuration  
- Password-based authentication  
- Network connectivity troubleshooting  

---

## 📌 Important Note
Telnet sends data in plain text, making it insecure.  
In real-world networks, SSH (Secure Shell) is preferred for secure remote access.  

---

## 📂 Project File
- telnet-project.pkt
- images/topology.png

---

## 📌 Conclusion
This project demonstrates how to configure and use Telnet for remote access to a router. It provided practical understanding of remote device management and basic network security considerations.



