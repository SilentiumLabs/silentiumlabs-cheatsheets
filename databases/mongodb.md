# MongoDB – Operational Reference

**Scope**  
Authorized administrative and defensive reference for MongoDB clusters.

**Authorization**  
Use only with explicit permission.

---

## Quick Facts
- Default ports: 27017 (mongod), 27018/27019 (replica/shards).
- Authentication and network isolation are mandatory in production.

## Administration
- `db.version()` – server version  
- `db.stats()` – db stats  
- `db.getMongo().getDBs()` – list databases (requires privilege)  
- `db.getCollectionNames()` – list collections  
- `db.currentOp()` – running operations (privileged)

## Data Inspection
- `db.<collection>.findOne()` – sample a document  
- `db.<collection>.countDocuments({})` – count documents  
- `db.<collection>.aggregate([...])` – pipeline analysis (authorized contexts)

## Security & Hardening
- Enable SCRAM auth; enforce role-based access (least privilege).
- Bind to internal interfaces; restrict with firewall/VPC rules.
- TLS for all client/replica/shard traffic.
- Disable REST/HTTP status endpoints on older versions; keep server up to date.

## Monitoring & Audit
- Enable audit logs where applicable.
- Watch for anonymous access, wildcard roles, and `{ role: 'root' }` assignments.
- Baseline slow query logs to detect anomalies.

## Backup & Recovery
- Test `mongodump` / `mongorestore` or snapshot tooling.
- Validate PIT (point-in-time) recovery procedures.
