# Hands-On Guide: Essential Networking Commands Cheat Sheet

This guide walks through fundamental networking commands that every DevOps and infrastructure engineer should know. These tools are crucial for diagnosing connectivity issues, analyzing routes, inspecting network usage, and validating DNS and HTTP behaviors.

---

## Tools Covered

- `ping` – Connectivity testing  
- `traceroute` / `tracert` – Route inspection  
- `netstat` – Connection and socket stats  
- `curl` – HTTP request debugging  
- `dig` / `nslookup` – DNS resolution  

---

## 1. `ping` – Reachability Check

**Description**: Sends ICMP echo requests to verify if a target host is alive and how long it takes to respond.

```bash
ping <host>
```

**Example**:
```bash
ping anshgupta.dev
```

**When to Use**:
- To quickly check if a server or device is online
- To measure packet loss or latency

---

## 2. `traceroute` / `tracert` – Packet Path Analysis

**Description**: Reveals the hops (routers) that packets traverse to reach the destination.

- On Linux/macOS:
  ```bash
  traceroute <host>
  ```
- On Windows:
  ```cmd
  tracert <host>
  ```

**Example**:
```bash
traceroute github.com
```

**When to Use**:
- To identify slow or failing points in the network path
- For advanced route diagnostics

---

## 3. `netstat` – Active Connections and Ports

**Description**: Displays active TCP/UDP connections, routing tables, and network interface stats.

```bash
netstat -tuln
```

**Useful Flags**:
- `-t`: TCP only
- `-u`: UDP only
- `-l`: Listening sockets
- `-n`: Show numeric addresses

**When to Use**:
- To identify which services are listening on which ports
- For detecting unauthorized or idle connections

---

## 4. `curl` – HTTP and API Request Tool

**Description**: Versatile command-line tool for making network requests using various protocols.

```bash
curl <url>
```

**Examples**:
- Get HTTP headers:
  ```bash
  curl -I https://example.com
  ```
- Make a POST request:
  ```bash
  curl -X POST -d 'name=devops' https://api.example.com/data
  ```

**When to Use**:
- To test API endpoints
- To simulate client requests and analyze server responses

---

## 5. `dig` / `nslookup` – DNS Resolution Tools

**Description**: Queries DNS servers for detailed domain name information.

- `dig` (preferred on Linux/macOS):
  ```bash
  dig <domain>
  ```
- `nslookup` (available on all OSes):
  ```bash
  nslookup <domain>
  ```

**Example**:
```bash
dig openai.com
```

**When to Use**:
- To resolve IP addresses from domain names
- To check DNS record types (A, CNAME, MX, etc.)

---

## Pro Tip

Most of these tools offer additional power through flags and extended options. Explore more with:

```bash
<command> --help
man <command>
```

---

## Conclusion

These hands-on tools are essential in any DevOps troubleshooting workflow. Keep this cheat sheet nearby as a quick reference for working with network issues in local environments, cloud platforms, or production systems.

