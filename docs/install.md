# Installation Guide

## 1. Hardware Used

- Raspberry Pi 5 B (8 GB)
- Official 27W power supply
- Aluminum case with cooling
- 128 GB microSD

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
- Static DHCP reservation configured in router
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
- docker version
- docker compose version

## 6. Service Deployment

Created service directories:
- uptime-kuma
- dashdot
- pihole

Each service was deployed with Docker Compose and configured to restart automatically.

## 7. Validation

Verified:
- Uptime Kuma accessible in browser
- dashdot accessible in browser
- Pi-hole admin accessible in browser
- Pi-hole DNS responding correctly on LAN
