# Raspberry Pi DNS Filtering Server (Pi-hole Deployment)

## Overview
Deployed and configured a Raspberry Pi–based Pi-hole DNS server as the primary DNS resolver for a private LAN.

Implemented network-wide DNS filtering and ad blocking to improve privacy, reduce unnecessary traffic, and centralize DNS management across multiple client devices.

Demonstrates hands-on experience with network services, DNS administration, client segmentation, and system troubleshooting in a controlled environment.

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

Firewall: UFW (Uncomplicated Firewall)  
- Allowed Ports:
  - 53 (DNS)
  - 80 (HTTP)
  - 443 (HTTPS)
  - 22 (SSH)
  - 123 (NTP)

---

## Storage

- Operating system deployed on NVMe SSD for improved performance
- SD card retained for backup and auxiliary storage 

---

## Deployment Process

### System Update
```bash
sudo apt update && sudo apt upgrade -y
```

---

## Screenshots

### Pi-hole Dashboard Overview
Displays real-time DNS statistics including total queries, blocked queries, and client activity.

![Dashboard](images/dashboard-overview.jpg)

### DNS Query Activity
Demonstrates active DNS request handling and filtering across multiple LAN clients.

![Query Log](images/query-log-activity.png)

---

## Troubleshooting and Optimization

- Diagnosed and resolved DNS resolution issues through iterative testing
- Monitored live DNS traffic using pihole -t
- Tuned blocklists and implemented selective whitelisting to maintain service functionality
- Verified service health using pihole status

---

## System Validation and Verification

### Service Validation

- Confirmed DNS service operation on port 53
- Verified active filtering and FTL engine status

### Storage Verification

- Root filesystem mounted on NVMe (/dev/nvme0n1p2)
- Filesystem type: ext4
- Optimized mount options (noatime)

### Verification Commands

```bash
pihole status
lsblk
findmnt /
```

---

## Key Outcomes

- Deployed a centralized DNS filtering solution for a multi-device LAN
- Reduced unwanted DNS traffic and improved network privacy
- Implemented device-level policy control using client segmentation
- Increased system performance and reliability through NVMe migration
- Demonstrated practical skills in Linux administration, networking, and troubleshooting



