IP Packet Analysis

Overview

This section documents my analysis of Internet Protocol (IP) traffic using Wireshark. The lab focused on examining IPv4 header fields, identifying how fields change between datagrams, analyzing packet fragmentation, and examining IPv6 addressing and header information.

IPv4 Analysis

During the IPv4 analysis, I inspected packet header fields including:

* Source and destination IP addresses
* Time to Live (TTL)
* Protocol number
* Header length
* Total length
* Identification
* Flags
* Fragment offset
* Header checksum

In the initial UDP datagram, the IPv4 header had a TTL of 1, a protocol value of 17 for UDP, a header length of 20 bytes, and a total length of 56 bytes.

Changing IPv4 Header Fields

I compared multiple IP datagrams to determine which header fields changed as packets were transmitted.

The fields that changed included:

* Identification
* TTL
* Header checksum

The Identification field changed between datagrams, while the TTL was adjusted to reach successive network hops. Because values within the IP header changed, the Header Checksum was also recalculated.

Other fields remained constant during the analyzed communication, including:

* Source IP address
* Destination IP address
* Header length
* Protocol

This comparison helped demonstrate which IPv4 header fields describe fixed communication information and which can change as packets are transmitted.

Protocol Identification

I examined the Protocol field within IPv4 packets to determine which higher level protocol was being carried.

Examples from the analysis included:

* UDP: Protocol 17
* ICMP: Protocol 1

This demonstrated how the IPv4 header identifies the protocol contained within its payload.

IP Fragmentation

I also examined fragmented IPv4 traffic.

Wireshark showed fragmentation through fields such as:

* Flags
* Fragment Offset
* Total Length
* Header Checksum

One analyzed fragment had a total length of 1500 bytes. Another showed a Fragment Offset corresponding to 1480 bytes.

Examining these fields demonstrated how IPv4 handles packets that are divided into multiple fragments for transmission.

IPv6 Analysis

The lab also included analysis of IPv6 traffic. I examined fields including:

* Source IPv6 address
* Destination IPv6 address
* Flow Label
* Payload Length
* Next Header

One analyzed IPv6 packet contained a payload length of 37 bytes and identified UDP as the Next Header using protocol value 17.

I also examined a DNS response containing an AAAA record, which provided an IPv6 address associated with a hostname.

Key Takeaways

This lab strengthened my understanding of IPv4 and IPv6 packet structure and how Wireshark can be used to inspect IP traffic.

Comparing packet headers provided practical experience identifying changing and constant fields, interpreting protocol numbers, analyzing TTL behavior, and examining IPv4 fragmentation. The IPv6 portion also introduced important differences in IPv6 addressing and header information.

Skills Demonstrated

* Wireshark packet analysis
* IPv4 and IPv6 fundamentals
* IP header inspection
* TTL analysis
* Protocol identification
* IPv4 fragmentation analysis
* IPv6 header analysis
* Packet field comparison
* Network troubleshooting fundamentals