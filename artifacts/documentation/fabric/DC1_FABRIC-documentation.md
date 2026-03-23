# DC1_FABRIC

## Table of Contents

- [Fabric Switches and Management IP](#fabric-switches-and-management-ip)
  - [Fabric Switches with inband Management IP](#fabric-switches-with-inband-management-ip)
- [Fabric Topology](#fabric-topology)
- [Fabric IP Allocation](#fabric-ip-allocation)
  - [Fabric Point-To-Point Links](#fabric-point-to-point-links)
  - [Point-To-Point Links Node Allocation](#point-to-point-links-node-allocation)
  - [Loopback Interfaces (BGP EVPN Peering)](#loopback-interfaces-bgp-evpn-peering)
  - [Loopback0 Interfaces Node Allocation](#loopback0-interfaces-node-allocation)
  - [VTEP Loopback VXLAN Tunnel Source Interfaces (VTEPs Only)](#vtep-loopback-vxlan-tunnel-source-interfaces-vteps-only)
  - [VTEP Loopback Node allocation](#vtep-loopback-node-allocation)

## Fabric Switches and Management IP

| POD | Type | Node | Management IP | Platform | Provisioned in CloudVision | Serial Number |
| --- | ---- | ---- | ------------- | -------- | -------------------------- | ------------- |
| DC1_FABRIC | l3leaf | dc1-leaf1a | 192.168.0.103/24 | vEOS-LAB | Provisioned | - |
| DC1_FABRIC | l3leaf | dc1-leaf1b | 192.168.0.104/24 | vEOS-LAB | Provisioned | - |
| DC1_FABRIC | l3leaf | dc1-leaf2a | 192.168.0.105/24 | vEOS-LAB | Provisioned | - |
| DC1_FABRIC | l3leaf | dc1-leaf2b | 192.168.0.106/24 | vEOS-LAB | Provisioned | - |
| DC1_FABRIC | l3leaf | dc1-leaf3a | 192.168.0.107/24 | vEOS-LAB | Provisioned | - |
| DC1_FABRIC | l3leaf | dc1-leaf3b | 192.168.0.108/24 | vEOS-LAB | Provisioned | - |
| DC1_FABRIC | spine | dc1-spine1 | 192.168.0.101/24 | vEOS-LAB | Provisioned | - |
| DC1_FABRIC | spine | dc1-spine2 | 192.168.0.102/24 | vEOS-LAB | Provisioned | - |

> Provision status is based on Ansible inventory declaration and do not represent real status from CloudVision.

### Fabric Switches with inband Management IP

| POD | Type | Node | Management IP | Inband Interface |
| --- | ---- | ---- | ------------- | ---------------- |

## Fabric Topology

| Type | Node | Node Interface | Peer Type | Peer Node | Peer Interface |
| ---- | ---- | -------------- | --------- | ----------| -------------- |
| l3leaf | dc1-leaf1a | Ethernet1 | spine | dc1-spine1 | Ethernet1 |
| l3leaf | dc1-leaf1a | Ethernet2 | spine | dc1-spine2 | Ethernet1 |
| l3leaf | dc1-leaf1a | Ethernet3 | mlag_peer | dc1-leaf1b | Ethernet3 |
| l3leaf | dc1-leaf1b | Ethernet1 | spine | dc1-spine1 | Ethernet2 |
| l3leaf | dc1-leaf1b | Ethernet2 | spine | dc1-spine2 | Ethernet2 |
| l3leaf | dc1-leaf2a | Ethernet1 | spine | dc1-spine1 | Ethernet3 |
| l3leaf | dc1-leaf2a | Ethernet2 | spine | dc1-spine2 | Ethernet3 |
| l3leaf | dc1-leaf2a | Ethernet3 | mlag_peer | dc1-leaf2b | Ethernet3 |
| l3leaf | dc1-leaf2b | Ethernet1 | spine | dc1-spine1 | Ethernet4 |
| l3leaf | dc1-leaf2b | Ethernet2 | spine | dc1-spine2 | Ethernet4 |
| l3leaf | dc1-leaf3a | Ethernet1 | spine | dc1-spine1 | Ethernet5 |
| l3leaf | dc1-leaf3a | Ethernet2 | spine | dc1-spine2 | Ethernet5 |
| l3leaf | dc1-leaf3a | Ethernet3 | mlag_peer | dc1-leaf3b | Ethernet3 |
| l3leaf | dc1-leaf3b | Ethernet1 | spine | dc1-spine1 | Ethernet6 |
| l3leaf | dc1-leaf3b | Ethernet2 | spine | dc1-spine2 | Ethernet6 |

## Fabric IP Allocation

### Fabric Point-To-Point Links

| Uplink IPv4 Pool | Available Addresses | Assigned addresses | Assigned Address % |
| ---------------- | ------------------- | ------------------ | ------------------ |
| 1.1.255.0/27 | 32 | 24 | 75.0 % |

### Point-To-Point Links Node Allocation

| Node | Node Interface | Node IP Address | Peer Node | Peer Interface | Peer IP Address |
| ---- | -------------- | --------------- | --------- | -------------- | --------------- |
| dc1-leaf1a | Ethernet1 | 1.1.255.1/31 | dc1-spine1 | Ethernet1 | 1.1.255.0/31 |
| dc1-leaf1a | Ethernet2 | 1.1.255.3/31 | dc1-spine2 | Ethernet1 | 1.1.255.2/31 |
| dc1-leaf1b | Ethernet1 | 1.1.255.5/31 | dc1-spine1 | Ethernet2 | 1.1.255.4/31 |
| dc1-leaf1b | Ethernet2 | 1.1.255.7/31 | dc1-spine2 | Ethernet2 | 1.1.255.6/31 |
| dc1-leaf2a | Ethernet1 | 1.1.255.9/31 | dc1-spine1 | Ethernet3 | 1.1.255.8/31 |
| dc1-leaf2a | Ethernet2 | 1.1.255.11/31 | dc1-spine2 | Ethernet3 | 1.1.255.10/31 |
| dc1-leaf2b | Ethernet1 | 1.1.255.13/31 | dc1-spine1 | Ethernet4 | 1.1.255.12/31 |
| dc1-leaf2b | Ethernet2 | 1.1.255.15/31 | dc1-spine2 | Ethernet4 | 1.1.255.14/31 |
| dc1-leaf3a | Ethernet1 | 1.1.255.17/31 | dc1-spine1 | Ethernet5 | 1.1.255.16/31 |
| dc1-leaf3a | Ethernet2 | 1.1.255.19/31 | dc1-spine2 | Ethernet5 | 1.1.255.18/31 |
| dc1-leaf3b | Ethernet1 | 1.1.255.21/31 | dc1-spine1 | Ethernet6 | 1.1.255.20/31 |
| dc1-leaf3b | Ethernet2 | 1.1.255.23/31 | dc1-spine2 | Ethernet6 | 1.1.255.22/31 |

### Loopback Interfaces (BGP EVPN Peering)

| Loopback Pool | Available Addresses | Assigned addresses | Assigned Address % |
| ------------- | ------------------- | ------------------ | ------------------ |
| 1.1.0.0/27 | 32 | 8 | 25.0 % |

### Loopback0 Interfaces Node Allocation

| POD | Node | Loopback0 |
| --- | ---- | --------- |
| DC1_FABRIC | dc1-leaf1a | 1.1.0.3/32 |
| DC1_FABRIC | dc1-leaf1b | 1.1.0.4/32 |
| DC1_FABRIC | dc1-leaf2a | 1.1.0.5/32 |
| DC1_FABRIC | dc1-leaf2b | 1.1.0.6/32 |
| DC1_FABRIC | dc1-leaf3a | 1.1.0.7/32 |
| DC1_FABRIC | dc1-leaf3b | 1.1.0.8/32 |
| DC1_FABRIC | dc1-spine1 | 1.1.0.1/32 |
| DC1_FABRIC | dc1-spine2 | 1.1.0.2/32 |

### VTEP Loopback VXLAN Tunnel Source Interfaces (VTEPs Only)

| VTEP Loopback Pool | Available Addresses | Assigned addresses | Assigned Address % |
| ------------------ | ------------------- | ------------------ | ------------------ |
| 1.1.1.0/27 | 32 | 6 | 18.75 % |

### VTEP Loopback Node allocation

| POD | Node | Loopback1 |
| --- | ---- | --------- |
| DC1_FABRIC | dc1-leaf1a | 1.1.1.3/32 |
| DC1_FABRIC | dc1-leaf1b | 1.1.1.3/32 |
| DC1_FABRIC | dc1-leaf2a | 1.1.1.5/32 |
| DC1_FABRIC | dc1-leaf2b | 1.1.1.5/32 |
| DC1_FABRIC | dc1-leaf3a | 1.1.1.7/32 |
| DC1_FABRIC | dc1-leaf3b | 1.1.1.7/32 |
