# CCNA Router-on-a-Stick | Inter-VLAN Routing

## Project Overview

This project demonstrates how to configure Inter-VLAN Routing using the Router-on-a-Stick (ROAS) method in Cisco Packet Tracer.

The topology separates HR and IT devices into different VLANs while allowing communication between the two networks through a single physical router interface configured with multiple subinterfaces.

## Objectives

- Create and configure VLANs.
- Assign switch access ports to the appropriate VLANs.
- Configure a trunk link between the switch and router.
- Configure router subinterfaces using 802.1Q encapsulation.
- Assign IP addresses and default gateways.
- Test connectivity within and between VLANs.
- Troubleshoot connectivity issues using Cisco IOS commands.

## Network Topology

The network consists of:

- 1 Cisco 2960 switch
- 1 Cisco router
- 4 end devices (PCs)
- 2 VLANs

### VLAN and IP Addressing Plan

| VLAN | Department | Network | Default Gateway |
|---|---|---|---|
| VLAN 10 | HR | 192.168.10.0/24 | 192.168.10.1 |
| VLAN 20 | IT | 192.168.20.0/24 | 192.168.20.1 |

### IP Address Assignment

| Device | VLAN | IP Address | Default Gateway |
|---|---|---|---|
| PC0 | 10 | 192.168.10.2/24 | 192.168.10.1 |
| PC1 | 10 | 192.168.10.3/24 | 192.168.10.1 |
| PC2 | 20 | 192.168.20.2/24 | 192.168.20.1 |
| PC3 | 20 | 192.168.20.3/24 | 192.168.20.1 |

## Technologies and Concepts

- Cisco Packet Tracer
- VLAN Configuration
- Access Ports and Trunking
- IEEE 802.1Q Encapsulation
- Router Subinterfaces
- Inter-VLAN Routing
- IPv4 Addressing and Subnetting
- ICMP and Ping Testing
- Network Troubleshooting

## Configuration Workflow

1. Create VLAN 10 and VLAN 20 on the switch.
2. Assign the PC-facing switch ports to their respective VLANs.
3. Configure the switch port connected to the router as a trunk.
4. Configure router subinterfaces for VLAN 10 and VLAN 20.
5. Configure IP addresses on all PCs.
6. Set the appropriate default gateway on each PC.
7. Verify VLAN membership, trunk status, interface status, and connectivity.

## Verification Commands

### Switch

```text
show vlan brief
show interfaces trunk
show interfaces status
```

### Router

```text
show ip interface brief
show running-config
show ip route
```

### Connectivity Testing

Use `ping` to verify:

- Communication between PCs in the same VLAN.
- Communication between PCs in different VLANs.
- Reachability of each VLAN's default gateway.

## Expected Results

- PCs in VLAN 10 communicate with their configured gateway.
- PCs in VLAN 20 communicate with their configured gateway.
- Devices in different VLANs communicate through the router when the configuration is correct.
- VLAN separation is maintained at Layer 2, while the router provides Layer 3 connectivity.

