
```markdown
# Backup Notes

## What Is Backed Up

- Docker Compose files
- homelab directory structure
- service configuration files
- documentation

## Backup Command

```bash
mkdir -p ~/backups
sudo tar -czf ~/backups/homelab-backup-$(date +%F).tar.gz ~/homelab

## Verification
```bash
ls -lh ~/backups
