# Installation Guide

## 1. Hardware Used

- Raspberry Pi 5 B (8 GB)
- Official 27W power supply
- Aluminum case with cooling
- 128 GB microSD card

## 2. Operating System

Installed:

- Raspberry Pi OS Lite (64-bit)

Configured during imaging:

- hostname
- user account
- SSH enabled
- timezone set correctly

## 3. Network Setup

- Raspberry Pi connected to the router using Ethernet
- Static DHCP reservation configured in the router
- Local IP assigned for stable service access

## 4. Base System Preparation

Performed after first boot:

- system update
- package upgrade
- reboot
- network verification

## 5. Docker Installation

Installed:

- Docker Engine
- Docker Compose plugin

Verified:

- `docker version`
- `docker compose version`

## 6. Service Deployment

Created service directories for:

- Uptime Kuma
- dashdot
- Pi-hole

An initial Pi-hole deployment was completed first.

Later, Unbound was integrated into the DNS design.  
Multiple approaches were tested:

- host-based Unbound
- separate Unbound container
- combined Pi-hole + Unbound container

The final working solution was a combined **Pi-hole + Unbound** Docker image.

## 7. Final Working DNS Design

Final DNS design:

- client devices send DNS requests to Pi-hole
- Pi-hole filters allowed and blocked domains
- Unbound performs recursive DNS resolution inside the same container

## 8. Validation

Verified:

- Uptime Kuma accessible in browser
- dashdot accessible in browser
- Pi-hole admin accessible in browser
- DNS responding correctly on LAN
- Pi-hole + Unbound working together in the final containerized setup
