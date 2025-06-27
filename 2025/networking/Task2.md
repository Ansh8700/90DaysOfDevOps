# Essential Ports and Protocols Every DevOps Engineer Should Know

This quick reference guide highlights some of the most frequently encountered network protocols and their default ports in the DevOps landscape. Mastery of these basics helps ensure secure and reliable system operations.

---

## 1. Web Communication Protocols

### HTTP (Hypertext Transfer Protocol)

- **Port:** 80
- **Purpose:** Facilitates standard, unencrypted communication between browsers and web servers.

### HTTPS (Hypertext Transfer Protocol Secure)

- **Port:** 443
- **Purpose:** Secures web traffic by encrypting data exchanged between client and server.

---

## 2. File Transfer Mechanisms

### FTP (File Transfer Protocol)

- **Port:** 21
- **Purpose:** Enables transfers of files between machines; lacks encryption, making it suitable for trusted networks only.

### SFTP (SSH File Transfer Protocol)

- **Port:** 22 (over SSH)
- **Purpose:** Provides encrypted file transfers and remote file management.

---

## 3. Remote Access & Management

### SSH (Secure Shell)

- **Port:** 22
- **Purpose:** Grants encrypted remote command-line access for administering servers and network devices.

---

## 4. Domain Name Services

### DNS (Domain Name System)

- **Port:** 53
- **Purpose:** Converts human-friendly domain names into IP addresses, vital for internet and internal network operations.

---

## 5. Email Transmission Protocols

### SMTP (Simple Mail Transfer Protocol)

- **Port:** 25
- **Purpose:** Handles outflow of emails from mail servers.

### POP3 (Post Office Protocol v3)

- **Port:** 110
- **Purpose:** Retrieves emails from the server and downloads them to local devices.

### IMAP (Internet Message Access Protocol)

- **Port:** 143
- **Purpose:** Allows users to manage and sync emails across multiple devices.

---

## 6. Database Connectivity

### MongoDB

- **Port:** 27017
- **Purpose:** Default port for MongoDB document databases.

### Microsoft SQL Server

- **Port:** 1433
- **Purpose:** Standard port for connecting to MS SQL Server instances.

---

## 7. DevOps & Monitoring Tool Ports

### Jenkins

- **Port:** 8080 (default)
- **Purpose:** Web interface for continuous integration/continuous delivery (CI/CD) automation.

### Grafana

- **Port:** 3000 (default)
- **Purpose:** Visualization and analytics dashboard for monitoring metrics.

### Redis

- **Port:** 6379 (default)
- **Purpose:** In-memory data structure store, supporting caching, messaging, and more.

### GitLab

- **Ports:** 22 (SSH), 443 (HTTPS), 80 (HTTP)
- **Purpose:** Source code management and CI/CD platform.

---

## 8. Security Guidelines for Protocols and Ports

- **Firewall Configuration:** Only open ports that are absolutely necessary for your application.
- **Port Scanning:** Regularly audit open ports to detect unexpected exposures.
- **Use of Encrypted Protocols:** Prefer SFTP over FTP, HTTPS over HTTP, and SSH over Telnet.
- **Access Controls:** Restrict access to sensitive ports by IP or network segment where feasible.
- **Active Monitoring:** Employ tools to monitor port activity and alert on suspicious patterns.

---

## Further Reading 


For an in-depth exploration of these protocols, practical DevOps scenarios, and additional security insights, check out my comprehensive article on linkdin  

🔗 [Click here to read.](https://www.linkedin.com/pulse/common-network-protocols-role-devops-ansh-gupta-bgkaf)