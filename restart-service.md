
# Runbook: Restart a Service



## When to use

When a service is unresponsive and needs a controlled restart.



## Steps

1. Check current service status: `systemctl status SERVICE_NAME`

2. Check logs before restarting: `journalctl -u SERVICE_NAME -n 50`

3. Restart: `sudo systemctl restart SERVICE_NAME`

4. Verify it came back up: `systemctl status SERVICE_NAME`

5. Check logs for errors: `journalctl -u SERVICE_NAME -n 20`



## Rollback

If restart fails, escalate to on-call lead.


## IMPORTANT: Never restart during trading hours (09:00-17:30 BST)
