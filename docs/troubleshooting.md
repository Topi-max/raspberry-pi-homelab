# Troubleshooting Notes

## Pi-hole DNS Timeout on LAN

### Problem
Pi-hole responded locally but not to LAN clients.

### Cause
Interface listening behavior was too restrictive.

### Fix
Changed Pi-hole DNS setting to allow LAN-originated queries.

---

## Router DNS Setting Not Available

### Problem
Router web UI did not expose a LAN/DHCP DNS setting.

### Workaround
Used Pi-hole as manual DNS on selected devices.

### Future Option
Consider Pi-hole DHCP later if full-network DNS control is required.

---

## Backup Permission Denied

### Problem
Standard tar command failed due to protected Pi-hole files.

### Fix
Run backup command with `sudo`.

---

## SSH Hardening

### Problem
Need to avoid weak password-only SSH access.

### Fix
Enabled SSH keys first, tested them, then disabled password authentication.
