# FUTURE_CS_03
# API Security Risk Analysis — Future Interns Cybersecurity Task 3 (2026)

##  Overview

This repository contains my completed work for **Cybersecurity Task 3** assigned by **Future Interns (2026)**.  
The task involved performing a professional, read-only API Security Risk Analysis on public APIs, mapping findings against the **OWASP API Security Top 10 (2023)**, and producing a client-ready security report.

---

##  Objective

The goal of this analysis was to:
- Analyze public and demo APIs for common security vulnerabilities
- Assess authentication mechanisms and access control
- Identify excessive data exposure and missing security controls
- Explain risks in clear business language
- Suggest actionable remediation steps

> This task focuses on **thinking like a security consultant**, not breaking systems.

---

##  APIs Tested

| API | Base URL | Auth Model | Profile |
|-----|----------|------------|---------|
| **ReqRes** | https://reqres.in | x-api-key + Bearer token | Two-layer auth, real sessions |
| **JSONPlaceholder** | https://jsonplaceholder.typicode.com | None | Fully open, no authentication |

---

##  Scope & Ethics

**Allowed:**
- Read-only requests (GET, safe POST where documented)
- Documentation-based analysis
- Header, token, and response inspection

**Not Allowed:**
- Exploitation or bypass attempts
- Flooding or DoS testing
- Attacking private or production APIs

All testing was conducted ethically and legally.

---

##  Tools Used

| Tool | Purpose |
|------|---------|
| **Postman** | Sending requests, inspecting headers and responses |
| **curl (CLI)** | Command-line request testing, header verification |
| **Browser DevTools** | Real-time traffic capture and response inspection |
| **JWT.io** | Decoding and analyzing JWT tokens |
| **MXToolbox** | Header and DNS analysis (reference) |

---

##  Key Findings Summary

| ID | Vulnerability | API | OWASP 2023 | Severity |
|----|--------------|-----|------------|----------|
| RISK-001 | No authentication on all endpoints | JSONPlaceholder | API1 — BOLA |  HIGH |
| RISK-002 | Excessive PII exposure (GPS, phone, address) | JSONPlaceholder | API3 — BOPLA |  HIGH |
| RISK-003 | No rate limiting — scraping/DoS risk | JSONPlaceholder | API4 — Resource Consumption |  MEDIUM |
| RISK-004 | Auth header confusion — 401/403 risk | ReqRes | API2 — Broken Auth |  MEDIUM |
| RISK-005 | Rate limit issues in CI/CD pipelines | ReqRes | API4 — Resource Consumption |  MEDIUM |
| RISK-006 | Free tier quota — availability risk | ReqRes | API8 — Misconfiguration |  LOW |
| RISK-007 | No request logs on free plan | ReqRes | API8 — Misconfiguration |  LOW |

---


## References

- [OWASP API Security Top 10 (2023)](https://github.com/OWASP/API-Security)
- [API Security Checklist](https://github.com/shieldfy/API-Security-Checklist)
- [ReqRes Official Documentation](https://reqres.in/docs)
- [Public APIs Collection](https://github.com/public-apis/public-apis)
