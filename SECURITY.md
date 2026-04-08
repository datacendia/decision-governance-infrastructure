# Security Policy

## Reporting a Vulnerability

**Please do NOT open a public GitHub issue for security vulnerabilities.**

If you discover a security vulnerability in this repository — whether in the specification itself, reference implementations, schemas, or examples — please report it responsibly by emailing:

**security@datacendia.com**

Please include as much detail as possible:
- A clear description of the vulnerability
- The affected file(s) or section(s) of the specification
- Steps to reproduce or a proof-of-concept (if applicable)
- Potential impact assessment

### What to expect

| Timeline | Action |
|----------|--------|
| **48 hours** | Acknowledgment of your report |
| **7 days** | Initial assessment and severity classification |
| **90 days** | Resolution or public disclosure (coordinated with reporter) |

We follow a **90-day responsible disclosure policy**. We ask that you do not publicly disclose the vulnerability until we have had the opportunity to address it or the 90-day window has elapsed.

---

## Scope

Although this is primarily a specification and framework repository, security issues are still in scope and should be reported if you identify:

- Vulnerabilities or weaknesses in the **DGI specification** that could be exploited in conforming implementations (e.g., authentication gaps, insecure-by-design patterns)
- Security issues in **JSON Schemas**, **OpenAPI specifications**, or **example payloads** (e.g., schemas that allow injection of dangerous values)
- Security issues in **reference implementations** or code examples provided in this repository
- Exposed secrets, credentials, or sensitive data accidentally committed to this repository
- Vulnerabilities in the **CI/CD pipeline** (GitHub Actions workflows) that could be exploited for supply-chain attacks

---

## Supported Versions

| Version | Supported |
|---------|-----------|
| v1.0.x (current) | ✅ |
| < v1.0 | ❌ |

---

## Security Best Practices for Implementors

If you are building a system based on the DGI specification, we recommend:

- Validate all decision packets against the provided JSON Schemas before processing
- Treat all fields marked as sensitive in the specification as requiring encryption at rest and in transit
- Follow the authentication and authorization guidance in the specification; do not implement unauthenticated endpoints for decision submission or retrieval
- Subscribe to releases of this repository to receive updates to the specification that may have security implications

---

## Contact

- **Security disclosures:** security@datacendia.com
- **General questions:** Open a GitHub Discussion or Issue (non-security only)
