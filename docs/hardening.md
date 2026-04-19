# Hardening Notes

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

- Uptime Kuma
- dashdot
- Pi-hole admin

## Pi-hole

Important DNS setting:

- Interface listening behavior changed to allow LAN clients

## Security Approach

This homelab is intended for internal LAN-only operation, not public hosting.
