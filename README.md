# CCNA Packet Tracer Lab: Basic Router Connectivity

## Overview
This project demonstrates the configuration of a basic routed network using Cisco Packet Tracer. The goal was to connect two separate IPv4 networks using a single router and verify end-to-end connectivity between hosts.

This lab was completed as part of my CCNA certification journey to build foundational networking and Cisco IOS configuration skills.

---

## Network Objective
- Configure IPv4 addressing on router interfaces
- Assign IP addresses and default gateways to end devices
- Enable router interfaces using Cisco IOS (`no shutdown`)
- Establish communication between two different networks
- Validate connectivity using ICMP ping tests

---

## Topology

PC1 -------- Router -------- PC2
        G0/0        G0/1

---

## IP Addressing Scheme

| Device | Interface | IP Address | Subnet Mask |
|--------|-----------|------------|--------------|
| PC1 | NIC | 192.168.1.10 | 255.255.255.0 |
| Router | G0/0 | 192.168.1.1 | 255.255.255.0 |
| Router | G0/1 | 192.168.2.1 | 255.255.255.0 |
| PC2 | NIC | 192.168.2.10 | 255.255.255.0 |

---

## Router Configuration

```bash
enable
configure terminal

interface g0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit

interface g0/1
ip address 192.168.2.1 255.255.255.0
no shutdown
exit

end
copy running-config startup-config
