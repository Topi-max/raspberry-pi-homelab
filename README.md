# Raspberry Pi Homelab

A self-hosted Raspberry Pi 5 homelab project built for learning Linux administration, Docker, DNS filtering, monitoring, and service hardening.

## Project Overview

This project runs on a Raspberry Pi 5 and includes the following services:

- **Pi-hole** for DNS-based ad and tracker blocking
- **Uptime Kuma** for service monitoring
- **dashdot** for host resource monitoring

The goal of the project was to build a small but practical homelab environment and document the installation, hardening, maintenance, backup, and troubleshooting process.

## Hardware

- Raspberry Pi 5 B, 8 GB RAM
- Official Raspberry Pi 27W USB-C power supply
- Aluminum case / heatsink
- Kingston High Endurance 128 GB microSD card

## Software Stack

- Raspberry Pi OS Lite (64-bit)
- Docker Engine
- Docker Compose
- Pi-hole
- Uptime Kuma
- dashdot

## Features

- DNS filtering with Pi-hole
- Service uptime monitoring
- Host system monitoring
- SSH hardening with key-based authentication
- Manual backup routine
- Lightweight, low-power self-hosted environment

## Network Design

- Raspberry Pi connected to the router with Ethernet
- Management from a Windows laptop over the local network
- No port forwarding enabled
- Internal LAN-only access to services

### Architecture

```text
Windows laptop (Wi-Fi)
        |
        v
   Home router / 5G router
        |
        +----------------------+
        |                      |
        v                      v
 Raspberry Pi 5           Other LAN devices
 (Ethernet)

        |
        +-- Pi-hole
        +-- Uptime Kuma
        +-- dashdot
```
## Services

| Service | Purpose |
|--------|---------|
| Pi-hole | DNS filtering and local DNS service |
| Uptime Kuma | Uptime monitoring for internal services |
| dashdot | Resource dashboard for CPU, memory, storage and network |

## Security Notes

- SSH key authentication enabled
- Password-based SSH login disabled
- Root login disabled
- Raspberry Pi Wi-Fi disabled, Ethernet only
- No public exposure of services
- No router port forwarding configured

## Documentation

Detailed setup and maintenance notes are available in the `docs/` folder:

- `install.md`
- `hardening.md`
- `updates.md`
- `backup.md`
- `troubleshooting.md`

## Project Status

Current version:
- Raspberry Pi base system installed
- Docker configured
- Pi-hole working locally
- Uptime Kuma working
- dashdot working
- SSH hardened
- Backup routine tested

## Future Improvements

- Add Unbound
- Add Tailscale for secure remote access
- Improve backup automation
- Evaluate Pi-hole DHCP if router DNS cannot be configured
- Publish a cleaned public portfolio version

## What I Learned

Through this project, I practiced:

- Raspberry Pi deployment and Linux basics
- Docker and Docker Compose service management
- DNS filtering with Pi-hole
- Basic service monitoring with Uptime Kuma
- Host monitoring with dashdot
- SSH hardening with key-based authentication
- Backup planning and troubleshooting
- Secure LAN-only service design

## Disclaimer

This repository contains documentation and example configuration files only.  
Sensitive information such as passwords, private IP planning details, keys, logs, and private service data are intentionally excluded.
All Docker Compose files in this repository are example configurations only and do not contain live credentials or private service data.
