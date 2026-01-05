# networkplus-labs
Private lab: TCP handshake, ARP resolution, netcat communication on Ubuntu Server and more...
# TCP Handshake & ARP Resolution Lab

## Project Overview
This lab demonstrates the fundamentals of TCP communication and ARP resolution in a private network environment. Using two Ubuntu Server virtual machines, we capture and analyze raw network traffic to understand how devices establish connections and resolve MAC addresses in a subnet.

**Key Objectives:**
- Observe the TCP three-way handshake (SYN, SYN-ACK, ACK)
- Capture and analyze ARP request and reply packets
- Understand local network communication without a gateway
- Apply practical concepts from CompTIA Network+ certification
- Use Wireshark for detailed packet inspection and visualization

---

## Lab Environment

| Component | Details |
|-----------|--------|
| VM1 (Client) | Ubuntu Server, IP: `192.168.10.10` |
| VM2 (Server) | Ubuntu Server, IP: `192.168.10.20` |
| Network | Private network `lab-net`, Subnet: `192.168.10.0/24` |
| Connectivity | VM1 ↔ VM2 (isolated, no Internet access) |

**Topology Diagram:**  
*(Add an image in `topology/network-diagram.png` if available)*

---

## Tools Used
- `netcat` for establishing TCP connections  
- `tcpdump` for packet capture  
- **Wireshark** for packet analysis and visualization  
- `ip` and `arp` for network configuration and inspection  

---

## Lab Procedure
1. Set up a private network (`lab-net`) connecting two VMs.
2. Assign static IP addresses:
   - Client: `192.168.10.10`
   - Server: `192.168.10.20`
3. Use `netcat` to establish a TCP connection from client to server:
   ```bash
   nc 192.168.10.20 12345
