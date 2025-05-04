Corporate Network Design - Head Office & Branch Integration

This project documents a sample enterprise network topology involving VLAN segmentation, inter-VLAN routing, DHCP relay, and OSPF-based branch connectivity. 

Head Office Network

- **Switch Configuration:**
  - VLAN 10 – IT
  - VLAN 20 – HR
  - VLAN 30 – Management
  - VLAN 40 – Sales

- **DHCP Server:**
  - Located in VLAN 10 (IT Department)
  - Serves IP addresses to all VLANs via DHCP relay on the router

- **Router:**
  - Performs Inter-VLAN Routing
  - Connected to:
    - ISP for Internet access (NAT enabled)
    - Branch office router via OSPF

Branch Office Network

- **Router:**
  - Connected to main router via OSPF
  - Accesses the internet through the main office router (NAT occurs at the main site)
  - Receives DHCP leases from the IT VLAN in the head office (relay through inter-site link)

Access Control

- All internal PCs can communicate across VLANs **except**:
  - **Access to the IT VLAN is restricted** from other VLANs and branch office

Routing

- **OSPF** is used for dynamic routing between the main and branch routers
- **NAT** is configured on the head office router for internet access

---

This setup can be emulated in Cisco Packet Tracer, GNS3, or real equipment. Useful for labs, learning inter-VLAN routing, OSPF, and DHCP relay configurations.
