# Raspberry Pi Pi-hole DNS Server

## Overview
This project documents the deployment and configuration of a Raspberry Pi–based Pi-hole DNS server used as the primary DNS resolver for a private LAN.

The system provides network-wide ad blocking, DNS filtering, and improved privacy by controlling outbound DNS queries.

All network identifiers and IP addresses have been sanitized for security.

---

## Architecture

- Device Role: DNS Filtering Server  
- Platform: Raspberry Pi  
- Service: Pi-hole  
- DHCP: Router-managed  
- Network Scope: Private LAN  

---

## System Information

- Operating System: Debian GNU/Linux 13 (Trixie)  
- Kernel: Raspberry Pi Linux Kernel (6.x)  
- CPU Architecture: ARM Cortex-A76  

---

## Network Configuration

- Interface: eth0 (Ethernet)  
- IP Assignment: Static (DHCP reservation via router)  
- DNS Role: Primary resolver for LAN clients  
- Fallback DNS: Router (sanitized)  

---

## Pi-hole Configuration

- Pi-hole Core Version: v6.x  
- Web Interface Version: v6.x  
- FTL Engine Version: v6.x  

### Service Status
- DNS service active on port 53  
- IPv4 and IPv6 enabled  
- Blocking enabled  

---

## Firewall Configuration

- Firewall: UFW (Uncomplicated Firewall)  
- Allowed Ports:
  - 53 (DNS)
  - 80 (HTTP)
  - 443 (HTTPS)
  - 22 (SSH)
  - 123 (NTP)

---

## Storage

- Operating System hosted on SD card  
- Additional storage provided via NVMe SSD  

---

## Deployment Process

### System Update
```bash
sudo apt update && sudo apt upgrade -y


