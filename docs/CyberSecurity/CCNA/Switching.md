---
sidebar_position: 7
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
import Highlight from '@site/src/components/Highlight';

# Switching



### **What is a Switch?**
- A switch is a network device operating at Layer 2 (Data Link Layer) of the OSI model But the tech advance and now we have L3 Switches.
- It is designed to connect devices within the same local network, such as computers, printers, and other networked devices.
- Switches use MAC addresses to make forwarding decisions.

### **Ethernet Frame Basics:**
- An Ethernet frame is a packet that includes an Ethernet header and a trailer.
- The minimum frame size is 64 bytes, including the header, packet, and trailer.
- The Ethernet header includes fields like the destination MAC address, source MAC address, Type, etc.
- The Frame Check Sequence (FCS) is used for error detection.

### **MAC Addresses:**
- MAC addresses are hardware addresses uniquely identifying network interfaces.
- They are written as 12 hexadecimal characters.
- The first 3 bytes represent the Organizationally Unique Identifier (OUI), and the last 3 bytes are unique to the device.

### **Switch Functions:**
1. **Address Learning:** Switches learn MAC addresses by observing the source MAC address of incoming frames. They build and maintain a MAC address table.
2. **Forwarding Messages:** Switches use the MAC address table to make forwarding decisions. They forward frames only to the appropriate destination port.
3. **Loop Avoidance:** Switches use the Spanning Tree Protocol (STP) to prevent network loops, which can cause broadcast storms and network instability.

### **Why Switches Are Essential:**
- Switches provide efficient and fast data forwarding within LANs, reducing network congestion and improving performance.
- They enable devices to communicate directly with each other, minimizing unnecessary network traffic.
- Switches allow the segmentation of LANs into VLANs (Virtual LANs), improving network security and management.
- By learning MAC addresses, switches create efficient paths for data transmission, reducing broadcast domains.
- STP ensures network reliability by preventing loops and redundant paths.


## **Initials Configurations**

| Step                                | Description                                                                                                                                                                 |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1. Power Up the Devices             | Ensure all network devices are powered on and operational.                                                                                                                  |
| 2. Connect to the Device via Console | Use terminal emulation software (e.g., PuTTY or SecureCRT) to establish a console connection to the network switch through the COM port.                                       |
| 3. Privilege Levels                  | By default, users may have privilege level 0, requiring a username and password for access.                                                                                |
| 4. Enable Mode                       | Enter enable mode (user/enable mode) using the "enable" command to gain elevated privileges.                                                                                 |
| 5. Interface Information             | - To view all interfaces and their status: use the "show ip interface brief" command. - To view details of a specific interface: use `show ip interface <interface>`    |
| 6. Configuration Mode                | Enter global configuration mode using commands like "configure terminal" or "conf t." This mode provides full access with privilege level 15.                              |
| 7. Using "do" with Commands          | While in configuration mode, you can use show commands by prefixing them with "do," such as "do show ip int brief."                                                        |
| 8. Interface Configuration           | Configure interface settings (e.g., speed, duplex, description) using commands like: - `interface <interface>` - `speed <speed>` - `duplex <duplex>` - `description <description>` |
| 9. Selecting Multiple Interfaces     | Use the "interface range" command to select and configure multiple interfaces simultaneously.                                                                                    |
| 10. Set Switch Hostname              | Assign a name to the switch using the `hostname <name>` command.                                                                                                                |
| 11. Banner Message                   | Create a banner message that users see when they log in.                                                                                                                        |
| 12. Console Password                 | Set a password for console access using the "line console 0" command.                                                                                                             |
| 13. Enable Telnet                    | Configure virtual lines (vty) for Telnet access.                                                                                                                                |
| 14. Management IP Address            | Assign an IP address to the management interface (usually VLAN 1).                                                                                                               |
| 15. Set Passwords                    | Set an enable secret password for privileged mode.                                                                                                                        |
| 16. Set Default Gateway              | Configure the default gateway.                                                                                                                                          |
| 17. Clear Configurations             | To delete all configurations, use the "write erase" command.                                                                                                                |
| 18. Disable DNS Lookup               | Use "no ip domain lookup" to disable DNS lookups.                                                                                                                         |
| 19. Enable IP Routing (L3 Switch)    | Configure IP routing on Layer 3 switches.                                                                                                                               |
| 20. Save Configurations              | Save configurations to memory or copy them to a TFTP server.                                                                                                               |
| 21. Check Interface Configurations    | Use "show run" to view running configurations.                                                                                                                           |
| 22. Check Time                        | View the switch's current time with "show clock."                                                                                                                        |
| 23. Change Time                      | Set the time with the "clock set" command.                                                                                                                                |
| 24. Change Timezone                  | Configure the timezone using "clock timezone."                                                                                                                            |
| 25. Interface Shutdown/No Shutdown    | Use "shutdown" and "no shutdown" to disable/enable an interface.                                                                                                           |
| 26. Interface Access Mode            | Set an interface to access mode with "switchport mode access."                                                                                                             |
| 27. Interface Trunk Mode             | Set an interface to trunk mode with "switchport mode trunk."                                                                                                              |
| 28. DTP Modes                        | Configure Dynamic Trunking Protocol (DTP) modes.                                                                                                                           |
| 29. Check ARP Table                  | View the Address Resolution Protocol (ARP) table with "show ip arp."                                                                                                       |
| 30. Encapsulation                    | Configure encapsulation for interfaces using "switchport trunk encapsulation dot1q."                                                                                     |


