# Linux Networking Commands

Linux provides several commands for inspecting and troubleshooting network connectivity.

These commands help administrators analyze network configuration, connectivity, and traffic.

---

# ip

The `ip` command is used to view and manage network interfaces, IP addresses, and routing.

Show network interfaces:

```bash
ip a
```

Example output:

```
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP>
    inet 192.168.1.20/24
```

Show routing table:

```bash
ip route
```

Example:

```
default via 192.168.1.1 dev eth0
```

---

# ping

Used to test connectivity between two hosts using **ICMP Echo Request and Echo Reply**.

Example:

```bash
ping google.com
```

Example output:

```
64 bytes from 142.250.182.46: icmp_seq=1 ttl=117 time=23.4 ms
```

Press **Ctrl + C** to stop.

---

# traceroute

Shows the path packets take to reach a destination.

Example:

```bash
traceroute google.com
```

Each hop represents a router along the route.

---

# netstat

Displays network connections, routing tables, and listening ports.

Example:

```bash
netstat -tuln
```

Explanation:

| Option | Meaning |
|------|------|
| t | TCP connections |
| u | UDP connections |
| l | Listening ports |
| n | Numeric addresses |

Example output:

```
tcp   0   0 0.0.0.0:22   0.0.0.0:*   LISTEN
```

---

# ss

Modern replacement for `netstat`.

Example:

```bash
ss -tuln
```

Shows active sockets and listening ports.

---

# hostname

Displays system hostname.

```bash
hostname
```

Show IP associated with hostname:

```bash
hostname -I
```

---

# curl

Used to send HTTP requests from command line.

Example:

```bash
curl http://example.com
```

Used frequently for testing APIs and web services.

---

# wget

Used to download files from the internet.

Example:

```bash
wget http://example.com/file.txt
```

---

# nslookup

Used to query DNS servers for domain name resolution.

Example:

```bash
nslookup google.com
```

Shows the IP address associated with the domain.

---

# Why These Commands Are Important

These commands help administrators:

- test network connectivity
- analyze routing
- identify open ports
- troubleshoot network issues
