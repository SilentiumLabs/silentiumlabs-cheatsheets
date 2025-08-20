# Elasticsearch – Operational Reference

**Scope**  
Authorized administrative reference for cluster health, indices, and security posture.

**Authorization**  
Use only with explicit permission.

---

## Cluster & Indices
- `GET /_cluster/health` – cluster status  
- `GET /_cat/nodes?v` – nodes summary  
- `GET /_cat/indices?v` – indices summary  
- `GET /index/_search?q=*:*&size=1` – sample doc

## Mapping & Data
- `GET /index/_mapping` – field mappings  
- `GET /index/_count` – document count  
- `POST /index/_search` with JSON body – filtered queries

## Security & Hardening
- Always enable security features (authn/authz, TLS) in modern distributions.
- Restrict network exposure; never expose management endpoints to the public internet.
- Apply index-level permissions (read vs write) by role.

## Maintenance
- ILM policies for retention and rollover.
- Snapshot repositories and periodic backups.
- Monitor heap usage, GC, and shard balance.
