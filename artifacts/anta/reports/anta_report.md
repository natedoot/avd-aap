# 📊 ANTA Report <a id="anta-report"></a>

**Table of Contents:**

- [ANTA Report](#anta-report)
  - [Test Results Summary](#test-results-summary)
    - [Summary Totals](#summary-totals)
    - [Summary Totals Device Under Test](#summary-totals-device-under-test)
    - [Summary Totals Per Category](#summary-totals-per-category)
  - [Test Results](#test-results)

## 📉 Test Results Summary <a id="test-results-summary"></a>

### 🔢 Summary Totals <a id="summary-totals"></a>

| Total Tests | ✅&nbsp;Success | ⏭️&nbsp;Skipped | ❌&nbsp;Failure | ❗&nbsp;Error |
| :- | :- | :- | :- | :- |
| 252 | 162 | 56 | 34 | 0 |

### 🔌 Summary Totals Device Under Test <a id="summary-totals-device-under-test"></a>

| Device | Total Tests | ✅&nbsp;Success | ⏭️&nbsp;Skipped | ❌&nbsp;Failure | ❗&nbsp;Error | Categories Skipped | Categories Failed |
| :- | :- | :- | :- | :- | :- | :- | :- |
| **dc1-leaf1a** | 33 | 20 | 7 | 6 | 0 | Hardware | Configuration, Interfaces, Logging, MLAG, System |
| **dc1-leaf1b** | 33 | 20 | 7 | 6 | 0 | Hardware | Configuration, Interfaces, Logging, MLAG, System |
| **dc1-leaf2a** | 33 | 20 | 7 | 6 | 0 | Hardware | Configuration, Interfaces, Logging, MLAG, System |
| **dc1-leaf2b** | 33 | 20 | 7 | 6 | 0 | Hardware | Configuration, Interfaces, Logging, MLAG, System |
| **dc1-leaf3a** | 33 | 23 | 7 | 3 | 0 | Hardware | Configuration, Logging, System |
| **dc1-leaf3b** | 33 | 23 | 7 | 3 | 0 | Hardware | Configuration, Logging, System |
| **dc1-spine1** | 27 | 18 | 7 | 2 | 0 | Hardware | Logging, System |
| **dc1-spine2** | 27 | 18 | 7 | 2 | 0 | Hardware | Logging, System |

### 🗂️ Summary Totals Per Category <a id="summary-totals-per-category"></a>

| Test Category | Total Tests | ✅&nbsp;Success | ⏭️&nbsp;Skipped | ❌&nbsp;Failure | ❗&nbsp;Error |
| :- | :- | :- | :- | :- | :- |
| **BGP** | 8 | 8 | 0 | 0 | 0 |
| **Configuration** | 16 | 10 | 0 | 6 | 0 |
| **Connectivity** | 16 | 16 | 0 | 0 | 0 |
| **Hardware** | 56 | 0 | 56 | 0 | 0 |
| **Interfaces** | 52 | 44 | 0 | 8 | 0 |
| **Logging** | 8 | 0 | 0 | 8 | 0 |
| **MLAG** | 18 | 14 | 0 | 4 | 0 |
| **Routing** | 8 | 8 | 0 | 0 | 0 |
| **STP** | 8 | 8 | 0 | 0 | 0 |
| **System** | 56 | 48 | 0 | 8 | 0 |
| **VXLAN** | 6 | 6 | 0 | 0 | 0 |

## 🧪 Test Results <a id="test-results"></a>

| Device | Categories | Test | Description | Result | Messages |
| :- | :- | :- | :- | :- | :- |
| dc1-leaf1a | Configuration | VerifyRunningConfigDiffs | Verifies there is no difference between the running-config and the startup-config. | ❌&nbsp;Failure | --- flash:/startup-config<br>+++ system:/running-config<br>@@ -43,12 +43,6 @@<br> vlan 12<br>    name VRF10_VLAN12<br> !<br>-vlan 13<br>-   name VRF10_VLAN13<br>-!<br>-vlan 14<br>-   name VRF10_VLAN14<br>-!<br> vlan 21<br>    name VRF12_VLAN21<br> !<br>@@ -236,16 +230,6 @@<br>    vrf VRF10<br>    ip address virtual 10.10.12.1/24<br> !<br>-interface Vlan13<br>-   description VRF10_VLAN13<br>-   vrf VRF10<br>-   ip address virtual 10.10.13.1/24<br>-!<br>-interface Vlan14<br>-   description VRF10_VLAN14<br>-   vrf VRF10<br>-   ip address virtual 10.10.14.1/24<br>-!<br> interface Vlan21<br>    description VRF12_VLAN21<br>    vrf VRF12<br>@@ -286,8 +270,6 @@<br>    vxlan udp-port 4789<br>    vxlan vlan 11 vni 10011<br>    vxlan vlan 12 vni 10012<br>-   vxlan vlan 13 vni 10013<br>-   vxlan vlan 14 vni 10014<br>    vxlan vlan 21 vni 10021<br>    vxlan vlan 22 vni 10022<br>    vxlan vlan 3401 vni 13401<br>@@ -383,16 +365,6 @@<br>       route-target both 10012:10012<br>       redistribute learned<br>    !<br>-   vlan 13<br>-      rd 1.1.0.3:10013<br>-      route-target both 10013:10013<br>-      redistribute learned<br>-   !<br>-   vlan 14<br>-      rd 1.1.0.3:10014<br>-      route-target both 10014:10014<br>-      redistribute learned<br>-   !<br>    vlan 21<br>       rd 1.1.0.3:10021<br>       route-target both 10021:10021<br> |
| dc1-leaf1a | Interfaces | VerifyInterfacesStatus | Verifies the operational states of specified interfaces to ensure they match expected configurations. | ❌&nbsp;Failure | Interface: Ethernet4 - Status mismatch - Expected: up/up, Actual: down/down<br>Interface: Port-Channel4 - Status mismatch - Expected: up/up, Actual: down/lowerLayerDown |
| dc1-leaf1a | Interfaces | VerifyPortChannels | Verifies there are no inactive ports in port channels. | ❌&nbsp;Failure | Interface: Port-Channel4 - Inactive port(s) - Ethernet4, PeerEthernet4 |
| dc1-leaf1a | Logging | VerifyLoggingErrors | Verifies there are no syslog messages with a severity of ERRORS or higher. | ❌&nbsp;Failure | Device has reported syslog messages with a severity of ERRORS or higher:<br>Mar 26 12:56:21 dc1-leaf1a ProcMgr: %PROCMGR-3-SHUTDOWNREQUESTED: ProcMgr shutdown requested via SIGQUIT or SIGTERM to worker (PID=1451) -- Master ProcMgr (PID=1451) exiting.<br> Mar 26 12:56:21 dc1-leaf1a Stp: %FWK-3-SOCKET_CLOSE_REMOTE: Connection to StpTxRx (pid:1866) at tbl://stpTxRxListen/+n closed by peer (EOF)<br> Mar 26 12:56:21 dc1-leaf1a Stp: %FWK-3-MOUNT_PEER_CLOSED: Peer closed socket connection. (tbl://stpTxRxListen/+n-in)(StpTxRx (pid:1866))<br> Mar 26 12:57:17 dc1-leaf1a Bgp: %BGP-3-NOTIFICATION: sent to neighbor 1.1.1.97 (VRF VRF12 AS 65101) 6/7 (Cease/connection collision resolution) 0 bytes <br> Mar 26 12:57:17 dc1-leaf1a Bgp: %BGP-3-NOTIFICATION: sent to neighbor 1.1.1.97 (VRF default AS 65101) 6/7 (Cease/connection collision resolution) 0 bytes <br> Mar 26 12:57:18 dc1-leaf1a Bgp: %BGP-3-NOTIFICATION: sent to neighbor 1.1.255.2 (VRF default AS 65100) 6/5 (Cease/connection rejected) 0 bytes<br> Mar 26 12:57:18 dc1-leaf1a Bgp: %BGP-3-NOTIFICATION: sent to neighbor 1.1.255.0 (VRF default AS 65100) 6/5 (Cease/connection rejected) 0 bytes<br> <br> |
| dc1-leaf1a | MLAG | VerifyMlagInterfaces | Verifies there are no inactive or active-partial MLAG ports. | ❌&nbsp;Failure | MLAG status is not ok - Inactive Ports: 1 Partial Active Ports: 0 |
| dc1-leaf1a | System | VerifyNTP | Verifies if NTP is synchronised. | ❌&nbsp;Failure | NTP status mismatch - Expected: synchronised Actual: unsynchronised |
| dc1-leaf1b | Configuration | VerifyRunningConfigDiffs | Verifies there is no difference between the running-config and the startup-config. | ❌&nbsp;Failure | --- flash:/startup-config<br>+++ system:/running-config<br>@@ -43,12 +43,6 @@<br> vlan 12<br>    name VRF10_VLAN12<br> !<br>-vlan 13<br>-   name VRF10_VLAN13<br>-!<br>-vlan 14<br>-   name VRF10_VLAN14<br>-!<br> vlan 21<br>    name VRF12_VLAN21<br> !<br>@@ -236,16 +230,6 @@<br>    vrf VRF10<br>    ip address virtual 10.10.12.1/24<br> !<br>-interface Vlan13<br>-   description VRF10_VLAN13<br>-   vrf VRF10<br>-   ip address virtual 10.10.13.1/24<br>-!<br>-interface Vlan14<br>-   description VRF10_VLAN14<br>-   vrf VRF10<br>-   ip address virtual 10.10.14.1/24<br>-!<br> interface Vlan21<br>    description VRF12_VLAN21<br>    vrf VRF12<br>@@ -286,8 +270,6 @@<br>    vxlan udp-port 4789<br>    vxlan vlan 11 vni 10011<br>    vxlan vlan 12 vni 10012<br>-   vxlan vlan 13 vni 10013<br>-   vxlan vlan 14 vni 10014<br>    vxlan vlan 21 vni 10021<br>    vxlan vlan 22 vni 10022<br>    vxlan vlan 3401 vni 13401<br>@@ -383,16 +365,6 @@<br>       route-target both 10012:10012<br>       redistribute learned<br>    !<br>-   vlan 13<br>-      rd 1.1.0.4:10013<br>-      route-target both 10013:10013<br>-      redistribute learned<br>-   !<br>-   vlan 14<br>-      rd 1.1.0.4:10014<br>-      route-target both 10014:10014<br>-      redistribute learned<br>-   !<br>    vlan 21<br>       rd 1.1.0.4:10021<br>       route-target both 10021:10021<br> |
| dc1-leaf1b | Interfaces | VerifyInterfacesStatus | Verifies the operational states of specified interfaces to ensure they match expected configurations. | ❌&nbsp;Failure | Interface: Ethernet4 - Status mismatch - Expected: up/up, Actual: down/down<br>Interface: Port-Channel4 - Status mismatch - Expected: up/up, Actual: down/lowerLayerDown |
| dc1-leaf1b | Interfaces | VerifyPortChannels | Verifies there are no inactive ports in port channels. | ❌&nbsp;Failure | Interface: Port-Channel4 - Inactive port(s) - Ethernet4, PeerEthernet4 |
| dc1-leaf1b | Logging | VerifyLoggingErrors | Verifies there are no syslog messages with a severity of ERRORS or higher. | ❌&nbsp;Failure | Device has reported syslog messages with a severity of ERRORS or higher:<br>Mar 26 12:56:14 dc1-leaf1b ProcMgr: %PROCMGR-3-SHUTDOWNREQUESTED: ProcMgr shutdown requested via SIGQUIT or SIGTERM to worker (PID=1453) -- Master ProcMgr (PID=1453) exiting.<br> Mar 26 12:57:17 dc1-leaf1b Bgp: %BGP-3-NOTIFICATION: sent to neighbor 1.1.1.96 (VRF VRF12 AS 65101) 6/7 (Cease/connection collision resolution) 0 bytes <br> Mar 26 12:57:17 dc1-leaf1b Bgp: %BGP-3-NOTIFICATION: sent to neighbor 1.1.1.96 (VRF default AS 65101) 6/7 (Cease/connection collision resolution) 0 bytes <br> <br> |
| dc1-leaf1b | MLAG | VerifyMlagInterfaces | Verifies there are no inactive or active-partial MLAG ports. | ❌&nbsp;Failure | MLAG status is not ok - Inactive Ports: 1 Partial Active Ports: 0 |
| dc1-leaf1b | System | VerifyNTP | Verifies if NTP is synchronised. | ❌&nbsp;Failure | NTP status mismatch - Expected: synchronised Actual: unsynchronised |
| dc1-leaf2a | Configuration | VerifyRunningConfigDiffs | Verifies there is no difference between the running-config and the startup-config. | ❌&nbsp;Failure | --- flash:/startup-config<br>+++ system:/running-config<br>@@ -43,12 +43,6 @@<br> vlan 12<br>    name VRF10_VLAN12<br> !<br>-vlan 13<br>-   name VRF10_VLAN13<br>-!<br>-vlan 14<br>-   name VRF10_VLAN14<br>-!<br> vlan 21<br>    name VRF12_VLAN21<br> !<br>@@ -236,16 +230,6 @@<br>    vrf VRF10<br>    ip address virtual 10.10.12.1/24<br> !<br>-interface Vlan13<br>-   description VRF10_VLAN13<br>-   vrf VRF10<br>-   ip address virtual 10.10.13.1/24<br>-!<br>-interface Vlan14<br>-   description VRF10_VLAN14<br>-   vrf VRF10<br>-   ip address virtual 10.10.14.1/24<br>-!<br> interface Vlan21<br>    description VRF12_VLAN21<br>    vrf VRF12<br>@@ -286,8 +270,6 @@<br>    vxlan udp-port 4789<br>    vxlan vlan 11 vni 10011<br>    vxlan vlan 12 vni 10012<br>-   vxlan vlan 13 vni 10013<br>-   vxlan vlan 14 vni 10014<br>    vxlan vlan 21 vni 10021<br>    vxlan vlan 22 vni 10022<br>    vxlan vlan 3401 vni 13401<br>@@ -383,16 +365,6 @@<br>       route-target both 10012:10012<br>       redistribute learned<br>    !<br>-   vlan 13<br>-      rd 1.1.0.5:10013<br>-      route-target both 10013:10013<br>-      redistribute learned<br>-   !<br>-   vlan 14<br>-      rd 1.1.0.5:10014<br>-      route-target both 10014:10014<br>-      redistribute learned<br>-   !<br>    vlan 21<br>       rd 1.1.0.5:10021<br>       route-target both 10021:10021<br> |
| dc1-leaf2a | Interfaces | VerifyInterfacesStatus | Verifies the operational states of specified interfaces to ensure they match expected configurations. | ❌&nbsp;Failure | Interface: Ethernet4 - Status mismatch - Expected: up/up, Actual: down/down<br>Interface: Port-Channel4 - Status mismatch - Expected: up/up, Actual: down/lowerLayerDown |
| dc1-leaf2a | Interfaces | VerifyPortChannels | Verifies there are no inactive ports in port channels. | ❌&nbsp;Failure | Interface: Port-Channel4 - Inactive port(s) - Ethernet4, PeerEthernet4 |
| dc1-leaf2a | Logging | VerifyLoggingErrors | Verifies there are no syslog messages with a severity of ERRORS or higher. | ❌&nbsp;Failure | Device has reported syslog messages with a severity of ERRORS or higher:<br>Mar 26 12:56:22 dc1-leaf2a ProcMgr: %PROCMGR-3-SHUTDOWNREQUESTED: ProcMgr shutdown requested via SIGQUIT or SIGTERM to worker (PID=1450) -- Master ProcMgr (PID=1450) exiting.<br> Mar 26 12:56:22 dc1-leaf2a StpTxRx: %FWK-3-SOCKET_CLOSE_REMOTE: Connection to Stp (pid:1911) at tbl://stpListen/+n closed by peer (EOF)<br> Mar 26 12:56:22 dc1-leaf2a StpTxRx: %FWK-3-MOUNT_PEER_CLOSED: Peer closed socket connection. (tbl://stpListen/+n-in)(Stp (pid:1911))<br> Mar 26 12:57:22 dc1-leaf2a Bgp: %BGP-3-NOTIFICATION: sent to neighbor 1.1.255.8 (VRF default AS 65100) 6/5 (Cease/connection rejected) 0 bytes<br> <br> |
| dc1-leaf2a | MLAG | VerifyMlagInterfaces | Verifies there are no inactive or active-partial MLAG ports. | ❌&nbsp;Failure | MLAG status is not ok - Inactive Ports: 1 Partial Active Ports: 0 |
| dc1-leaf2a | System | VerifyNTP | Verifies if NTP is synchronised. | ❌&nbsp;Failure | NTP status mismatch - Expected: synchronised Actual: unsynchronised |
| dc1-leaf2b | Configuration | VerifyRunningConfigDiffs | Verifies there is no difference between the running-config and the startup-config. | ❌&nbsp;Failure | --- flash:/startup-config<br>+++ system:/running-config<br>@@ -43,12 +43,6 @@<br> vlan 12<br>    name VRF10_VLAN12<br> !<br>-vlan 13<br>-   name VRF10_VLAN13<br>-!<br>-vlan 14<br>-   name VRF10_VLAN14<br>-!<br> vlan 21<br>    name VRF12_VLAN21<br> !<br>@@ -236,16 +230,6 @@<br>    vrf VRF10<br>    ip address virtual 10.10.12.1/24<br> !<br>-interface Vlan13<br>-   description VRF10_VLAN13<br>-   vrf VRF10<br>-   ip address virtual 10.10.13.1/24<br>-!<br>-interface Vlan14<br>-   description VRF10_VLAN14<br>-   vrf VRF10<br>-   ip address virtual 10.10.14.1/24<br>-!<br> interface Vlan21<br>    description VRF12_VLAN21<br>    vrf VRF12<br>@@ -286,8 +270,6 @@<br>    vxlan udp-port 4789<br>    vxlan vlan 11 vni 10011<br>    vxlan vlan 12 vni 10012<br>-   vxlan vlan 13 vni 10013<br>-   vxlan vlan 14 vni 10014<br>    vxlan vlan 21 vni 10021<br>    vxlan vlan 22 vni 10022<br>    vxlan vlan 3401 vni 13401<br>@@ -383,16 +365,6 @@<br>       route-target both 10012:10012<br>       redistribute learned<br>    !<br>-   vlan 13<br>-      rd 1.1.0.6:10013<br>-      route-target both 10013:10013<br>-      redistribute learned<br>-   !<br>-   vlan 14<br>-      rd 1.1.0.6:10014<br>-      route-target both 10014:10014<br>-      redistribute learned<br>-   !<br>    vlan 21<br>       rd 1.1.0.6:10021<br>       route-target both 10021:10021<br> |
| dc1-leaf2b | Interfaces | VerifyInterfacesStatus | Verifies the operational states of specified interfaces to ensure they match expected configurations. | ❌&nbsp;Failure | Interface: Ethernet4 - Status mismatch - Expected: up/up, Actual: down/down<br>Interface: Port-Channel4 - Status mismatch - Expected: up/up, Actual: down/lowerLayerDown |
| dc1-leaf2b | Interfaces | VerifyPortChannels | Verifies there are no inactive ports in port channels. | ❌&nbsp;Failure | Interface: Port-Channel4 - Inactive port(s) - Ethernet4, PeerEthernet4 |
| dc1-leaf2b | Logging | VerifyLoggingErrors | Verifies there are no syslog messages with a severity of ERRORS or higher. | ❌&nbsp;Failure | Device has reported syslog messages with a severity of ERRORS or higher:<br>Mar 26 12:56:26 dc1-leaf2b ProcMgr: %PROCMGR-3-SHUTDOWNREQUESTED: ProcMgr shutdown requested via SIGQUIT or SIGTERM to worker (PID=1451) -- Master ProcMgr (PID=1451) exiting.<br> Mar 26 12:56:26 dc1-leaf2b StpTxRx: %FWK-3-SOCKET_CLOSE_REMOTE: Connection to Stp (pid:1915) at tbl://stpListen/+n closed by peer (EOF)<br> Mar 26 12:56:26 dc1-leaf2b StpTxRx: %FWK-3-MOUNT_PEER_CLOSED: Peer closed socket connection. (tbl://stpListen/+n-in)(Stp (pid:1915))<br> Mar 26 12:57:22 dc1-leaf2b Bgp: %BGP-3-NOTIFICATION: sent to neighbor 1.1.255.12 (VRF default AS 65100) 6/5 (Cease/connection rejected) 0 bytes<br> Mar 26 12:57:22 dc1-leaf2b Bgp: %BGP-3-NOTIFICATION: sent to neighbor 1.1.255.14 (VRF default AS 65100) 6/5 (Cease/connection rejected) 0 bytes<br> <br> |
| dc1-leaf2b | MLAG | VerifyMlagInterfaces | Verifies there are no inactive or active-partial MLAG ports. | ❌&nbsp;Failure | MLAG status is not ok - Inactive Ports: 1 Partial Active Ports: 0 |
| dc1-leaf2b | System | VerifyNTP | Verifies if NTP is synchronised. | ❌&nbsp;Failure | NTP status mismatch - Expected: synchronised Actual: unsynchronised |
| dc1-leaf3a | Configuration | VerifyRunningConfigDiffs | Verifies there is no difference between the running-config and the startup-config. | ❌&nbsp;Failure | --- flash:/startup-config<br>+++ system:/running-config<br>@@ -43,12 +43,6 @@<br> vlan 12<br>    name VRF10_VLAN12<br> !<br>-vlan 13<br>-   name VRF10_VLAN13<br>-!<br>-vlan 14<br>-   name VRF10_VLAN14<br>-!<br> vlan 21<br>    name VRF12_VLAN21<br> !<br>@@ -226,16 +220,6 @@<br>    vrf VRF10<br>    ip address virtual 10.10.12.1/24<br> !<br>-interface Vlan13<br>-   description VRF10_VLAN13<br>-   vrf VRF10<br>-   ip address virtual 10.10.13.1/24<br>-!<br>-interface Vlan14<br>-   description VRF10_VLAN14<br>-   vrf VRF10<br>-   ip address virtual 10.10.14.1/24<br>-!<br> interface Vlan21<br>    description VRF12_VLAN21<br>    vrf VRF12<br>@@ -276,8 +260,6 @@<br>    vxlan udp-port 4789<br>    vxlan vlan 11 vni 10011<br>    vxlan vlan 12 vni 10012<br>-   vxlan vlan 13 vni 10013<br>-   vxlan vlan 14 vni 10014<br>    vxlan vlan 21 vni 10021<br>    vxlan vlan 22 vni 10022<br>    vxlan vlan 3401 vni 13401<br>@@ -373,16 +355,6 @@<br>       route-target both 10012:10012<br>       redistribute learned<br>    !<br>-   vlan 13<br>-      rd 1.1.0.7:10013<br>-      route-target both 10013:10013<br>-      redistribute learned<br>-   !<br>-   vlan 14<br>-      rd 1.1.0.7:10014<br>-      route-target both 10014:10014<br>-      redistribute learned<br>-   !<br>    vlan 21<br>       rd 1.1.0.7:10021<br>       route-target both 10021:10021<br> |
| dc1-leaf3a | Logging | VerifyLoggingErrors | Verifies there are no syslog messages with a severity of ERRORS or higher. | ❌&nbsp;Failure | Device has reported syslog messages with a severity of ERRORS or higher:<br>Mar 26 12:56:31 dc1-leaf3a ProcMgr: %PROCMGR-3-SHUTDOWNREQUESTED: ProcMgr shutdown requested via SIGQUIT or SIGTERM to worker (PID=1451) -- Master ProcMgr (PID=1451) exiting.<br> Mar 26 12:56:31 dc1-leaf3a StpTxRx: %FWK-3-SOCKET_CLOSE_REMOTE: Connection to Stp (pid:1925) at tbl://stpListen/+n closed by peer (EOF)<br> Mar 26 12:56:31 dc1-leaf3a StpTxRx: %FWK-3-MOUNT_PEER_CLOSED: Peer closed socket connection. (tbl://stpListen/+n-in)(Stp (pid:1925))<br> Mar 26 12:57:32 dc1-leaf3a Bgp: %BGP-3-NOTIFICATION: sent to neighbor 1.1.255.18 (VRF default AS 65100) 6/5 (Cease/connection rejected) 0 bytes<br> <br> |
| dc1-leaf3a | System | VerifyNTP | Verifies if NTP is synchronised. | ❌&nbsp;Failure | NTP status mismatch - Expected: synchronised Actual: unsynchronised |
| dc1-leaf3b | Configuration | VerifyRunningConfigDiffs | Verifies there is no difference between the running-config and the startup-config. | ❌&nbsp;Failure | --- flash:/startup-config<br>+++ system:/running-config<br>@@ -43,12 +43,6 @@<br> vlan 12<br>    name VRF10_VLAN12<br> !<br>-vlan 13<br>-   name VRF10_VLAN13<br>-!<br>-vlan 14<br>-   name VRF10_VLAN14<br>-!<br> vlan 21<br>    name VRF12_VLAN21<br> !<br>@@ -226,16 +220,6 @@<br>    vrf VRF10<br>    ip address virtual 10.10.12.1/24<br> !<br>-interface Vlan13<br>-   description VRF10_VLAN13<br>-   vrf VRF10<br>-   ip address virtual 10.10.13.1/24<br>-!<br>-interface Vlan14<br>-   description VRF10_VLAN14<br>-   vrf VRF10<br>-   ip address virtual 10.10.14.1/24<br>-!<br> interface Vlan21<br>    description VRF12_VLAN21<br>    vrf VRF12<br>@@ -276,8 +260,6 @@<br>    vxlan udp-port 4789<br>    vxlan vlan 11 vni 10011<br>    vxlan vlan 12 vni 10012<br>-   vxlan vlan 13 vni 10013<br>-   vxlan vlan 14 vni 10014<br>    vxlan vlan 21 vni 10021<br>    vxlan vlan 22 vni 10022<br>    vxlan vlan 3401 vni 13401<br>@@ -373,16 +355,6 @@<br>       route-target both 10012:10012<br>       redistribute learned<br>    !<br>-   vlan 13<br>-      rd 1.1.0.8:10013<br>-      route-target both 10013:10013<br>-      redistribute learned<br>-   !<br>-   vlan 14<br>-      rd 1.1.0.8:10014<br>-      route-target both 10014:10014<br>-      redistribute learned<br>-   !<br>    vlan 21<br>       rd 1.1.0.8:10021<br>       route-target both 10021:10021<br> |
| dc1-leaf3b | Logging | VerifyLoggingErrors | Verifies there are no syslog messages with a severity of ERRORS or higher. | ❌&nbsp;Failure | Device has reported syslog messages with a severity of ERRORS or higher:<br>Mar 26 12:56:25 dc1-leaf3b ProcMgr: %PROCMGR-3-SHUTDOWNREQUESTED: ProcMgr shutdown requested via SIGQUIT or SIGTERM to worker (PID=1451) -- Master ProcMgr (PID=1451) exiting.<br> Mar 26 12:56:26 dc1-leaf3b Stp: %FWK-3-SOCKET_CLOSE_REMOTE: Connection to StpTxRx (pid:1868) at tbl://stpTxRxListen/+n closed by peer (EOF)<br> Mar 26 12:56:26 dc1-leaf3b Stp: %FWK-3-MOUNT_PEER_CLOSED: Peer closed socket connection. (tbl://stpTxRxListen/+n-in)(StpTxRx (pid:1868))<br> Mar 26 12:57:30 dc1-leaf3b Bgp: %BGP-3-NOTIFICATION: sent to neighbor 1.1.255.22 (VRF default AS 65100) 6/5 (Cease/connection rejected) 0 bytes<br> Mar 26 12:57:30 dc1-leaf3b Bgp: %BGP-3-NOTIFICATION: sent to neighbor 1.1.255.20 (VRF default AS 65100) 6/5 (Cease/connection rejected) 0 bytes<br> <br> |
| dc1-leaf3b | System | VerifyNTP | Verifies if NTP is synchronised. | ❌&nbsp;Failure | NTP status mismatch - Expected: synchronised Actual: unsynchronised |
| dc1-spine1 | Logging | VerifyLoggingErrors | Verifies there are no syslog messages with a severity of ERRORS or higher. | ❌&nbsp;Failure | Device has reported syslog messages with a severity of ERRORS or higher:<br>Mar 26 12:56:17 dc1-spine1 ProcMgr: %PROCMGR-3-SHUTDOWNREQUESTED: ProcMgr shutdown requested via SIGQUIT or SIGTERM to worker (PID=1411) -- Master ProcMgr (PID=1411) exiting.<br> Mar 26 12:56:17 dc1-spine1 Stp: %FWK-3-SOCKET_CLOSE_REMOTE: Connection to StpTxRx (pid:1827) at tbl://stpTxRxListen/+n closed by peer (EOF)<br> Mar 26 12:56:17 dc1-spine1 Stp: %FWK-3-MOUNT_PEER_CLOSED: Peer closed socket connection. (tbl://stpTxRxListen/+n-in)(StpTxRx (pid:1827))<br> Mar 26 12:57:19 dc1-spine1 Bgp: %BGP-3-NOTIFICATION: received from neighbor 1.1.255.1 (VRF default AS 65101) 6/5 (Cease/connection rejected) 0 bytes<br> Mar 26 12:57:22 dc1-spine1 Bgp: %BGP-3-NOTIFICATION: received from neighbor 1.1.255.13 (VRF default AS 65102) 6/5 (Cease/connection rejected) 0 bytes<br> Mar 26 12:57:23 dc1-spine1 Bgp: %BGP-3-NOTIFICATION: received from neighbor 1.1.255.9 (VRF default AS 65102) 6/5 (Cease/connection rejected) 0 bytes<br> Mar 26 12:57:30 dc1-spine1 Bgp: %BGP-3-NOTIFICATION: received from neighbor 1.1.255.21 (VRF default AS 65103) 6/5 (Cease/connection rejected) 0 bytes<br> <br> |
| dc1-spine1 | System | VerifyNTP | Verifies if NTP is synchronised. | ❌&nbsp;Failure | NTP status mismatch - Expected: synchronised Actual: unsynchronised |
| dc1-spine2 | Logging | VerifyLoggingErrors | Verifies there are no syslog messages with a severity of ERRORS or higher. | ❌&nbsp;Failure | Device has reported syslog messages with a severity of ERRORS or higher:<br>Mar 26 12:56:21 dc1-spine2 ProcMgr: %PROCMGR-3-SHUTDOWNREQUESTED: ProcMgr shutdown requested via SIGQUIT or SIGTERM to worker (PID=1410) -- Master ProcMgr (PID=1410) exiting.<br> Mar 26 12:56:21 dc1-spine2 StpTxRx: %FWK-3-SOCKET_CLOSE_REMOTE: Connection to Stp (pid:1858) at tbl://stpListen/+n closed by peer (EOF)<br> Mar 26 12:56:21 dc1-spine2 StpTxRx: %FWK-3-MOUNT_PEER_CLOSED: Peer closed socket connection. (tbl://stpListen/+n-in)(Stp (pid:1858))<br> Mar 26 12:57:19 dc1-spine2 Bgp: %BGP-3-NOTIFICATION: received from neighbor 1.1.255.3 (VRF default AS 65101) 6/5 (Cease/connection rejected) 0 bytes<br> Mar 26 12:57:22 dc1-spine2 Bgp: %BGP-3-NOTIFICATION: received from neighbor 1.1.255.15 (VRF default AS 65102) 6/5 (Cease/connection rejected) 0 bytes<br> Mar 26 12:57:31 dc1-spine2 Bgp: %BGP-3-NOTIFICATION: received from neighbor 1.1.255.23 (VRF default AS 65103) 6/5 (Cease/connection rejected) 0 bytes<br> Mar 26 12:57:32 dc1-spine2 Bgp: %BGP-3-NOTIFICATION: received from neighbor 1.1.255.19 (VRF default AS 65103) 6/5 (Cease/connection rejected) 0 bytes<br> <br> |
| dc1-spine2 | System | VerifyNTP | Verifies if NTP is synchronised. | ❌&nbsp;Failure | NTP status mismatch - Expected: synchronised Actual: unsynchronised |
| dc1-leaf1a | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | ⏭️&nbsp;Skipped | VerifyEnvironmentCooling test is not supported on vEOS-lab |
| dc1-leaf1a | Hardware | VerifyEnvironmentPower | Verifies the power supplies state and input voltage. | ⏭️&nbsp;Skipped | VerifyEnvironmentPower test is not supported on vEOS-lab |
| dc1-leaf1a | Hardware | VerifyEnvironmentSystemCooling | Verifies the device's system cooling status. | ⏭️&nbsp;Skipped | VerifyEnvironmentSystemCooling test is not supported on vEOS-lab |
| dc1-leaf1a | Hardware | VerifyInventory | Verifies the physical hardware inventory of the device. | ⏭️&nbsp;Skipped | VerifyInventory test is not supported on vEOS-lab |
| dc1-leaf1a | Hardware | VerifyTemperature | Verifies if the device temperature is within acceptable limits. | ⏭️&nbsp;Skipped | VerifyTemperature test is not supported on vEOS-lab |
| dc1-leaf1a | Hardware | VerifyTransceiversManufacturers | Verifies if all the transceivers come from approved manufacturers. | ⏭️&nbsp;Skipped | VerifyTransceiversManufacturers test is not supported on vEOS-lab |
| dc1-leaf1a | Hardware | VerifyTransceiversTemperature | Verifies if all the transceivers are operating at an acceptable temperature. | ⏭️&nbsp;Skipped | VerifyTransceiversTemperature test is not supported on vEOS-lab |
| dc1-leaf1b | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | ⏭️&nbsp;Skipped | VerifyEnvironmentCooling test is not supported on vEOS-lab |
| dc1-leaf1b | Hardware | VerifyEnvironmentPower | Verifies the power supplies state and input voltage. | ⏭️&nbsp;Skipped | VerifyEnvironmentPower test is not supported on vEOS-lab |
| dc1-leaf1b | Hardware | VerifyEnvironmentSystemCooling | Verifies the device's system cooling status. | ⏭️&nbsp;Skipped | VerifyEnvironmentSystemCooling test is not supported on vEOS-lab |
| dc1-leaf1b | Hardware | VerifyInventory | Verifies the physical hardware inventory of the device. | ⏭️&nbsp;Skipped | VerifyInventory test is not supported on vEOS-lab |
| dc1-leaf1b | Hardware | VerifyTemperature | Verifies if the device temperature is within acceptable limits. | ⏭️&nbsp;Skipped | VerifyTemperature test is not supported on vEOS-lab |
| dc1-leaf1b | Hardware | VerifyTransceiversManufacturers | Verifies if all the transceivers come from approved manufacturers. | ⏭️&nbsp;Skipped | VerifyTransceiversManufacturers test is not supported on vEOS-lab |
| dc1-leaf1b | Hardware | VerifyTransceiversTemperature | Verifies if all the transceivers are operating at an acceptable temperature. | ⏭️&nbsp;Skipped | VerifyTransceiversTemperature test is not supported on vEOS-lab |
| dc1-leaf2a | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | ⏭️&nbsp;Skipped | VerifyEnvironmentCooling test is not supported on vEOS-lab |
| dc1-leaf2a | Hardware | VerifyEnvironmentPower | Verifies the power supplies state and input voltage. | ⏭️&nbsp;Skipped | VerifyEnvironmentPower test is not supported on vEOS-lab |
| dc1-leaf2a | Hardware | VerifyEnvironmentSystemCooling | Verifies the device's system cooling status. | ⏭️&nbsp;Skipped | VerifyEnvironmentSystemCooling test is not supported on vEOS-lab |
| dc1-leaf2a | Hardware | VerifyInventory | Verifies the physical hardware inventory of the device. | ⏭️&nbsp;Skipped | VerifyInventory test is not supported on vEOS-lab |
| dc1-leaf2a | Hardware | VerifyTemperature | Verifies if the device temperature is within acceptable limits. | ⏭️&nbsp;Skipped | VerifyTemperature test is not supported on vEOS-lab |
| dc1-leaf2a | Hardware | VerifyTransceiversManufacturers | Verifies if all the transceivers come from approved manufacturers. | ⏭️&nbsp;Skipped | VerifyTransceiversManufacturers test is not supported on vEOS-lab |
| dc1-leaf2a | Hardware | VerifyTransceiversTemperature | Verifies if all the transceivers are operating at an acceptable temperature. | ⏭️&nbsp;Skipped | VerifyTransceiversTemperature test is not supported on vEOS-lab |
| dc1-leaf2b | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | ⏭️&nbsp;Skipped | VerifyEnvironmentCooling test is not supported on vEOS-lab |
| dc1-leaf2b | Hardware | VerifyEnvironmentPower | Verifies the power supplies state and input voltage. | ⏭️&nbsp;Skipped | VerifyEnvironmentPower test is not supported on vEOS-lab |
| dc1-leaf2b | Hardware | VerifyEnvironmentSystemCooling | Verifies the device's system cooling status. | ⏭️&nbsp;Skipped | VerifyEnvironmentSystemCooling test is not supported on vEOS-lab |
| dc1-leaf2b | Hardware | VerifyInventory | Verifies the physical hardware inventory of the device. | ⏭️&nbsp;Skipped | VerifyInventory test is not supported on vEOS-lab |
| dc1-leaf2b | Hardware | VerifyTemperature | Verifies if the device temperature is within acceptable limits. | ⏭️&nbsp;Skipped | VerifyTemperature test is not supported on vEOS-lab |
| dc1-leaf2b | Hardware | VerifyTransceiversManufacturers | Verifies if all the transceivers come from approved manufacturers. | ⏭️&nbsp;Skipped | VerifyTransceiversManufacturers test is not supported on vEOS-lab |
| dc1-leaf2b | Hardware | VerifyTransceiversTemperature | Verifies if all the transceivers are operating at an acceptable temperature. | ⏭️&nbsp;Skipped | VerifyTransceiversTemperature test is not supported on vEOS-lab |
| dc1-leaf3a | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | ⏭️&nbsp;Skipped | VerifyEnvironmentCooling test is not supported on vEOS-lab |
| dc1-leaf3a | Hardware | VerifyEnvironmentPower | Verifies the power supplies state and input voltage. | ⏭️&nbsp;Skipped | VerifyEnvironmentPower test is not supported on vEOS-lab |
| dc1-leaf3a | Hardware | VerifyEnvironmentSystemCooling | Verifies the device's system cooling status. | ⏭️&nbsp;Skipped | VerifyEnvironmentSystemCooling test is not supported on vEOS-lab |
| dc1-leaf3a | Hardware | VerifyInventory | Verifies the physical hardware inventory of the device. | ⏭️&nbsp;Skipped | VerifyInventory test is not supported on vEOS-lab |
| dc1-leaf3a | Hardware | VerifyTemperature | Verifies if the device temperature is within acceptable limits. | ⏭️&nbsp;Skipped | VerifyTemperature test is not supported on vEOS-lab |
| dc1-leaf3a | Hardware | VerifyTransceiversManufacturers | Verifies if all the transceivers come from approved manufacturers. | ⏭️&nbsp;Skipped | VerifyTransceiversManufacturers test is not supported on vEOS-lab |
| dc1-leaf3a | Hardware | VerifyTransceiversTemperature | Verifies if all the transceivers are operating at an acceptable temperature. | ⏭️&nbsp;Skipped | VerifyTransceiversTemperature test is not supported on vEOS-lab |
| dc1-leaf3b | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | ⏭️&nbsp;Skipped | VerifyEnvironmentCooling test is not supported on vEOS-lab |
| dc1-leaf3b | Hardware | VerifyEnvironmentPower | Verifies the power supplies state and input voltage. | ⏭️&nbsp;Skipped | VerifyEnvironmentPower test is not supported on vEOS-lab |
| dc1-leaf3b | Hardware | VerifyEnvironmentSystemCooling | Verifies the device's system cooling status. | ⏭️&nbsp;Skipped | VerifyEnvironmentSystemCooling test is not supported on vEOS-lab |
| dc1-leaf3b | Hardware | VerifyInventory | Verifies the physical hardware inventory of the device. | ⏭️&nbsp;Skipped | VerifyInventory test is not supported on vEOS-lab |
| dc1-leaf3b | Hardware | VerifyTemperature | Verifies if the device temperature is within acceptable limits. | ⏭️&nbsp;Skipped | VerifyTemperature test is not supported on vEOS-lab |
| dc1-leaf3b | Hardware | VerifyTransceiversManufacturers | Verifies if all the transceivers come from approved manufacturers. | ⏭️&nbsp;Skipped | VerifyTransceiversManufacturers test is not supported on vEOS-lab |
| dc1-leaf3b | Hardware | VerifyTransceiversTemperature | Verifies if all the transceivers are operating at an acceptable temperature. | ⏭️&nbsp;Skipped | VerifyTransceiversTemperature test is not supported on vEOS-lab |
| dc1-spine1 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | ⏭️&nbsp;Skipped | VerifyEnvironmentCooling test is not supported on vEOS-lab |
| dc1-spine1 | Hardware | VerifyEnvironmentPower | Verifies the power supplies state and input voltage. | ⏭️&nbsp;Skipped | VerifyEnvironmentPower test is not supported on vEOS-lab |
| dc1-spine1 | Hardware | VerifyEnvironmentSystemCooling | Verifies the device's system cooling status. | ⏭️&nbsp;Skipped | VerifyEnvironmentSystemCooling test is not supported on vEOS-lab |
| dc1-spine1 | Hardware | VerifyInventory | Verifies the physical hardware inventory of the device. | ⏭️&nbsp;Skipped | VerifyInventory test is not supported on vEOS-lab |
| dc1-spine1 | Hardware | VerifyTemperature | Verifies if the device temperature is within acceptable limits. | ⏭️&nbsp;Skipped | VerifyTemperature test is not supported on vEOS-lab |
| dc1-spine1 | Hardware | VerifyTransceiversManufacturers | Verifies if all the transceivers come from approved manufacturers. | ⏭️&nbsp;Skipped | VerifyTransceiversManufacturers test is not supported on vEOS-lab |
| dc1-spine1 | Hardware | VerifyTransceiversTemperature | Verifies if all the transceivers are operating at an acceptable temperature. | ⏭️&nbsp;Skipped | VerifyTransceiversTemperature test is not supported on vEOS-lab |
| dc1-spine2 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | ⏭️&nbsp;Skipped | VerifyEnvironmentCooling test is not supported on vEOS-lab |
| dc1-spine2 | Hardware | VerifyEnvironmentPower | Verifies the power supplies state and input voltage. | ⏭️&nbsp;Skipped | VerifyEnvironmentPower test is not supported on vEOS-lab |
| dc1-spine2 | Hardware | VerifyEnvironmentSystemCooling | Verifies the device's system cooling status. | ⏭️&nbsp;Skipped | VerifyEnvironmentSystemCooling test is not supported on vEOS-lab |
| dc1-spine2 | Hardware | VerifyInventory | Verifies the physical hardware inventory of the device. | ⏭️&nbsp;Skipped | VerifyInventory test is not supported on vEOS-lab |
| dc1-spine2 | Hardware | VerifyTemperature | Verifies if the device temperature is within acceptable limits. | ⏭️&nbsp;Skipped | VerifyTemperature test is not supported on vEOS-lab |
| dc1-spine2 | Hardware | VerifyTransceiversManufacturers | Verifies if all the transceivers come from approved manufacturers. | ⏭️&nbsp;Skipped | VerifyTransceiversManufacturers test is not supported on vEOS-lab |
| dc1-spine2 | Hardware | VerifyTransceiversTemperature | Verifies if all the transceivers are operating at an acceptable temperature. | ⏭️&nbsp;Skipped | VerifyTransceiversTemperature test is not supported on vEOS-lab |
| dc1-leaf1a | BGP | VerifyBGPPeerSession | Verifies the session state of BGP peers. | ✅&nbsp;Success | - |
| dc1-leaf1a | Configuration | VerifyZeroTouch | Verifies ZeroTouch is disabled. | ✅&nbsp;Success | - |
| dc1-leaf1a | Connectivity | VerifyLLDPNeighbors | Verifies the connection status of the specified LLDP (Link Layer Discovery Protocol) neighbors. | ✅&nbsp;Success | - |
| dc1-leaf1a | Connectivity | VerifyReachability | Verifies point-to-point reachability between Ethernet interfaces. | ✅&nbsp;Success | - |
| dc1-leaf1a | Interfaces | VerifyIllegalLACP | Verifies there are no illegal LACP packets in port channels. | ✅&nbsp;Success | - |
| dc1-leaf1a | Interfaces | VerifyInterfaceDiscards | Verifies that the interfaces packet discard counters are equal to zero. | ✅&nbsp;Success | - |
| dc1-leaf1a | Interfaces | VerifyInterfaceErrDisabled | Verifies there are no interfaces in the errdisabled state. | ✅&nbsp;Success | - |
| dc1-leaf1a | Interfaces | VerifyInterfaceErrors | Verifies that the interfaces error counters are equal to zero. | ✅&nbsp;Success | - |
| dc1-leaf1a | Interfaces | VerifyInterfaceUtilization | Verifies that the utilization of interfaces is below a certain threshold. | ✅&nbsp;Success | - |
| dc1-leaf1a | MLAG | VerifyMlagConfigSanity | Verifies there are no MLAG config-sanity inconsistencies. | ✅&nbsp;Success | - |
| dc1-leaf1a | MLAG | VerifyMlagStatus | Verifies the health status of the MLAG configuration. | ✅&nbsp;Success | - |
| dc1-leaf1a | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | ✅&nbsp;Success | - |
| dc1-leaf1a | STP | VerifySTPCounters | Verifies there is no errors in STP BPDU packets. | ✅&nbsp;Success | - |
| dc1-leaf1a | System | VerifyAgentLogs | Verifies there are no agent crash reports. | ✅&nbsp;Success | - |
| dc1-leaf1a | System | VerifyCoredump | Verifies there are no core dump files. | ✅&nbsp;Success | - |
| dc1-leaf1a | System | VerifyFileSystemUtilization | Verifies that no partition is utilizing more than 75% of its disk space. | ✅&nbsp;Success | - |
| dc1-leaf1a | System | VerifyMaintenance | Verifies that the device is not currently under or entering maintenance. | ✅&nbsp;Success | - |
| dc1-leaf1a | System | VerifyMemoryUtilization | Verifies whether the memory utilization is below 75%. | ✅&nbsp;Success | - |
| dc1-leaf1a | System | VerifyReloadCause | Verifies the last reload cause of the device. | ✅&nbsp;Success | - |
| dc1-leaf1a | VXLAN | VerifyVxlanConfigSanity | Verifies there are no VXLAN config-sanity inconsistencies. | ✅&nbsp;Success | - |
| dc1-leaf1b | BGP | VerifyBGPPeerSession | Verifies the session state of BGP peers. | ✅&nbsp;Success | - |
| dc1-leaf1b | Configuration | VerifyZeroTouch | Verifies ZeroTouch is disabled. | ✅&nbsp;Success | - |
| dc1-leaf1b | Connectivity | VerifyLLDPNeighbors | Verifies the connection status of the specified LLDP (Link Layer Discovery Protocol) neighbors. | ✅&nbsp;Success | - |
| dc1-leaf1b | Connectivity | VerifyReachability | Verifies point-to-point reachability between Ethernet interfaces. | ✅&nbsp;Success | - |
| dc1-leaf1b | Interfaces | VerifyIllegalLACP | Verifies there are no illegal LACP packets in port channels. | ✅&nbsp;Success | - |
| dc1-leaf1b | Interfaces | VerifyInterfaceDiscards | Verifies that the interfaces packet discard counters are equal to zero. | ✅&nbsp;Success | - |
| dc1-leaf1b | Interfaces | VerifyInterfaceErrDisabled | Verifies there are no interfaces in the errdisabled state. | ✅&nbsp;Success | - |
| dc1-leaf1b | Interfaces | VerifyInterfaceErrors | Verifies that the interfaces error counters are equal to zero. | ✅&nbsp;Success | - |
| dc1-leaf1b | Interfaces | VerifyInterfaceUtilization | Verifies that the utilization of interfaces is below a certain threshold. | ✅&nbsp;Success | - |
| dc1-leaf1b | MLAG | VerifyMlagConfigSanity | Verifies there are no MLAG config-sanity inconsistencies. | ✅&nbsp;Success | - |
| dc1-leaf1b | MLAG | VerifyMlagStatus | Verifies the health status of the MLAG configuration. | ✅&nbsp;Success | - |
| dc1-leaf1b | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | ✅&nbsp;Success | - |
| dc1-leaf1b | STP | VerifySTPCounters | Verifies there is no errors in STP BPDU packets. | ✅&nbsp;Success | - |
| dc1-leaf1b | System | VerifyAgentLogs | Verifies there are no agent crash reports. | ✅&nbsp;Success | - |
| dc1-leaf1b | System | VerifyCoredump | Verifies there are no core dump files. | ✅&nbsp;Success | - |
| dc1-leaf1b | System | VerifyFileSystemUtilization | Verifies that no partition is utilizing more than 75% of its disk space. | ✅&nbsp;Success | - |
| dc1-leaf1b | System | VerifyMaintenance | Verifies that the device is not currently under or entering maintenance. | ✅&nbsp;Success | - |
| dc1-leaf1b | System | VerifyMemoryUtilization | Verifies whether the memory utilization is below 75%. | ✅&nbsp;Success | - |
| dc1-leaf1b | System | VerifyReloadCause | Verifies the last reload cause of the device. | ✅&nbsp;Success | - |
| dc1-leaf1b | VXLAN | VerifyVxlanConfigSanity | Verifies there are no VXLAN config-sanity inconsistencies. | ✅&nbsp;Success | - |
| dc1-leaf2a | BGP | VerifyBGPPeerSession | Verifies the session state of BGP peers. | ✅&nbsp;Success | - |
| dc1-leaf2a | Configuration | VerifyZeroTouch | Verifies ZeroTouch is disabled. | ✅&nbsp;Success | - |
| dc1-leaf2a | Connectivity | VerifyLLDPNeighbors | Verifies the connection status of the specified LLDP (Link Layer Discovery Protocol) neighbors. | ✅&nbsp;Success | - |
| dc1-leaf2a | Connectivity | VerifyReachability | Verifies point-to-point reachability between Ethernet interfaces. | ✅&nbsp;Success | - |
| dc1-leaf2a | Interfaces | VerifyIllegalLACP | Verifies there are no illegal LACP packets in port channels. | ✅&nbsp;Success | - |
| dc1-leaf2a | Interfaces | VerifyInterfaceDiscards | Verifies that the interfaces packet discard counters are equal to zero. | ✅&nbsp;Success | - |
| dc1-leaf2a | Interfaces | VerifyInterfaceErrDisabled | Verifies there are no interfaces in the errdisabled state. | ✅&nbsp;Success | - |
| dc1-leaf2a | Interfaces | VerifyInterfaceErrors | Verifies that the interfaces error counters are equal to zero. | ✅&nbsp;Success | - |
| dc1-leaf2a | Interfaces | VerifyInterfaceUtilization | Verifies that the utilization of interfaces is below a certain threshold. | ✅&nbsp;Success | - |
| dc1-leaf2a | MLAG | VerifyMlagConfigSanity | Verifies there are no MLAG config-sanity inconsistencies. | ✅&nbsp;Success | - |
| dc1-leaf2a | MLAG | VerifyMlagStatus | Verifies the health status of the MLAG configuration. | ✅&nbsp;Success | - |
| dc1-leaf2a | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | ✅&nbsp;Success | - |
| dc1-leaf2a | STP | VerifySTPCounters | Verifies there is no errors in STP BPDU packets. | ✅&nbsp;Success | - |
| dc1-leaf2a | System | VerifyAgentLogs | Verifies there are no agent crash reports. | ✅&nbsp;Success | - |
| dc1-leaf2a | System | VerifyCoredump | Verifies there are no core dump files. | ✅&nbsp;Success | - |
| dc1-leaf2a | System | VerifyFileSystemUtilization | Verifies that no partition is utilizing more than 75% of its disk space. | ✅&nbsp;Success | - |
| dc1-leaf2a | System | VerifyMaintenance | Verifies that the device is not currently under or entering maintenance. | ✅&nbsp;Success | - |
| dc1-leaf2a | System | VerifyMemoryUtilization | Verifies whether the memory utilization is below 75%. | ✅&nbsp;Success | - |
| dc1-leaf2a | System | VerifyReloadCause | Verifies the last reload cause of the device. | ✅&nbsp;Success | - |
| dc1-leaf2a | VXLAN | VerifyVxlanConfigSanity | Verifies there are no VXLAN config-sanity inconsistencies. | ✅&nbsp;Success | - |
| dc1-leaf2b | BGP | VerifyBGPPeerSession | Verifies the session state of BGP peers. | ✅&nbsp;Success | - |
| dc1-leaf2b | Configuration | VerifyZeroTouch | Verifies ZeroTouch is disabled. | ✅&nbsp;Success | - |
| dc1-leaf2b | Connectivity | VerifyLLDPNeighbors | Verifies the connection status of the specified LLDP (Link Layer Discovery Protocol) neighbors. | ✅&nbsp;Success | - |
| dc1-leaf2b | Connectivity | VerifyReachability | Verifies point-to-point reachability between Ethernet interfaces. | ✅&nbsp;Success | - |
| dc1-leaf2b | Interfaces | VerifyIllegalLACP | Verifies there are no illegal LACP packets in port channels. | ✅&nbsp;Success | - |
| dc1-leaf2b | Interfaces | VerifyInterfaceDiscards | Verifies that the interfaces packet discard counters are equal to zero. | ✅&nbsp;Success | - |
| dc1-leaf2b | Interfaces | VerifyInterfaceErrDisabled | Verifies there are no interfaces in the errdisabled state. | ✅&nbsp;Success | - |
| dc1-leaf2b | Interfaces | VerifyInterfaceErrors | Verifies that the interfaces error counters are equal to zero. | ✅&nbsp;Success | - |
| dc1-leaf2b | Interfaces | VerifyInterfaceUtilization | Verifies that the utilization of interfaces is below a certain threshold. | ✅&nbsp;Success | - |
| dc1-leaf2b | MLAG | VerifyMlagConfigSanity | Verifies there are no MLAG config-sanity inconsistencies. | ✅&nbsp;Success | - |
| dc1-leaf2b | MLAG | VerifyMlagStatus | Verifies the health status of the MLAG configuration. | ✅&nbsp;Success | - |
| dc1-leaf2b | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | ✅&nbsp;Success | - |
| dc1-leaf2b | STP | VerifySTPCounters | Verifies there is no errors in STP BPDU packets. | ✅&nbsp;Success | - |
| dc1-leaf2b | System | VerifyAgentLogs | Verifies there are no agent crash reports. | ✅&nbsp;Success | - |
| dc1-leaf2b | System | VerifyCoredump | Verifies there are no core dump files. | ✅&nbsp;Success | - |
| dc1-leaf2b | System | VerifyFileSystemUtilization | Verifies that no partition is utilizing more than 75% of its disk space. | ✅&nbsp;Success | - |
| dc1-leaf2b | System | VerifyMaintenance | Verifies that the device is not currently under or entering maintenance. | ✅&nbsp;Success | - |
| dc1-leaf2b | System | VerifyMemoryUtilization | Verifies whether the memory utilization is below 75%. | ✅&nbsp;Success | - |
| dc1-leaf2b | System | VerifyReloadCause | Verifies the last reload cause of the device. | ✅&nbsp;Success | - |
| dc1-leaf2b | VXLAN | VerifyVxlanConfigSanity | Verifies there are no VXLAN config-sanity inconsistencies. | ✅&nbsp;Success | - |
| dc1-leaf3a | BGP | VerifyBGPPeerSession | Verifies the session state of BGP peers. | ✅&nbsp;Success | - |
| dc1-leaf3a | Configuration | VerifyZeroTouch | Verifies ZeroTouch is disabled. | ✅&nbsp;Success | - |
| dc1-leaf3a | Connectivity | VerifyLLDPNeighbors | Verifies the connection status of the specified LLDP (Link Layer Discovery Protocol) neighbors. | ✅&nbsp;Success | - |
| dc1-leaf3a | Connectivity | VerifyReachability | Verifies point-to-point reachability between Ethernet interfaces. | ✅&nbsp;Success | - |
| dc1-leaf3a | Interfaces | VerifyIllegalLACP | Verifies there are no illegal LACP packets in port channels. | ✅&nbsp;Success | - |
| dc1-leaf3a | Interfaces | VerifyInterfaceDiscards | Verifies that the interfaces packet discard counters are equal to zero. | ✅&nbsp;Success | - |
| dc1-leaf3a | Interfaces | VerifyInterfaceErrDisabled | Verifies there are no interfaces in the errdisabled state. | ✅&nbsp;Success | - |
| dc1-leaf3a | Interfaces | VerifyInterfaceErrors | Verifies that the interfaces error counters are equal to zero. | ✅&nbsp;Success | - |
| dc1-leaf3a | Interfaces | VerifyInterfaceUtilization | Verifies that the utilization of interfaces is below a certain threshold. | ✅&nbsp;Success | - |
| dc1-leaf3a | Interfaces | VerifyInterfacesStatus | Verifies the operational states of specified interfaces to ensure they match expected configurations. | ✅&nbsp;Success | - |
| dc1-leaf3a | Interfaces | VerifyPortChannels | Verifies there are no inactive ports in port channels. | ✅&nbsp;Success | - |
| dc1-leaf3a | MLAG | VerifyMlagConfigSanity | Verifies there are no MLAG config-sanity inconsistencies. | ✅&nbsp;Success | - |
| dc1-leaf3a | MLAG | VerifyMlagInterfaces | Verifies there are no inactive or active-partial MLAG ports. | ✅&nbsp;Success | - |
| dc1-leaf3a | MLAG | VerifyMlagStatus | Verifies the health status of the MLAG configuration. | ✅&nbsp;Success | - |
| dc1-leaf3a | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | ✅&nbsp;Success | - |
| dc1-leaf3a | STP | VerifySTPCounters | Verifies there is no errors in STP BPDU packets. | ✅&nbsp;Success | - |
| dc1-leaf3a | System | VerifyAgentLogs | Verifies there are no agent crash reports. | ✅&nbsp;Success | - |
| dc1-leaf3a | System | VerifyCoredump | Verifies there are no core dump files. | ✅&nbsp;Success | - |
| dc1-leaf3a | System | VerifyFileSystemUtilization | Verifies that no partition is utilizing more than 75% of its disk space. | ✅&nbsp;Success | - |
| dc1-leaf3a | System | VerifyMaintenance | Verifies that the device is not currently under or entering maintenance. | ✅&nbsp;Success | - |
| dc1-leaf3a | System | VerifyMemoryUtilization | Verifies whether the memory utilization is below 75%. | ✅&nbsp;Success | - |
| dc1-leaf3a | System | VerifyReloadCause | Verifies the last reload cause of the device. | ✅&nbsp;Success | - |
| dc1-leaf3a | VXLAN | VerifyVxlanConfigSanity | Verifies there are no VXLAN config-sanity inconsistencies. | ✅&nbsp;Success | - |
| dc1-leaf3b | BGP | VerifyBGPPeerSession | Verifies the session state of BGP peers. | ✅&nbsp;Success | - |
| dc1-leaf3b | Configuration | VerifyZeroTouch | Verifies ZeroTouch is disabled. | ✅&nbsp;Success | - |
| dc1-leaf3b | Connectivity | VerifyLLDPNeighbors | Verifies the connection status of the specified LLDP (Link Layer Discovery Protocol) neighbors. | ✅&nbsp;Success | - |
| dc1-leaf3b | Connectivity | VerifyReachability | Verifies point-to-point reachability between Ethernet interfaces. | ✅&nbsp;Success | - |
| dc1-leaf3b | Interfaces | VerifyIllegalLACP | Verifies there are no illegal LACP packets in port channels. | ✅&nbsp;Success | - |
| dc1-leaf3b | Interfaces | VerifyInterfaceDiscards | Verifies that the interfaces packet discard counters are equal to zero. | ✅&nbsp;Success | - |
| dc1-leaf3b | Interfaces | VerifyInterfaceErrDisabled | Verifies there are no interfaces in the errdisabled state. | ✅&nbsp;Success | - |
| dc1-leaf3b | Interfaces | VerifyInterfaceErrors | Verifies that the interfaces error counters are equal to zero. | ✅&nbsp;Success | - |
| dc1-leaf3b | Interfaces | VerifyInterfaceUtilization | Verifies that the utilization of interfaces is below a certain threshold. | ✅&nbsp;Success | - |
| dc1-leaf3b | Interfaces | VerifyInterfacesStatus | Verifies the operational states of specified interfaces to ensure they match expected configurations. | ✅&nbsp;Success | - |
| dc1-leaf3b | Interfaces | VerifyPortChannels | Verifies there are no inactive ports in port channels. | ✅&nbsp;Success | - |
| dc1-leaf3b | MLAG | VerifyMlagConfigSanity | Verifies there are no MLAG config-sanity inconsistencies. | ✅&nbsp;Success | - |
| dc1-leaf3b | MLAG | VerifyMlagInterfaces | Verifies there are no inactive or active-partial MLAG ports. | ✅&nbsp;Success | - |
| dc1-leaf3b | MLAG | VerifyMlagStatus | Verifies the health status of the MLAG configuration. | ✅&nbsp;Success | - |
| dc1-leaf3b | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | ✅&nbsp;Success | - |
| dc1-leaf3b | STP | VerifySTPCounters | Verifies there is no errors in STP BPDU packets. | ✅&nbsp;Success | - |
| dc1-leaf3b | System | VerifyAgentLogs | Verifies there are no agent crash reports. | ✅&nbsp;Success | - |
| dc1-leaf3b | System | VerifyCoredump | Verifies there are no core dump files. | ✅&nbsp;Success | - |
| dc1-leaf3b | System | VerifyFileSystemUtilization | Verifies that no partition is utilizing more than 75% of its disk space. | ✅&nbsp;Success | - |
| dc1-leaf3b | System | VerifyMaintenance | Verifies that the device is not currently under or entering maintenance. | ✅&nbsp;Success | - |
| dc1-leaf3b | System | VerifyMemoryUtilization | Verifies whether the memory utilization is below 75%. | ✅&nbsp;Success | - |
| dc1-leaf3b | System | VerifyReloadCause | Verifies the last reload cause of the device. | ✅&nbsp;Success | - |
| dc1-leaf3b | VXLAN | VerifyVxlanConfigSanity | Verifies there are no VXLAN config-sanity inconsistencies. | ✅&nbsp;Success | - |
| dc1-spine1 | BGP | VerifyBGPPeerSession | Verifies the session state of BGP peers. | ✅&nbsp;Success | - |
| dc1-spine1 | Configuration | VerifyRunningConfigDiffs | Verifies there is no difference between the running-config and the startup-config. | ✅&nbsp;Success | - |
| dc1-spine1 | Configuration | VerifyZeroTouch | Verifies ZeroTouch is disabled. | ✅&nbsp;Success | - |
| dc1-spine1 | Connectivity | VerifyLLDPNeighbors | Verifies the connection status of the specified LLDP (Link Layer Discovery Protocol) neighbors. | ✅&nbsp;Success | - |
| dc1-spine1 | Connectivity | VerifyReachability | Verifies point-to-point reachability between Ethernet interfaces. | ✅&nbsp;Success | - |
| dc1-spine1 | Interfaces | VerifyInterfaceDiscards | Verifies that the interfaces packet discard counters are equal to zero. | ✅&nbsp;Success | - |
| dc1-spine1 | Interfaces | VerifyInterfaceErrDisabled | Verifies there are no interfaces in the errdisabled state. | ✅&nbsp;Success | - |
| dc1-spine1 | Interfaces | VerifyInterfaceErrors | Verifies that the interfaces error counters are equal to zero. | ✅&nbsp;Success | - |
| dc1-spine1 | Interfaces | VerifyInterfaceUtilization | Verifies that the utilization of interfaces is below a certain threshold. | ✅&nbsp;Success | - |
| dc1-spine1 | Interfaces | VerifyInterfacesStatus | Verifies the operational states of specified interfaces to ensure they match expected configurations. | ✅&nbsp;Success | - |
| dc1-spine1 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | ✅&nbsp;Success | - |
| dc1-spine1 | STP | VerifySTPCounters | Verifies there is no errors in STP BPDU packets. | ✅&nbsp;Success | - |
| dc1-spine1 | System | VerifyAgentLogs | Verifies there are no agent crash reports. | ✅&nbsp;Success | - |
| dc1-spine1 | System | VerifyCoredump | Verifies there are no core dump files. | ✅&nbsp;Success | - |
| dc1-spine1 | System | VerifyFileSystemUtilization | Verifies that no partition is utilizing more than 75% of its disk space. | ✅&nbsp;Success | - |
| dc1-spine1 | System | VerifyMaintenance | Verifies that the device is not currently under or entering maintenance. | ✅&nbsp;Success | - |
| dc1-spine1 | System | VerifyMemoryUtilization | Verifies whether the memory utilization is below 75%. | ✅&nbsp;Success | - |
| dc1-spine1 | System | VerifyReloadCause | Verifies the last reload cause of the device. | ✅&nbsp;Success | - |
| dc1-spine2 | BGP | VerifyBGPPeerSession | Verifies the session state of BGP peers. | ✅&nbsp;Success | - |
| dc1-spine2 | Configuration | VerifyRunningConfigDiffs | Verifies there is no difference between the running-config and the startup-config. | ✅&nbsp;Success | - |
| dc1-spine2 | Configuration | VerifyZeroTouch | Verifies ZeroTouch is disabled. | ✅&nbsp;Success | - |
| dc1-spine2 | Connectivity | VerifyLLDPNeighbors | Verifies the connection status of the specified LLDP (Link Layer Discovery Protocol) neighbors. | ✅&nbsp;Success | - |
| dc1-spine2 | Connectivity | VerifyReachability | Verifies point-to-point reachability between Ethernet interfaces. | ✅&nbsp;Success | - |
| dc1-spine2 | Interfaces | VerifyInterfaceDiscards | Verifies that the interfaces packet discard counters are equal to zero. | ✅&nbsp;Success | - |
| dc1-spine2 | Interfaces | VerifyInterfaceErrDisabled | Verifies there are no interfaces in the errdisabled state. | ✅&nbsp;Success | - |
| dc1-spine2 | Interfaces | VerifyInterfaceErrors | Verifies that the interfaces error counters are equal to zero. | ✅&nbsp;Success | - |
| dc1-spine2 | Interfaces | VerifyInterfaceUtilization | Verifies that the utilization of interfaces is below a certain threshold. | ✅&nbsp;Success | - |
| dc1-spine2 | Interfaces | VerifyInterfacesStatus | Verifies the operational states of specified interfaces to ensure they match expected configurations. | ✅&nbsp;Success | - |
| dc1-spine2 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | ✅&nbsp;Success | - |
| dc1-spine2 | STP | VerifySTPCounters | Verifies there is no errors in STP BPDU packets. | ✅&nbsp;Success | - |
| dc1-spine2 | System | VerifyAgentLogs | Verifies there are no agent crash reports. | ✅&nbsp;Success | - |
| dc1-spine2 | System | VerifyCoredump | Verifies there are no core dump files. | ✅&nbsp;Success | - |
| dc1-spine2 | System | VerifyFileSystemUtilization | Verifies that no partition is utilizing more than 75% of its disk space. | ✅&nbsp;Success | - |
| dc1-spine2 | System | VerifyMaintenance | Verifies that the device is not currently under or entering maintenance. | ✅&nbsp;Success | - |
| dc1-spine2 | System | VerifyMemoryUtilization | Verifies whether the memory utilization is below 75%. | ✅&nbsp;Success | - |
| dc1-spine2 | System | VerifyReloadCause | Verifies the last reload cause of the device. | ✅&nbsp;Success | - |
