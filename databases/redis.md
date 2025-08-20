# Redis – Operational Reference

**Scope**  
Operational reference for working with Redis in authorized environments. Intended for administrators, defenders, and auditors verifying configuration and data integrity.

**Authorization**  
Use only against systems you own or are explicitly permitted to test.

---

## Quick Facts
- In-memory key/value store supporting strings, lists, sets, hashes, streams.
- Default port: 6379. Authentication and network controls are strongly recommended.

## Administration
- `PING` – connectivity check  
- `INFO` – server metrics and configuration overview  
- `CONFIG GET *` – view configuration (restrict in production)  
- `DBSIZE` – number of keys in current DB  
- `SELECT <db>` – switch logical database (0..15 by default)

## Data Inspection (Use judiciously on large datasets)
- Prefer `SCAN` over `KEYS *` for performance:
  - `SCAN 0 MATCH <pattern> COUNT 100`
- Key-type reads:
  - `GET <key>` (string)
  - `HGETALL <hash>` (hash)
  - `LRANGE <list> 0 -1` (list)
  - `SMEMBERS <set>` (set)
  - `ZRANGE <zset> 0 -1 WITHSCORES` (sorted set)

## Security & Hardening
- Enable `requirepass` / ACLs; avoid legacy `requirepass` alone in multi-user setups.
- Bind to localhost or internal subnets; restrict via firewall/Security Groups.
- Disable dangerous commands or rename them with `rename-command` where appropriate.
- Monitor: Authentication failures, unusual key growth, config changes.

## Incident Readiness
- Baseline `INFO` outputs and keyspace metrics.
- Snapshot policies (RDB/AOF) tested and recoverable.
- Log retention sufficient for auditing access and changes.
