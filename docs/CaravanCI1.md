# CaravanCI1

- [CaravanCI1](#caravanci1)
- [Management](#management)
  - [Management Interfaces](#management-interfaces)
    - [Management Interfaces Summary](#management-interfaces-summary)
      - [IPv4](#ipv4)
      - [IPv6](#ipv6)
  - [DNS Domain](#dns-domain)
    - [DNS domain: atd.lab](#dns-domain-atdlab)
    - [DNS Domain Device Configuration](#dns-domain-device-configuration)
  - [Name Servers](#name-servers)
    - [Name Servers Summary](#name-servers-summary)
    - [Name Servers Device Configuration](#name-servers-device-configuration)
  - [Management API HTTP](#management-api-http)
    - [Management API HTTP Summary](#management-api-http-summary)
    - [Management API VRF Access](#management-api-vrf-access)
    - [Management API HTTP Configuration](#management-api-http-configuration)
- [Authentication](#authentication)
- [Monitoring](#monitoring)
- [Spanning Tree](#spanning-tree)
  - [Spanning Tree Summary](#spanning-tree-summary)
    - [MSTP Instance and Priority](#mstp-instance-and-priority)
  - [Spanning Tree Device Configuration](#spanning-tree-device-configuration)
- [Internal VLAN Allocation Policy](#internal-vlan-allocation-policy)
  - [Internal VLAN Allocation Policy Summary](#internal-vlan-allocation-policy-summary)
  - [Internal VLAN Allocation Policy Configuration](#internal-vlan-allocation-policy-configuration)
- [Interfaces](#interfaces)
  - [Ethernet Interfaces](#ethernet-interfaces)
    - [Ethernet Interfaces Summary](#ethernet-interfaces-summary)
      - [L2](#l2)
      - [IPv4](#ipv4-1)
    - [Ethernet Interfaces Device Configuration](#ethernet-interfaces-device-configuration)
  - [VXLAN Interface](#vxlan-interface)
    - [VXLAN Interface Summary](#vxlan-interface-summary)
      - [VLAN to VNI, Flood List and Multicast Group Mappings](#vlan-to-vni-flood-list-and-multicast-group-mappings)
      - [VRF to VNI and Multicast Group Mappings](#vrf-to-vni-and-multicast-group-mappings)
    - [VXLAN Interface Device Configuration](#vxlan-interface-device-configuration)
- [Routing](#routing)
  - [Service Routing Protocols Model](#service-routing-protocols-model)
  - [Virtual Router MAC Address](#virtual-router-mac-address)
    - [Virtual Router MAC Address Summary](#virtual-router-mac-address-summary)
      - [Virtual Router MAC Address: 00:1c:73:00:dc:01](#virtual-router-mac-address-001c7300dc01)
    - [Virtual Router MAC Address Configuration](#virtual-router-mac-address-configuration)
  - [IP Routing](#ip-routing)
    - [IP Routing Summary](#ip-routing-summary)
    - [IP Routing Device Configuration](#ip-routing-device-configuration)
  - [IPv6 Routing](#ipv6-routing)
    - [IPv6 Routing Summary](#ipv6-routing-summary)
  - [Static Routes](#static-routes)
    - [Static Routes Summary](#static-routes-summary)
    - [Static Routes Device Configuration](#static-routes-device-configuration)
  - [Router BGP](#router-bgp)
    - [Router BGP Summary](#router-bgp-summary)
    - [Router BGP Peer Groups](#router-bgp-peer-groups)
      - [EVPN-OVERLAY-PEERS](#evpn-overlay-peers)
    - [BGP Neighbors](#bgp-neighbors)
    - [Router BGP EVPN Address Family](#router-bgp-evpn-address-family)
      - [EVPN Peer Groups](#evpn-peer-groups)
    - [Router BGP VLAN Aware Bundles](#router-bgp-vlan-aware-bundles)
    - [Router BGP VRFs](#router-bgp-vrfs)
    - [Router BGP Device Configuration](#router-bgp-device-configuration)
- [BFD](#bfd)
  - [Router BFD](#router-bfd)
    - [Router BFD Multihop Summary](#router-bfd-multihop-summary)
    - [Router BFD Device Configuration](#router-bfd-device-configuration)
- [Multicast](#multicast)
  - [IP IGMP Snooping](#ip-igmp-snooping)
    - [IP IGMP Snooping Summary](#ip-igmp-snooping-summary)
    - [IP IGMP Snooping Device Configuration](#ip-igmp-snooping-device-configuration)
- [Filters](#filters)
- [ACL](#acl)
- [VRF Instances](#vrf-instances)
  - [VRF Instances Summary](#vrf-instances-summary)
  - [VRF Instances Device Configuration](#vrf-instances-device-configuration)
- [Quality Of Service](#quality-of-service)

# Management

## Management Interfaces

### Management Interfaces Summary

#### IPv4

| Management Interface | description | Type | VRF | IP Address | Gateway |
| -------------------- | ----------- | ---- | --- | ---------- | ------- |

#### IPv6

| Management Interface | description | Type | VRF | IPv6 Address | IPv6 Gateway |
| -------------------- | ----------- | ---- | --- | ------------ | ------------ |

## DNS Domain

### DNS domain: atd.lab

### DNS Domain Device Configuration

```eos
dns domain atd.lab
!
```

## Name Servers

### Name Servers Summary

| Name Server | Source VRF |
| ----------- | ---------- |
| 8.8.8.8 | default |

### Name Servers Device Configuration

```eos
ip name-server vrf default 8.8.8.8
```

## Management API HTTP

### Management API HTTP Summary

| HTTP | HTTPS | Default Services |
| ---- | ----- | ---------------- |
| False | True | - |

### Management API VRF Access

| VRF Name | IPv4 ACL | IPv6 ACL |
| -------- | -------- | -------- |
| default | - | - |

### Management API HTTP Configuration

```eos
!
management api http-commands
   protocol https
   no shutdown
   !
   vrf default
      no shutdown
```

# Authentication

# Monitoring

# Spanning Tree

## Spanning Tree Summary

STP mode: **mstp**

### MSTP Instance and Priority

| Instance(s) | Priority |
| -------- | -------- |
| 0 | 16384 |

## Spanning Tree Device Configuration

```eos
!
spanning-tree mode mstp
spanning-tree mst 0 priority 16384
```

# Internal VLAN Allocation Policy

## Internal VLAN Allocation Policy Summary

| Policy Allocation | Range Beginning | Range Ending |
| ------------------| --------------- | ------------ |
| ascending | 1006 | 1199 |

## Internal VLAN Allocation Policy Configuration

```eos
!
vlan internal order ascending range 1006 1199
```

# Interfaces

## Ethernet Interfaces

### Ethernet Interfaces Summary

#### L2

| Interface | Description | Mode | VLANs | Native VLAN | Trunk Group | Channel-Group |
| --------- | ----------- | ---- | ----- | ----------- | ----------- | ------------- |
| Ethernet1 |  - | access | - | - | - | - |

#### IPv4

| Interface | Description | Type | Channel Group | IP Address | VRF |  MTU | Shutdown | ACL In | ACL Out |
| --------- | ----------- | -----| ------------- | ---------- | ----| ---- | -------- | ------ | ------- |
| Ethernet1 | | routed | - | dynamic | default | 1500 | False | - | - |

### Ethernet Interfaces Device Configuration

```eos
!
interface Ethernet1
   shutdown
   no switchport
   ip address dhcp
!
```

## VXLAN Interface

### VXLAN Interface Summary

| Setting | Value |
| ------- | ----- |
| Source Interface | Loopback1 |
| UDP port | 4789 |

#### VLAN to VNI, Flood List and Multicast Group Mappings

| VLAN | VNI | Flood List | Multicast Group |
| ---- | --- | ---------- | --------------- |
| 110 | 10110 | - | - |
| 210 | 10210 | - | - |

#### VRF to VNI and Multicast Group Mappings

| VRF | VNI | Multicast Group |
| ---- | --- | --------------- |
| Tenant_A_OP_Zone | 10 | - |

### VXLAN Interface Device Configuration

```eos
!
interface Vxlan1
   description s1-leaf1_VTEP
   vxlan source-interface Loopback1
   vxlan udp-port 4789
   vxlan vlan 110 vni 10110
   vxlan vlan 210 vni 10210
   vxlan vrf Tenant_A_OP_Zone vni 10
```

# Routing
## Service Routing Protocols Model

Multi agent routing protocol model disabled

```eos
!
service routing protocols model ribd
```

## Virtual Router MAC Address

### Virtual Router MAC Address Summary

#### Virtual Router MAC Address: 00:1c:73:00:dc:01

### Virtual Router MAC Address Configuration

```eos
!
ip virtual-router mac-address 00:1c:73:00:dc:01
```

## IP Routing

### IP Routing Summary

| VRF | Routing Enabled |
| --- | --------------- |
| default | True |
| default | false |
| Tenant_A_OP_Zone | true |

### IP Routing Device Configuration

```eos
!
ip routing
ip routing vrf Tenant_A_OP_Zone
```
## IPv6 Routing

### IPv6 Routing Summary

| VRF | Routing Enabled |
| --- | --------------- |
| default | False |
| default | false |
| Tenant_A_OP_Zone | false |

## Static Routes

### Static Routes Summary

| VRF | Destination Prefix | Next Hop IP             | Exit interface      | Administrative Distance       | Tag               | Route Name                    | Metric         |
| --- | ------------------ | ----------------------- | ------------------- | ----------------------------- | ----------------- | ----------------------------- | -------------- |
| default | 0.0.0.0/0 | 155.204.132.249 | - | 1 | - | - | - |

### Static Routes Device Configuration

```eos
!
ip route 0.0.0.0/0 155.204.132.249
```

## Router BGP

### Router BGP Summary

| BGP AS | Router ID |
| ------ | --------- |
| 65100|  10.0.0.1 |

| BGP Tuning |
| ---------- |
| no bgp default ipv4-unicast |
| distance bgp 20 200 200 |
| graceful-restart restart-time 300 |
| graceful-restart |
| maximum-paths 4 ecmp 4 |

### Router BGP Peer Groups

#### EVPN-OVERLAY-PEERS

| Settings | Value |
| -------- | ----- |
| Address Family | evpn |
| Source | Loopback0 |
| BFD | True |
| Ebgp multihop | 3 |
| Send community | all |
| Maximum routes | 0 (no limit) |

### BGP Neighbors

| Neighbor | Remote AS | VRF | Shutdown | Send-community | Maximum-routes | Allowas-in | BFD | RIB Pre-Policy Retain | Route-Reflector Client |
| -------- | --------- | --- | -------- | -------------- | -------------- | ---------- | --- | --------------------- | ---------------------- |
| 192.0.255.1 | 65100 | default | - | | | - | | - | - |

### Router BGP EVPN Address Family

#### EVPN Peer Groups

| Peer Group | Activate |
| ---------- | -------- |
| EVPN-OVERLAY-PEERS | True |

### Router BGP VLAN Aware Bundles

| VLAN Aware Bundle | Route-Distinguisher | Both Route-Target | Import Route Target | Export Route-Target | Redistribute | VLANs |
| ----------------- | ------------------- | ----------------- | ------------------- | ------------------- | ------------ | ----- |
| Extend | 192.0.255.3:10110 | 10110:10110 | - | - | learned | 110 |
| Tenant_A_OP_Zone | 192.0.255.3:10 | 10:10 | - | - | learned | 210 |

### Router BGP VRFs

| VRF | Route-Distinguisher | Redistribute |
| --- | ------------------- | ------------ |
| Tenant_A_OP_Zone | 192.0.255.3:10 | connected |

### Router BGP Device Configuration

```eos
!
router bgp 65100
   router-id 192.0.255.3
   no bgp default ipv4-unicast
   distance bgp 20 200 200
   graceful-restart restart-time 300
   graceful-restart
   maximum-paths 4 ecmp 4
   neighbor EVPN-OVERLAY-PEERS peer group
   neighbor EVPN-OVERLAY-PEERS update-source Loopback0
   neighbor EVPN-OVERLAY-PEERS bfd
   neighbor EVPN-OVERLAY-PEERS ebgp-multihop 3
   neighbor EVPN-OVERLAY-PEERS password 7 q+VNViP5i4rVjW1cxFv2wA==
   neighbor EVPN-OVERLAY-PEERS send-community
   neighbor EVPN-OVERLAY-PEERS maximum-routes 0
   neighbor 192.0.255.1 peer group EVPN-OVERLAY-PEERS
   neighbor 192.0.255.1 remote-as 65001
   neighbor 192.0.255.1 description s1-spine1
   !
   vlan-aware-bundle Extend
      rd 192.0.255.3:10110
      route-target both 10110:10110
      redistribute learned
      vlan 110
   !
   vlan-aware-bundle Tenant_A_OP_Zone
      rd 192.0.255.3:10
      route-target both 10:10
      redistribute learned
      vlan 210
   !
   address-family evpn
      neighbor EVPN-OVERLAY-PEERS activate
   !
   address-family ipv4
      no neighbor EVPN-OVERLAY-PEERS activate
   !
   vrf Tenant_A_OP_Zone
      rd 192.0.255.3:10
      route-target import evpn 10:10
      route-target export evpn 10:10
      router-id 192.0.255.3
      redistribute connected
```

# BFD

## Router BFD

### Router BFD Multihop Summary

| Interval | Minimum RX | Multiplier |
| -------- | ---------- | ---------- |
| 1200 | 1200 | 3 |

### Router BFD Device Configuration

```eos
!
router bfd
   multihop interval 1200 min-rx 1200 multiplier 3
```

# Multicast

## IP IGMP Snooping

### IP IGMP Snooping Summary

| IGMP Snooping | Fast Leave | Interface Restart Query | Proxy | Restart Query Interval | Robustness Variable |
| ------------- | ---------- | ----------------------- | ----- | ---------------------- | ------------------- |
| Enabled | - | - | - | - | - |

### IP IGMP Snooping Device Configuration

```eos
```

# Filters

# ACL

# VRF Instances

## VRF Instances Summary

| VRF Name | IP Routing |
| -------- | ---------- |
| default | disabled |
| Tenant_A_OP_Zone | enabled |

## VRF Instances Device Configuration

```eos
!
vrf instance Tenant_A_OP_Zone
```

# Quality Of Service