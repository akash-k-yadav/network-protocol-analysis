# Network Protocol Analysis

Packet level analysis of core networking, transport, and application layer
protocols using Wireshark. Built as a home lab project using Kali Linux and
Ubuntu Server in a VirtualBox host-only network, moving from protocol
fundamentals to hands on capture and analysis of each one.

Start here: [OSI Model](01_networking/01_OSI-Model.md) for fundamentals, or
go straight to [02_Labs](02_Labs) for the hands on packet captures.

## Structure

### 01_networking (30 files)

Reference notes covering networking concepts, organized to build up from
fundamentals to full protocol behavior.

- **01 to 07** - fundamentals: OSI model, TCP/IP model, IP addressing, MAC
  addressing, ARP, ports and sockets, networking devices
- **08 to 13** - TCP in depth: overview, three way handshake, data transfer
  and flow control, retransmission and congestion control, connection
  termination, and [TCP based attacks and abuse](01_networking/13_06_TCP_Attacks_and_Abuse.md),
  which covers SYN flood and RST injection along with what a defender would
  look for in that traffic
- **14 to 15** - UDP: overview and comparison with TCP
- **16 to 21** - DHCP, DNS, ICMP, IP header and fragmentation, subnetting
  and CIDR, NAT. The DHCP, DNS, and ICMP notes also include a short section
  on what a defender would look for in that protocol's traffic
- **22 to 29** - application layer protocols: HTTP/HTTPS, FTP/FTPS/SFTP,
  SMTP/POP3/IMAP, SSH, SMB, RDP, NTP, SSL/TLS
- **30** - a Linux command line reference (ip, ss, tcpdump, curl, nslookup,
  and others) covering tools relevant to networking, documented for
  reference rather than used directly to capture traffic in these labs

These are study notes, not lab evidence. For the actual packet captures,
see 02_Labs below.

### 02_Labs (19 lab files across 6 categories)

Hands on packet captures and analysis. Every lab uses Wireshark to capture
and inspect the traffic, and follows the same report format: objective,
lab environment, network configuration, tools used, procedure, observation,
security relevance, and conclusion. Screenshots for each lab are in the
screenshots folder inside that lab's category, and show the traffic as
captured in Wireshark.

```
02_Labs/
├── 01-basics-protocols/ ARP, ICMP, IP structure
├── 02-transport-layer-protocols/ TCP handshake, connection termination,
│ data flow, retransmission, control flow
├── 03-infrastructure-protocols/ DNS query/response, DNS record types,
│ DHCP
├── 04-tls/ TLS handshake
├── 05-file-transfer-protocols/ FTP, FTPS, SFTP
└── 06-emails-protocols/ SMTP, POP3, IMAP, and their encrypted
variants (SMTPS, IMAPS, POP3S)
```

## Lab environment

Most labs use two VMs on a VirtualBox host-only network:
- Kali Linux, used to generate traffic and capture packets in Wireshark
- Ubuntu Server, used as the target, running different services depending
  on the protocol being tested:
  - vsftpd for FTP and FTPS
  - Postfix for SMTP
  - Dovecot for POP3 and IMAP
  - OpenSSH for SFTP

The DNS and DHCP labs are captured against the home network's router acting
as the DNS/DHCP server. The TLS lab captures a real handshake against an
external HTTPS server on the internet.

Traffic is generated using real tools (curl, arping, openssl s_client, mail
clients) rather than synthetic packet crafting, so each capture reflects
what that protocol actually looks like in normal use.