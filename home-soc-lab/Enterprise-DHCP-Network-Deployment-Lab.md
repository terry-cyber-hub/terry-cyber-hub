# Enterprise DHCP Network Deployment Lab

## Project Overview

This project demonstrates the configuration of a Cisco router as a **DHCP server** to automatically assign IP addresses to computers connected to a network.

The goal of this lab was to simulate a small business network where users can connect their devices and automatically receive the necessary network settings, including:

- IP Address
- Subnet Mask
- Default Gateway
- DNS Server

This project was built using **Cisco Packet Tracer** and demonstrates foundational networking skills used in IT Support and Network Administration roles.

---

## Skills Demonstrated

- Cisco IOS command-line configuration
- DHCP server deployment
- IPv4 addressing
- Network topology design
- Router and switch configuration
- Basic network troubleshooting

---

# Network Topology

             Cisco 2911 Router
          (DHCP Server/Gateway)
                   |
             GigabitEthernet 0/0
                   |
             Cisco 2960 Switch
          _________|_________
         |         |         |
        PC1       PC2       PC3
    DHCP Client DHCP Client DHCP Client


  **Screenshots**  
  <img width="960" height="540" alt="Screenshot 2026-07-20 165217" src="https://github.com/user-attachments/assets/1b09bab4-069e-4896-ad27-1782532a11c1" />


Figure 1: This is the network topology that shows the logical structure of this network

  <img width="878" height="451" alt="Screenshot 2026-07-20 165559" src="https://github.com/user-attachments/assets/2d382315-82ae-4b57-a71e-709e933773d1" />


Figure 2: All PCs were able to receive ip addresses from the DHCP server successfully within the scope
