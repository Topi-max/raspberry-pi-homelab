## SSH

Initial state:

- SSH enabled with password login

Final state:

- SSH public key authentication enabled
- PasswordAuthentication disabled
- PermitRootLogin disabled
- ChallengeResponseAuthentication disabled

## Network

- Raspberry Pi connected with Ethernet only
- Wi-Fi disabled on Raspberry Pi
- No public exposure of services
- No port forwarding configured on the router

## Service Exposure

Services are accessible only from the local network:

- Pi-hole admin
- Uptime Kuma
- dashdot

## DNS

Final DNS design:

- Pi-hole + Unbound combined in one Docker container
- recursive DNS resolution handled locally
- LAN clients use Pi-hole as DNS server

## Security Approach

This homelab is intended for internal LAN-only operation, not public hosting.
