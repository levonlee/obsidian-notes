## Get current system timezone

```sh
timedatectl
```

## Change timezone
```sh
sudo timedatectl set-timezone America/Toronto
sudo systemctl restart cron
sudo systemctl status cron
```