## **VLAN**
### **Virtual Local Area**


| Topic                                   | Description                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **What is VLAN (Virtual Local Area Network)?** | VLAN, or Virtual Local Area Network, enhances network security by creating virtual partitions within a network. It isolates and segregates network traffic, making it act as a virtual wall between different parts of a network.                                                                 |
| **Why Use VLANs?**                     | VLANs are used to improve network security and organization. They help segment a network into isolated parts, allowing different departments or groups to share the same network infrastructure while keeping their data separate and secure.                               |
| **Inter-Switch Link (ISL)**             | **IEEE 802.1Q (Dot1q)**                                                                                                                                                                                                                       |
| **Protocol Type**                      | Cisco Proprietary                                                                                                                                                                                                                                | Industry Standard                                                                                                                                                                                                                                      |
| **Header Modification**                | Adds a proprietary 26-byte header to Ethernet frames, containing VLAN information.                                                                                                                                                                | Inserts a 4-byte VLAN tag into the original Ethernet frame.                                                                                                                                                                                             |
| **Compatibility**                      | Primarily used within Cisco environments; not compatible with non-Cisco devices.                                                                                                                                                                  | Widely supported across various network vendors, promoting interoperability.                                                                                                                                                                             |
| **Supported VLANs**                    | Supports up to 1000 VLANs, suitable for large-scale networks.                                                                                                                                                                                      | Supports up to 4096 VLANs, more than sufficient for most network environments.                                                                                                                                                                          |
| **Native VLAN**                        | Does not support a concept of a native VLAN. All VLAN information is included in the header.                                                                                                                                                      | Supports the concept of a native VLAN, an untagged VLAN on a trunk link for easier interoperability with non-trunk-aware devices.                                                                                                                                 |
| **Tagging Process**                    | VLAN tagging occurs with the addition of a proprietary header at Layer 2.                                                                                                                                                                          | VLAN tagging occurs at Layer 2 with the insertion of a 4-byte VLAN tag into the frame's header.                                                                                                                                                          |
| **Dynamic Trunking Protocol (DTP)**     | **Three DTP modes**: Auto, Desirable, No Negotiate. Auto waits for commands from the other switch, Desirable initiates trunking, No Negotiate disables DTP.                                                                                                                                                 |




## **VTP**

| **VTP (VLAN Trunking Protocol)** | **Description**                                                                                                                                                                         |
|-----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Purpose**                        | Simplifies VLAN configuration in networks with multiple switches by allowing one switch to configure VLANs and share that configuration with others.                                           |
| **VTP Server Mode**                | - Default mode for all switches. - Can create, modify, and delete VLANs.                                                                                                                |
| **VTP Client Mode**                | - Cannot create or modify VLANs. - Receives VLAN information from VTP Servers.                                                                                                           |
| **VTP Transparent Mode**           | - Does not store VLAN information locally. - Passes VTP Server's VLAN configurations to connected switches.                                                                              |
| **Configuration (Server Mode)**    | - Set switch as a VTP Server: `vtp mode server` - Define VTP domain: `vtp domain Shadow` - Set VTP password: `vtp password ShadowGuardain`                                                 |
| **Configuration (Client Mode)**    | - Set switch as a VTP Client: `vtp mode client` - Specify VTP domain: `vtp domain Shadow` - Set VTP password: `vtp password ShadowGuardain`                                             |

This table provides an overview of VTP and its different modes, along with the basic configuration steps for setting up a switch as either a VTP Server or a VTP Client.

## EtherChannel:

EtherChannel is a method used for link aggregation and redundancy in network configurations. It operates under the IEEE 802.1ad standard and combines multiple Ethernet links into a single logical link. This provides increased bandwidth, load balancing, and fault tolerance.

**Conditions for EtherChannel:**
- The switch must support IEEE 802.1ad.
- All cables in the EtherChannel bundle must have the same speed; mixing different cable speeds is not supported.

**LACP (Link Aggregation Control Protocol):**
- LACP stands for Link Aggregation Control Protocol, which is used to establish and manage EtherChannels.
- LACP enables the combination of multiple network connections in parallel, improving performance and redundancy.

### **LACP Modes:**

<Tabs>
  <TabItem value="Active" label="Active" >
    In this mode, a device actively sends LACPDU (Link Aggregation Control Protocol Data Unit) packets to check if there are devices connected to the adjacent ports. If both sides detect each other, they establish a connection.
  </TabItem>
  <TabItem value="Passive" label="Passive">
   In passive mode, a device waits to receive LACPDU packets from the adjacent ports. It accepts the connection if it receives the appropriate LACPDU packet from the other side. If both devices are in passive mode, they will wait for LACPDU packets, and no connection will be formed until one side changes its mode.
  </TabItem>
  <TabItem value="*ON (Open)" label="*ON (Open)">
    The ON mode, also known as static mode, is a configuration where a connection is open without any negotiation. Both devices need to be in the ON mode for a connection to be established.
  </TabItem>
