# Raspberry Pi Pi-hole DNS Server

## Overview
Deployed, configured, and validated a Raspberry Pi–based Pi-hole server as the primary DNS resolver for a private LAN.

The system enables network-wide DNS filtering and ad blocking, improving privacy, reducing unwanted traffic, and centralizing DNS control across multiple devices.

This project demonstrates real-world network administration tasks, including DNS management, DHCP integration, policy-based filtering, and troubleshooting in a controlled environment.

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
- IP Assignment: DHCP reservation via router (ensures consistent IP without manual static configuration)
- DNS Role: Primary resolver for LAN clients  
- Fallback DNS: Router (sanitized)

---

## Advanced Configuration

### Client-Based DNS Filtering (Device Segmentation)
Designed and implemented client-based DNS filtering using Pi-hole groups to enforce device-specific network policies.

- Isolated streaming devices (Roku) into a dedicated client group
- Applied stricter blocklists to reduce ads on streaming platforms
- Maintained separate filtering policies for general LAN clients to prevent service disruption

---

## Pi-hole Configuration

- Pi-hole Core Version: v6.4  
- Web Interface Version: v6.5  
- FTL Engine Version: v6.6  

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

- Operating System hosted on NVMe SSD  
- SD card retained for auxiliary storage and backup use  

---

## Deployment Process

### System Update
```bash
sudo apt update && sudo apt upgrade -y
```

---

## Screenshots

### Pi-hole Dashboard Overview
The dashboard displays real-time DNS statistics, including total queries, blocked queries, and client activity across the network.

![Dashboard](images/dashboard-overview.jpg)

### DNS Query Activity
The query log demonstrates real-time DNS requests from multiple LAN clients, confirming that the Pi-hole instance is actively handling and filtering network traffic.

![Query Log](images/query-log-activity.png)

---

## Troubleshooting and Optimization

- Diagnosed DNS resolution issues and applied temporary resolver fixes when needed  
- Monitored live DNS traffic using `pihole -t` to verify filtering behavior  
- Adjusted blocklists and implemented selective whitelisting to prevent application breakage 
- Verified DNS service health and status using `pihole status`

---

## System Validation and Verification

### Pi-hole Service Status
I verified that the Pi-hole DNS service is active and handling DNS requests on port 53 across multiple LAN clients.

- DNS service running
- Blocking enabled
- FTL engine active

### Storage Verification
I confirmed that the system is running from NVMe storage rather than the default SD card.

- Root filesystem mounted on NVMe (`/dev/nvme0n1p2`)
- Filesystem type: ext4
- Mount options optimized for performance (`noatime`)

### Verification Commands

```bash
pihole status
lsblk
findmnt /
```

---

## Key Outcomes

- Deployed a centralized DNS filtering solution for a multi-device LAN environment  
- Reduced unwanted network traffic and improved privacy through DNS-based filtering  
- Implemented DHCP reservations to ensure consistent network addressing for critical devices  
- Applied device-specific filtering policies to balance security and usability  
- Improved system performance and reliability by migrating the OS to NVMe storage



