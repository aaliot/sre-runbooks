
# Runbook: Disk Full



## Symptoms

- Application cannot write logs

- "No space left on device" errors



## Steps

1. Find large files: `du -sh /* 2>/dev/null | sort -rh | head -20`

2. Check log directories: `du -sh /var/log/*`

3. Compress old logs: `gzip /var/log/app/*.log.*`

4. Remove old compressed logs: `find /var/log -name "*.gz" -mtime +30 -delete`

