# OSI and TCP/IP Networking Models

---

## OSI Model Overview

The OSI (Open Systems Interconnection) model organizes network communication into seven distinct layers, each with a specific role in moving data from one device to another.

- [Layer 1: Physical Layer](#layer-1-physical-layer)
- [Layer 2: Data Link Layer](#layer-2-data-link-layer)
- [Layer 3: Network Layer](#layer-3-network-layer)
- [Layer 4: Transport Layer](#layer-4-transport-layer)
- [Layer 5: Session Layer](#layer-5-session-layer)
- [Layer 6: Presentation Layer](#layer-6-presentation-layer)
- [Layer 7: Application Layer](#layer-7-application-layer)

---

### Layer 7: Application Layer

- Sits at the top of the stack, closest to the end user.
- Provides the interface for users to interact with network services.
- Protocol Data Unit: Data

- **High-level protocols** facilitate sharing resources or accessing files remotely.
- Works with multiple protocols like POP3, IMAP, Telnet, and SNMP to support various network applications.

- **Example:** Video conferencing platforms and instant messaging apps; these interact directly with the Application Layer to send and receive messages or video streams.

---

### Layer 6: Presentation Layer

- Protocol Data Unit: Data
- Functions as the system’s “translator,” converting data between formats the network and applications understand.

- Handles tasks such as:
    - file type conversion (e.g., JPEG to PNG)
    - compressing data to save bandwidth
    - encrypting/decrypting to protect sensitive info

- **Protocols:**
    - **MIME** is used for encoding multimedia email attachments.
    - **TLS** (Transport Layer Security) is the standard for encrypting modern web traffic.

- **Example:** Streaming music on Spotify, where audio data is compressed and decrypted for playback.

---

### Layer 5: Session Layer

- Manages and maintains dialogs between two devices.
- Protocol Data Unit: Data
- Sets up, manages, and tears down connections, and can keep sessions “alive” or recover from sudden interruptions.

- **Protocols:**
    - **NetBIOS** (Network Basic Input/Output System)
    - **L2TP** (Layer 2 Tunneling Protocol)
    - **SMB** (Server Message Block)

- **Example:** Uploading files to a cloud drive—your session persists so you can upload multiple files in one go without reconnecting each time.

---

### Layer 4: Transport Layer

- Protocol Data Unit: Segment (TCP) or Datagram (UDP)
- Ensures reliable, complete, and correct data delivery between devices.
- Handles segmentation, flow control, and error recovery.

- **Protocols:** SCTP (Stream Control Transmission Protocol), TCP, UDP

- **Example:** Playing an online multiplayer game. UDP is often used for its speed, while TCP is used for in-game purchases to guarantee transaction delivery.

---

### Layer 3: Network Layer

- Protocol Data Unit: Packet
- Focuses on routing and forwarding packets between different networks.
- Finds the optimal path for data, even across complex internetworks.

- **Protocols:** BGP (Border Gateway Protocol), IP, IGMP (Internet Group Management Protocol)

- **Example:** Sending an email to someone overseas—the Network Layer finds a route across continents, through various routers and ISPs.

---

### Layer 2: Data Link Layer

- Protocol Data Unit: Frame
- Handles transmission between directly connected nodes and manages error detection within a local network.

- **Protocols:** PPP (Point-to-Point Protocol), HDLC, VLAN (Virtual LAN)

- **Example:** When your smart TV connects to Wi-Fi, the Data Link Layer ensures your video stream is delivered frame by frame without local interference.

---

### Layer 1: Physical Layer

- Protocol Data Unit: Bit
- Deals with transmitting raw bits or symbols over the chosen medium—copper wire, fiber optics, or radio waves.

- **Technologies:** USB cables, Bluetooth, satellite transmission

- **Example:** Plugging your phone into a charger with a USB-C cable; the Physical Layer moves the electrical signals.

---

## TCP/IP Model

A streamlined, four-layer model widely used in real-world networking. It maps to the OSI model but combines and simplifies some layers.

- [Application Layer](#1-application-layer)
- [Transport Layer](#2-transport-layer)
- [Internet Layer](#3-internet-layer)
- [Network Interface Layer](#4-network-interface-layer)

The TCP/IP model is at the core of the Internet and most modern networks, using the TCP/IP protocol suite.

---

### 1. Application Layer

- Topmost layer, combining Application, Presentation, and Session layers from OSI.
- Facilitates direct user and process interaction with the network.

- **Protocols:**
    - **DNS** (Domain Name System) – translates domain names into IP addresses.
    - **SMTP** (Simple Mail Transfer Protocol) – sends emails between servers.
    - **FTP** (File Transfer Protocol) – transfers files across networks.

- **Example:** Downloading a file from a remote FTP server or checking your email through a webmail client.

---

### 2. Transport Layer

- Functions like the OSI Transport Layer.
- Responsible for reliable or best-effort data delivery, sequencing, and error control.

- **Protocols:**
    - TCP – ensures reliable, ordered delivery.
    - UDP – faster, connectionless transfer for time-sensitive data.

- **Example:** Voice-over-IP (VoIP) calls favor UDP for minimal delay, while web browsing relies on TCP for complete and ordered page loads.

---

### 3. Internet Layer

- Similar to OSI’s Network Layer.
- Handles logical addressing and routing of packets over interconnected networks.

- **Protocols:**
    - IPv4/IPv6 – provide unique addresses for every device.
    - ICMP – used for diagnostic tools like ping and traceroute.

- **Example:** Sending a WhatsApp message—the Internet Layer finds the route from your phone to a friend’s device, wherever they are in the world.

---

### 4. Network Interface Layer

- Corresponds to OSI’s Data Link and Physical Layers.
- Defines how data is physically sent across hardware interfaces.

- **Technologies:** Ethernet, DSL, Wi-Fi, LTE

- **Example:** Your Smart Fridge connecting to your home router via Ethernet to download a firmware update.

---