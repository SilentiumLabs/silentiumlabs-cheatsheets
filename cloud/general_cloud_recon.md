# Cloud Posture – Authorized Review Notes

**Scope**  
Neutral checklist for cloud configuration posture in authorized environments (AWS/GCP/Azure).

**Authorization**  
Perform only with explicit permission.

---

## Inventory
- Enumerate accounts/subscriptions, regions, and public endpoints.
- Track internet-facing load balancers, storage, functions, and CI/CD endpoints.

## Storage & Data
- Public access policies on object storage (buckets/containers)
- Encryption at rest/in transit
- Lifecycle and retention policies aligned to compliance

## Identity & Access
- MFA enforcement for humans; workload identities for services
- Least privilege roles; periodic access review
- Audit logging enabled and retained

## Networking
- Ingress/egress controls; security groups and NSGs scoped to necessity
- Private endpoints for internal services where possible
- WAF and DDoS protections for critical surfaces

## Operations
- Patching cadence and image baselines
- Backup, DR, and restore testing
- Centralized logging/monitoring with alerting
