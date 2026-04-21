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

---

## Host-Based Unbound Did Not Work Well With Docker Pi-hole

### Problem
Unbound worked correctly on the Raspberry Pi host, but Pi-hole running in Docker did not reliably use it as an upstream DNS resolver.

### Cause
The DNS path between Dockerized Pi-hole and host-based Unbound was not reliable in this setup.

### Result
Pi-hole worked normally with public upstream DNS, but integration with host-based Unbound was inconsistent.

### Resolution
A different architecture was selected for the final solution.

---

## Separate Unbound Container Was Not the Best Fit

### Problem
A separate Unbound container was tested, but integration and container behavior were harder to maintain than expected.

### Cause
Different images, architecture compatibility, and networking behavior made the setup more complex.

### Resolution
The final working solution was a combined Pi-hole + Unbound Docker image.

---

## Final Working DNS Design

### Final Solution
The final working setup uses a combined Pi-hole + Unbound Docker image.

### Result
Pi-hole handles DNS filtering and Unbound handles recursive DNS resolution inside the same container.
