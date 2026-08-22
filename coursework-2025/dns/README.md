DNS Packet Analysis

Overview

This section documents my analysis of Domain Name System (DNS) traffic using Wireshark and nslookup. The lab focused on how DNS queries and responses are exchanged, how DNS records can be inspected, and how caching can affect what appears in a packet capture.

DNS Analysis

During the analysis, I examined DNS traffic and identified information including:

* DNS server IP addresses
* UDP source and destination ports
* DNS query and response packets
* Query types
* Question and Answer resource records
* Name server records
* IPv4 address records
* DNS caching behavior

DNS Queries and Responses

I identified DNS query and response packets using Wireshark and examined the communication between the client and DNS server. The DNS traffic used UDP, with DNS queries being sent to destination port 53.

For one analyzed exchange, the query contained 1 question and 0 Answer resource records. The corresponding response contained 1 question and 1 Answer resource record.

I also identified an A query, which is used to request an IPv4 address associated with a hostname.

DNS Server and Name Server Analysis

During the lab, I used nslookup to examine DNS information and identified an authoritative name server. I also analyzed name server records for umass.edu and observed multiple NS records in a DNS response.

The response included name servers such as:

* ns1.umass.edu
* ns2.umass.edu
* ns3.umass.edu

Additional records included IPv4 addresses associated with some of these name servers.

DNS Caching

The analysis also demonstrated how DNS caching can affect packet captures. After a computer receives a DNS response, it may temporarily store the result. If the same site is visited again while the cached entry is still available, the computer may reuse the stored result instead of sending another DNS query.

This helped explain why an expected DNS query may not always appear in a Wireshark capture.

Key Takeaways

This lab strengthened my understanding of how DNS translates hostnames into network addressing information and how DNS communication can be inspected with Wireshark. Examining queries, responses, ports, resource records, name servers, and caching behavior provided practical experience analyzing name resolution and identifying potential causes of DNS related connectivity issues.

Skills Demonstrated

* Wireshark packet analysis
* DNS fundamentals
* DNS query and response analysis
* UDP port identification
* A and NS record analysis
* nslookup
* DNS caching analysis
* Network troubleshooting fundamentals