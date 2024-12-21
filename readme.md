## 1. Project Overview
This project serves as a comprehensive recap of the concepts and practical skills learned in the first semester of the CCNA Introduction to Networks curriculum. The network topology includes two routers, switches, multiple VLANs, a Voice VLAN, router-on-a-stick configuration, subnetting, DHCP implementation, default routing, and relay agent configuration.

---

## 2. Network Topology Description
The network is divided into two main segments:
- **Router 1 Segment:** Connected to a switch with four VLANs, including a Voice VLAN, using a router-on-a-stick configuration.
- **Router 2 Segment:** Connected to three switches, each representing a subnet derived from the 172.16.1.X network.
- **Inter-Router Communication:** The two routers are interconnected using a subnet with only 4 available IPs for efficient IP address utilization.

---

## 3. Network Design and Implementation
### 3.1 Router 2 Configuration
- **VLAN Implementation:**
  - VLAN 10: Room 22
  - VLAN 20: Room 23
  - VLAN 30: Room 24
  - VLAN 40: Voice
- **Router-on-a-Stick Configuration:**
  - Sub-interfaces were configured on Router 2 to enable inter-VLAN communication.
  - Each sub-interface was assigned an IP address within its respective VLAN.
- **Switch Configuration:**
  - VLANs were created and assigned to specific switch ports.
  - VLAN Trunking Protocol (VTP) was configured where applicable.
- **IP Assignment:**
  - Static IP addresses were assigned to each VLAN interface on Router 2.
- **Voice VLAN:**
  - A dedicated VLAN for VoIP communication was created to prioritize voice traffic.

### 3.2 Router 1 Configuration
- **Subnetting:**
  - The 172.16.1.X network was subnetted into 4 subnets.
  - Each subnet has a specific range and is assigned to:
    - Switch 1-1: Subnet 1
    - Switch 2-1: Subnet 2
    - Switch 3-1: Subnet 3
- **DHCP Server:**
  - A DHCP server is connected to Subnet 1.
  - It is configured to distribute IP addresses to devices in Subnet 1, Subnet 2, and Subnet 3.
- **Relay Agent Configuration:**
  - Router 1 acts as a DHCP relay agent for Subnet 2 and Subnet 3, forwarding DHCP requests to the DHCP server.

### 3.3 Inter-Router Communication
- **Subnetting:**
  - A small subnet with 4 available IP addresses was created for the connection between the two routers.
  - This ensures efficient utilization of IP addresses.
- **Routing:**
  - Default routing was implemented between the two routers to ensure seamless communication between all subnets.

---

## 4. IP Addressing Scheme
| Subnet   | Network ID   | First IP / Gateway | Last IP       | Broadcast    | Subnet Mask       |
|----------|--------------|--------------------|---------------|--------------|-------------------|
| Subnet 1 | 172.16.1.0   | 172.16.1.1         | 172.16.1.62   | 172.16.1.63  | 255.255.255.192   |
| Subnet 2 | 172.16.1.64  | 172.16.1.65        | 172.16.1.126  | 172.16.1.127 | 255.255.255.192   |
| Subnet 3 | 172.16.1.128 | 172.16.1.129       | 172.16.1.190  | 172.16.1.191 | 255.255.255.192   |
| Subnet 4 | 172.16.1.192 | 172.16.1.193       | 172.16.1.254  | 172.16.1.255 | 255.255.255.192   |

| VLAN ID | VLAN Name  | Purpose             | Network ID     | Prefix |
|---------|------------|---------------------|----------------|--------|
| 10      | Room 22    | Data traffic        | 192.168.10.0   | /24    |
| 20      | Room 23    | Data traffic        | 192.168.20.0   | /24    |
| 30      | Room 24    | Data traffic        | 192.168.30.0   | /24    |
| 40      | Voice      | Voice communication | 192.168.40.0   | /24    |

---

## 6. DHCP Configuration
- **DHCP Server:**
  - DHCP pools were created to distribute IP addresses for Subnet 1, Subnet 2, and Subnet 3.
- **DHCP Relay Agent:**
  - Router 2 was configured to forward DHCP requests for Subnet 2 and Subnet 3 to the DHCP server on Subnet 1.

---

## 7. Routing Configuration
- **Default Routing:**
  - Default routes were configured on both routers to enable communication between all subnets.

---

## 8. Summary
This project demonstrates the implementation of VLANs, router-on-a-stick, DHCP, subnetting, and inter-router communication using default routing. Key highlights include:
- Efficient IP address utilization through subnetting.
- Configuration of VLANs, including a dedicated Voice VLAN.
- Router-on-a-stick implementation to enable inter-VLAN communication.
- DHCP server setup with relay agent configuration to serve multiple subnets.
- Default routing to connect all devices across the two routers.

The project reinforces foundational networking concepts and provides hands-on experience in designing and configuring a functional network topology.

---

## 9. Conclusion
This project served as an excellent recap of the first semester of the CCNA curriculum, applying theoretical knowledge to practical networking scenarios. It highlights the importance of proper network design, VLAN management, router-on-a-stick, IP addressing, and routing protocols in building scalable and efficient networks.