</Tabs>


**PAGP (Port Aggregation Group Protocol):**
- PAGP, or Port Aggregation Group Protocol, is a Cisco-proprietary protocol used for link aggregation, similar to LACP.
- It is supported exclusively on Cisco devices.

### **PAGP Modes:**

<Tabs>
  <TabItem value="Auto" label="Auto" >
    The Auto mode in PAGP is similar to the passive mode in LACP. It waits for negotiation packets from the other end.
  </TabItem>
  <TabItem value="Desirable" label="Desirable">
   The Desirable mode in PAGP is comparable to the active mode in LACP. It initiates negotiation with the other end.
  </TabItem>
 </Tabs>


**Configuration for EtherChannel (Switch & Router):**

**Switch Configuration:**
1. `interface range fastethernet 0/1-2, ethernet 0/3` - Select the range of interfaces to bundle.
2. `no shutdown` - Enable the selected interfaces.
3. `channel-group [number] mode [active, passive, on]` - Create an EtherChannel group with a specific mode.
4. `exit` - Exit interface configuration mode.
5. `show interface port channel [number]` - Display information about the created EtherChannel.

**For Switch (Additional Configuration):**
6. `switchport mode access` or `switchport mode trunk encapsulation dot1q` - Set the interface mode to access or trunk.
7. `switchport mode trunk` - Enable trunking on the interface.

**For Router (Additional Configuration):**
8. `IP address [ip-address] [subnet]` - Assign an IP address to the interface.

:::note
These configurations enable EtherChannel and LACP/PAGP on network devices, providing benefits like increased bandwidth, load balancing, and redundancy.
:::



| **EtherChannel and LACP/PAGP**       | **Description**                                                                                                                                                             |
|--------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **EtherChannel Methods**             | IEEE 802.1ad is used for EtherChannel.                                                                                                                                        |
| **Conditions for EtherChannel**       | - The switch must support IEEE 802.1ad. - All cables in the bundle must have the same speed; different cable speeds cannot be bundled.                                       |
| **LACP (Link Aggregation Control Protocol)** | - Combines multiple network connections in parallel. - Three LACP Modes:   - **Active:** Sends LACPDU to check for connected devices.   - **Passive:** Waits for active packets to establish a connection.   - **On (Open):** Connection is open, no negotiation; also called static mode. |
| **PAGP (Port Aggregation Group Protocol)** | - Supports only Cisco devices. - Two Modes:   - **Auto:** Similar to Passive in LACP, waits for negotiation.   - **Desirable:** Similar to Active in LACP, initiates negotiation.                                |
| **Configuration (Switch & Router)**   | **Switch Configuration:** - `interface range fastethernet 0/1-2 , ethernet 0/3` - `no shutdown` - `channel-group [number] mode [active, passive, on]` - `exit` - `show interface port channel [number]` - **Switch:** - `switchport mode access` or `switchport mode trunk encapsulation dot1q` - `switchport mode trunk` - **Router Configuration:** - `ip address [ip-address] [subnet]` |


## **CDP & LLDP**

**CDP (Cisco Discovery Protocol) and LLDP (Link Layer Discovery Protocol):**

CDP (Cisco Discovery Protocol) and LLDP (Link Layer Discovery Protocol) are network discovery protocols that operate at Layer 2 of the OSI model. They are used to discover information about directly connected devices in a network. While CDP is a Cisco-proprietary protocol, LLDP is an open standard defined by the IEEE.

**CDP (Cisco Discovery Protocol):**
- CDP is developed by Cisco and is primarily used in Cisco networking environments.
- It operates at Layer 2 and allows Cisco devices to discover and learn information about neighboring Cisco devices.
- CDP is used to gather information such as the device type, device name, and IP address of directly connected Cisco devices.

**LLDP (Link Layer Discovery Protocol):**
- LLDP is an open standard protocol defined by the IEEE (802.1AB) and is supported by a wide range of network vendors, not limited to Cisco.
- Like CDP, LLDP operates at Layer 2 and enables devices to exchange information about their identity and capabilities with neighboring devices.
- LLDP is used to discover details such as system name, system description, port identifier, and more.

**Configuration for CDP and LLDP:**

**To Enable LLDP:**
- Enter the global configuration mode on a network device.
- Use the command `lldp run` to enable LLDP globally on the device.
- You can then use commands like `show lldp neighbors` and `show lldp details` to view LLDP information.

**To Enable CDP:**
- Enter the global configuration mode on a Cisco network device.
- Use the command `cdp run` to enable CDP globally on the device.
- To view CDP information, you can use the `show cdp neighbors` command.

:::note
These protocols help network administrators discover and understand the topology of their networks by providing information about directly connected devices. 
:::