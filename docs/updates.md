# Update Routine

## Operating System

Recommended routine:

```bash
sudo apt update
sudo apt full-upgrade -y
sudo apt autoremove -y
sudo reboot

## Docker Containers

cd ~/homelab/uptime-kuma
docker compose pull
docker compose up -d

## Dasbot

cd ~/homelab/dashdot
docker compose pull
docker compose up -d

## Pi-Hole

cd ~/homelab/pihole
docker compose pull
docker compose up -d

## Post-update Verification

Check:

containers are running
web dashboards open correctly
Pi-hole DNS still responds
monitoring remains healthy
