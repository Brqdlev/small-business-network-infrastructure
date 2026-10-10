# Small Business Network Infrastructure

## Project Overview

This project documents the design, implementation, security, and ongoing improvement of a small business network infrastructure.

The goal is to build a reliable, segmented, manageable, and secure network while applying practical networking and systems administration concepts in a real-world environment.

## Objectives

- Design and implement a structured network topology.
- Configure VLANs, IP addressing, DHCP, and inter-VLAN routing.
- Apply firewall policies to control communication between network segments.
- Implement per-device bandwidth limits.
- Secure network devices and restrict access to unused physical ports.
- Deploy centralized storage and Linux services using Proxmox VE and Ubuntu Server.
- Build network monitoring and troubleshooting capabilities.
- Document configuration decisions, testing results, and lessons learned.

## Technologies

- **Routing and firewall:** MikroTik RouterOS
- **Switching:** TP-Link TL-SG1016DE Easy Smart Switch
- **Wireless:** TP-Link access points
- **Virtualization:** Proxmox VE
- **Server OS:** Ubuntu Server
- **Storage services**: Samba
- **Monitoring:** Prometheus and Grafana
- **Troubleshooting:** Ping, WinBox/WebFig, and Wireshark
- **Documentation and version control:** Markdown, Git, GitHub, and Visual Studio Code

## Network Segmentation

| VLAN | Purpose    | Subnet              |
|------|------------|---------------------|
| 10   | HOME       | `192.168.10.0/26`   |
| 20   | SHOP       | `192.168.10.64/27`  |
| 30   | SERVER     | `192.168.10.96/28`  |
| 40   | MANAGEMENT | `192.168.10.112/28` |

## Implementation Progress

- [x] Design IP addressing and VLAN plan
- [x] Configure MikroTik VLAN interfaces and gateways
- [x] Configure managed-switch VLAN membership and access ports
- [x] Configure DHCP for the planned VLANs
- [x] Test HOME and SHOP connectivity
- [x] Verify per-PC bandwidth limits for shop clients
- [x] Test HOME-to-SHOP and SHOP-to-HOME firewall isolation
- [x] Disable selected unused router and switch ports
- [ ] Complete final firewall and management-access verification
- [ ] Verify production WAN configuration
- [ ] Complete centralized storage deployment and client testing
- [ ] Deploy Prometheus and Grafana monitoring
- [ ] Finalize topology diagrams and technical documentation

## Documentation Structure

Technical documentation, network diagrams, configuration notes, testing evidence, and lessons learned will be added as the project progresses.

## Security Notice

Sensitive information such as passwords, private keys, customer data, and unredacted device configurations will not be published in this repository.