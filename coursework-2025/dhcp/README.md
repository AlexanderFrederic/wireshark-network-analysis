DHCP Packet Analysis

Overview

This section documents my analysis of DHCP traffic using Wireshark. The lab focused on how a client obtains network configuration information from a DHCP server and how DHCP messages can be identified and compared through packet fields.

DHCP Analysis

During the analysis, I examined DHCP messages and identified information including:

* Source and destination IP addresses
* UDP source and destination ports
* Transaction IDs
* Requested configuration options
* Assigned client IP address
* Lease time
* Router address
* DNS and other network configuration information

Client Discovery

The DHCP client initially used the source address 0.0.0.0 because it had not yet been assigned an IP address. The destination address was 255.255.255.255, allowing the message to be broadcast across the local network so that available DHCP servers could receive it.

The analyzed DHCP traffic used UDP. Client messages used source port 68 and destination port 67 when communicating with the DHCP server.

Transaction Identification

I used the DHCP transaction ID to associate messages belonging to the same address assignment process. The DHCP Discover and DHCP Offer shared the transaction ID 0x56f415ed, showing that the Offer was sent in response to that Discover message.

The DHCP Request also used the same transaction ID, allowing the messages from the exchange to be connected during packet analysis.

Address Assignment and Configuration

The DHCP server used the address 192.168.86.1, while the client was assigned 192.168.86.65. The analyzed configuration included a lease time of 1 day (86400 seconds) and a router address of 192.168.86.1.

The DHCP messages also contained requested or supplied network configuration information such as:

* Subnet mask
* Router
* Domain name
* Domain search
* Domain name server
* Broadcast address

Key Takeaways

This lab helped me understand how DHCP dynamically provides network configuration to clients and how Wireshark can be used to follow related DHCP messages. Examining addresses, ports, transaction IDs, and configuration options provided practical experience identifying the different stages of DHCP communication and troubleshooting address assignment behavior.

Skills Demonstrated

* Wireshark packet analysis
* DHCP fundamentals
* UDP port identification
* Broadcast and unicast analysis
* IP address assignment analysis
* Network configuration analysis
* Packet field inspection
* Network troubleshooting fundamentals