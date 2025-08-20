# OpenAPI / Swagger – Review Notes

**Scope**  
Authorized guidance for documenting and validating API specifications and dev portals.

**Authorization**  
Assess only with permission.

---

## Verification
- Confirm the spec matches deployed behavior (no undocumented admin/debug endpoints).
- Ensure protected routes require authentication in both code and gateway.
- Avoid exposing API keys, secrets, or example payloads with sensitive data.

## Documentation Hygiene
- Separate internal vs public schemas.
- Mark deprecated endpoints; remove from public docs when retired.
- Use schemas to enforce validation on request/response bodies.

## Operational Controls
- Gate interactive consoles (Swagger UI) behind authentication in staging/production.
- Rate-limit and monitor developer portals.
