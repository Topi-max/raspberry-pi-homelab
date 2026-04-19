# Troubleshooting Notes

## Pi-hole DNS Timeout on LAN

### Problem
Pi-hole responded locally but not to LAN clients.

### Cause
The interface listening behavior was too restrictive.

### Fix
Changed the Pi-hole DNS setting to allow LAN-originated queries.

---

## Router DNS Setting Not Available

### Problem
The router web interface did not expose a configurable LAN/DHCP DNS setting.

### Result
Pi-hole could not be distributed automatically as the DNS server through the router.

### Workaround
Pi-hole was used as a manual DNS server on selected devices.

### Future Option
Evaluate Pi-hole DHCP later if full-network DNS control is required.

---

## Backup Permission Denied

### Problem
The standard tar command failed because some Pi-hole files required elevated permissions.

### Fix
Run the backup command with `sudo`.

---

## SSH Hardening

### Problem
Password-only SSH access was not ideal for long-term use.

### Fix
Enabled SSH keys first, tested key-based login, and then disabled password authentication.
