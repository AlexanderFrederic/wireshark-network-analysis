ICMP Packet Analysis

Overview

This section documents my analysis of Internet Control Message Protocol (ICMP) traffic using Wireshark, ping, and traceroute. The lab focused on examining ICMP Echo Request and Echo Reply packets, identifying ICMP header fields, and using traceroute traffic to observe network hops and changes in round trip time.

ICMP Analysis

During the analysis, I examined ICMP traffic and identified information including:

* Source and destination IP addresses
* ICMP message types and codes
* Checksums
* Identifiers
* Sequence numbers
* Echo Request and Echo Reply packets
* Traceroute behavior
* Network hop latency

Unlike TCP and UDP, ICMP does not use source and destination ports. The protocol operates at the Internet layer and is used for network control, diagnostic, and error messages.

Ping Analysis

I used ping to generate ICMP traffic and examined the resulting packets in Wireshark.

The ICMP Echo Request packet contained:

* Type: 8 (Echo Request)
* Code: 0
* Identifier: 14165
* Sequence Number: 7

I then examined the corresponding Echo Reply:

* Type: 0 (Echo Reply)
* Code: 0
* Identifier: 14165
* Sequence Number: 7

Matching identifiers and sequence numbers helped associate the request with its corresponding reply.

Traceroute Analysis

I also analyzed traffic generated using traceroute to observe how packets travel through multiple network hops.

The analysis demonstrated how traceroute can reveal the routers encountered along a route and the round trip time associated with each hop.

One noticeable change occurred between hops 5 and 6. The round trip time increased from approximately 11 ms at hop 5 to approximately 85 ms at hop 6.

Examining this change demonstrated how traceroute data can be used to identify where latency increases along a network path.

ICMP Error Messages

I compared ICMP error packets with other ICMP packets in the capture. The ICMP error packets contained additional fields that included information from the original packet that caused the error.

I also observed IPv4 and UDP information while examining the traceroute related traffic.

Key Takeaways

This lab strengthened my understanding of how ICMP supports network diagnostics and how tools such as ping, traceroute, and Wireshark can be used together to investigate connectivity and network paths.

Analyzing Echo Requests, Echo Replies, ICMP header fields, network hops, and changes in round trip time provided practical experience with techniques commonly used when troubleshooting network connectivity and latency.

Skills Demonstrated

* Wireshark packet analysis
* ICMP fundamentals
* ping
* traceroute
* Echo Request and Echo Reply analysis
* Packet header inspection
* Network path analysis
* Latency analysis
* Network troubleshooting fundamentals