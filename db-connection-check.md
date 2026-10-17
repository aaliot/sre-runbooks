# Runbook: Database Connection Issues



## Symptoms

- Application logs show "connection refused" or "too many connections"

- Dashboards show DB connection pool exhausted



## Steps

1. Check active connections: `SELECT count(*) FROM pg_stat_activity;`

2. Check for long-running queries: `SELECT pid, now()-query_start AS duration, query FROM pg_stat_activity WHERE state='active';`

3. Kill problematic queries if needed: `SELECT pg_terminate_backend(pid);`

