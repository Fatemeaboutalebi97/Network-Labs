# University-Network-Lab
University network with Cisco Packet Tracer

Project Overview
This project was developed using Cisco Packet Tracer as part of a university networking project.
 This university is a large university with two campuses located 20 miles apart. Students and staff are distributed across four faculties: Health and Science; Business; Engineering/Computer Science; and Arts/Design. Each staff member has a personal computer, while students have access to computers in the laboratories, There is also a mail server that is externally hosted in the cloud. 
The main goal of this project is to design and configure a network using fundamental CCNA networking concepts, including IPv4 addressing, subnetting, VLANs, trunking, inter-VLAN routing, DHCP, serial communication, and dynamic routing with RIPv2.

Technologies and Networking Concepts

The following concepts and technologies were implemented in this project:
1.	  IPv4 Addressing
2.	  Subnetting
3.	  VLAN
4.	  Access Ports
5.	  Trunk Ports
6.	  Inter-VLAN Routing
7.	  Router Subinterfaces
8.	  802.1Q Encapsulation
9.	  DHCP
10.	  Serial Interfaces
11.	  Clock Rate
12.	  RIPv2 (Routing Information Protocol Version 2)
13.	  Basic Cisco IOS Configuration

Configuration Overview

1. IPv4 Addressing and Subnetting

IPv4 addresses and subnet masks were configured for routers and network devices. Subnetting was used to divide the network into appropriate IP networks and provide efficient address allocation.
Example:
```cisco
int gig0/0.90
encapsulation dot1Q 90
ip add 192.168.9.1 255.255.255.0
```

2. VLAN Configuration

VLANs were configured to logically separate different network segments. Access ports were assigned to the appropriate VLANs, allowing connected end devices to communicate within their designated VLAN.
Example:
```cisco
En
Conf t
int range fa0/1-24
switchport mode acc
switchport acc vlan 10
do wr
```

3. Trunk Ports

Trunking was configured between network devices to carry traffic from multiple VLANs over a single link.
Example:
```cisco
int gig1/0/1
switchport mode trunk 
```

4. Router Subinterfaces

Subinterfaces were configured on the router's GigabitEthernet interface.
Example:
```cisco
int gig0/0.90
encapsulation dot1Q 90
ip add 192.168.9.1 255.255.255.0
```

5. DHCP Configuration

A DHCP pool was configured on the router to automatically assign IP addresses to clients.
Example:
```cisco
service dhcp
ip dhcp pool Staff-pool
network 192.168.9.0 255.255.255.0
default-router 192.168.9.1
dns-server 192.168.9.1
```

6. RIPv2

RIPv2 was configured as the dynamic routing protocol to allow routers to exchange routing information.
Example:
```cisco
router rip
version 2
network 192.168.9.0
network 192.168.10.0
network 10.10.10.0
```

7. Access Ports

Switch interfaces connected to end devices were configured as access ports.

8. Inter-VLAN Routing

Inter-VLAN communication was implemented using router subinterfaces.
This allows devices in different VLANs to communicate through the router.

9. 802.1Q Encapsulation

IEEE 802.1Q encapsulation was used on router subinterfaces to identify VLAN traffic across trunk links.

10. Serial Interfaces

Serial interfaces were configured to establish communication between routers.

11. Clock Rate

A clock rate was configured on the appropriate serial interface to provide clocking for the serial connection.
Example:
```cisco
Router(config)# interface se0/1/1
Router(config-if)# clock rate 64000
```

12. Basic Cisco IOS Configuration

Basic Cisco IOS commands were used throughout the project for device configuration and management.
Examples include:
```cisco
enable
configure terminal
interface
no shutdown
do write
```

Verification

The network configuration can be verified using Cisco IOS commands such as:
```cisco
show ip interface brief
show ip route
show vlan brief
show interfaces trunk
show running-config
```

Project File

The main Cisco Packet Tracer project file is:
CCNA-Network-Project.pkt
The .pkt file contains the complete network topology and device configurations created in Cisco Packet Tracer.

Troubleshooting

When I configured the RIP protocol, I encountered the following error while testing the connection with a ping:
`Destination host unreachable.`
After reviewing the commands again, I realized that the following command had not been entered on the main-campus router:
`Router(config-router)#version 2`

Learning Outcomes

Through this project, I gained practical experience with:
•	IPv4 addressing and subnetting
•	VLAN configuration
•	Access and trunk ports
•	Inter-VLAN routing
•	Router-on-a-Stick configuration
•	802.1Q encapsulation
•	DHCP configuration
•	Serial router connections
•	RIPv2 dynamic routing
•	Basic Cisco IOS commands
•	Network troubleshooting and connectivity testing

Tools
•	Cisco Packet Tracer

Author

[Fateme Aboutalebi](https://github.com/Fatemeaboutalebi97)

CCNA / Networking Student



