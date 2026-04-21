```markdown
# Update Routine

## Operating System

## Recommended update routine:

```bash
sudo apt update
sudo apt full-upgrade -y
sudo apt autoremove -y
sudo reboot
```

## Docker Containers

```bash
cd ~/homelab/uptime-kuma
docker compose pull
docker compose up -d
```

## Dasbot

```bash
cd ~/homelab/dashdot
docker compose pull
docker compose up -d
```

## Pi-Hole

```bash
cd ~/homelab/pihole-unbound
docker compose pull
docker compose up -d
```

## Post-update Verification

Check:

containers are running
web dashboards open correctly
Pi-hole DNS still responds
monitoring remains healthy

Useful Commands:

```bash
docker ps
docker logs uptime-kuma --tail 30
docker logs dashdot --tail 30
docker logs pihole --tail 50
```
