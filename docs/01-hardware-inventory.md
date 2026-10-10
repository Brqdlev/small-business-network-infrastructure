# 01 — Hardware Inventory

## 1. Purpose

This document records the physical computing and network devices used in the small business network infrastructure project. It provides a baseline for network design, configuration, troubleshooting, capacity planning, and future upgrades.

## 2. Shop Client PCs

| Device | CPU | Memory | Storage | Storage Type |
|---|---|---:|---:|---|
| PC 1 | AMD Ryzen 3 3200G | 16 GB DDR4 | 256 GB | NVMe SSD |
| PC 2 | Intel Core i7, 8th generation | 16 GB DDR4 | 256 GB | NVMe SSD |
| PC 3 | AMD Ryzen 3 2200G | 16 GB DDR4 | 240 GB | SATA SSD |
| PC 4 | AMD Ryzen 3 3200G | 16 GB DDR4 | 240 GB | SATA SSD |
| PC 5 | AMD Ryzen 3 2200G | 16 GB DDR4 | 240 GB | SATA SSD |
| PC 6 | AMD Ryzen 3 PRO 2100GE | 16 GB DDR4 | 240 GB | SATA SSD |

**Client environment**
- Number of shop client PCs: 6
- Operating system: Windows 10 (as currently reported)
- Network segment: VLAN 20 — SHOP
- Bandwidth policy: per-PC Simple Queues configured for 20 Mbps download and 10 Mbps upload

## 3. Virtualization and Storage Server

| Item | Specification |
|---|---|
| Model | Dell OptiPlex 7060 |
| CPU | Intel Core i7, 8th generation |
| Memory | 32 GB DDR4, dual-channel |
| OS / VM storage | 240 GB SATA SSD |
| Additional storage | 512 GB NVMe SSD |
| Hypervisor | Proxmox VE 9.2.2 |
| Virtual machine | Ubuntu Server VM, ID 100, named `ubuntu-samba` |
| Server network | VLAN 30 — SERVER |
| Proxmox management address | `192.168.10.98/28` |
| Ubuntu/Samba VM address | `192.168.10.99` |

**Purpose**
- Host virtual machines using Proxmox VE.
- Provide a Linux-based server environment for centralized storage and file-sharing services.
- Support future infrastructure services and monitoring experiments.

*Storage-role note: the 512 GB NVMe is intended for game-storage data. Confirm the final mount and storage layout before treating this inventory as a record of the current live configuration.*

## 4. Network Infrastructure

| Device | Model | Role | Notes |
|---|---|---|---|
| Router | MikroTik hEX Refresh E50UG | Main router and firewall | RouterOS; provides VLAN gateways, DHCP, routing, firewall policy, and per-client bandwidth limits |
| Managed switch | TP-Link TL-SG1016DE | LAN switching | 16-port Easy Smart Gigabit switch; used for VLAN membership and physical-port management |
| Wireless access point | TP-Link Archer C64 | Wi-Fi access | Used to connect wireless home devices to the HOME network; confirm its final AP configuration and switch-port assignment |

## 5. Network Segmentation Reference

| VLAN | Name | Subnet | Gateway |
|---:|---|---|---|
| 10 | HOME | `192.168.10.0/26` | `192.168.10.1` |
| 20 | SHOP | `192.168.10.64/27` | `192.168.10.65` |
| 30 | SERVER | `192.168.10.96/28` | `192.168.10.97` |
| 40 | MANAGEMENT | `192.168.10.112/28` | `192.168.10.113` |

This table is a reference to the current network plan. Verify addresses and configuration against the live devices before making operational changes.



