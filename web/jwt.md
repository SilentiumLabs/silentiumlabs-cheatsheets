# JSON Web Tokens (JWT) – Verification Notes

**Scope**  
Authorized guidance for inspecting and validating JWTs in development and security reviews.

**Authorization**  
Decode and test only tokens you are permitted to handle.

---

## Inspection
- Parse header/payload locally; do not rely on untrusted online tools.
- Verify `alg` is expected (e.g., RS256/ES256). Reject `none` or unexpected algorithms.
- Validate `exp`, `nbf`, `iat`, `iss`, `aud` against server policy.

## Implementation Guidance
- Prefer asymmetric signing (RS/ES) with key rotation and KID management.
- Enforce audience/issuer checks server-side.
- Prevent algorithm confusion (explicitly pin acceptable algorithms).

## Operational Controls
- Short token lifetimes; refresh rotation.
- Revoke/blacklist on compromise where architecture permits.
- Log verification failures and unusual claim sets.
