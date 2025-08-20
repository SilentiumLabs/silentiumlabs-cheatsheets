# DICOM / PACS – Professional Notes (Redacted)

**Scope**  
Operational notes for authorized validation of Picture Archiving and Communication Systems (PACS) and DICOM services.

**Authorization**  
Use only in test labs or with written authorization. Never capture or store PHI/PII.

---

## Components
- DICOM services (C-STORE, C-FIND, C-MOVE on TCP/104 or vendor ports)
- PACS web consoles (may front DICOM services)
- Modalities and viewers

## Operational Checks (Authorized)
- Access control: authentication enabled for all consoles and APIs
- Transport security: TLS in transit for DICOM and web
- Role separation: viewer vs admin privileges
- Audit: access logging for study retrieval/changes

## Compliance & Reporting
- Redact all images and study metadata in reports.
- Provide remediation: enforce auth, segment networks, rotate exposed endpoints.
- Include CVSS only for confirmed, authorized findings.

## Incident Readiness
- Validate backup/restore of studies.
- Verify audit trail integrity and retention policies.
