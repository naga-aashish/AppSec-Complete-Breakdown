# APPLICATION SECURITY (AppSec) — COMPLETE BREAKDOWN

---

## 1. CORE APPLICATION TYPES IN AppSec

| # | Application Type | Description | Security Standard |
|---|---|---|---|
| 1 | Web Applications | Browser-based apps (HTTP/HTTPS) | OWASP Top 10 |
| 2 | Mobile Applications | iOS & Android native/hybrid apps | OWASP Mobile Top 10 |
| 3 | Thick Client (Desktop) | Locally installed software with optional server communication | OWASP Desktop App Guide |
| 4 | API (REST/SOAP/GraphQL) | Machine-to-machine endpoints | OWASP API Top 10 |
| 5 | Cloud-Native / Serverless | Lambda, Azure Functions, K8s-deployed apps | OWASP Serverless Top 10 |
| 6 | Hybrid Applications | Web tech in native wrappers (Electron, Cordova, Tauri) | Web + Desktop combined |

---

## 2. ALL SECURITY ACTIVITIES × ALL 6 APP TYPES

| # | Security Activity | Web App | Mobile App | Thick Client | API | Cloud-Native/Serverless | Hybrid App |
|---|---|---|---|---|---|---|---|
| 1 | Threat Modeling | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 2 | SAST | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 3 | DAST | ✅ | ✅ | ⚠️ Limited | ✅ | ✅ | ✅ |
| 4 | IAST | ✅ | ⚠️ Limited | ❌ Rare | ✅ | ⚠️ Limited | ✅ |
| 5 | SCA | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 6 | RASP | ✅ | ⚠️ Limited | ❌ Rare | ✅ | ⚠️ Limited | ⚠️ Limited |
| 7 | VAPT (Pen Testing) | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 8 | Vulnerability Management | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 9 | Secret Scanning | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 10 | Secure Code Review (Manual) | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 11 | Fuzzing | ✅ | ⚠️ Limited | ✅ | ✅ | ✅ | ✅ |
| 12 | Configuration Review | ✅ | ✅ | ✅ | ✅ | ✅ Critical | ✅ |
| 13 | Reverse Engineering | ❌ | ✅ | ✅ | ❌ | ❌ | ✅ |
| 14 | DevSecOps (CI/CD) | ✅ | ✅ | ✅ | ✅ | ✅ Critical | ✅ |
| 15 | Compliance/Regulatory | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 16 | IaC Security Scanning | ⚠️ If cloud-hosted | ❌ | ❌ | ⚠️ If cloud-hosted | ✅ Critical | ⚠️ If cloud-hosted |
| 17 | Container/Image Scanning | ⚠️ If containerized | ❌ | ❌ | ⚠️ If containerized | ✅ Critical | ⚠️ If containerized |
| 18 | CSPM (Cloud Posture Mgmt) | ❌ | ❌ | ❌ | ❌ | ✅ Critical | ❌ |

---

## 4. SDLC PHASE MAPPING

| SDLC Phase | Activities | Applies To |
|---|---|---|
| Design | Threat Modeling | All 6 |
| Development | SAST, Secret Scanning, Secure Code Review, SCA | All 6 |
| Build / CI | SCA, SAST (automated), IaC Scanning, Container Scanning, DevSecOps | All 6 (IaC/Container = Cloud-Native mainly) |
| Testing / QA | DAST, IAST, Fuzzing, VAPT | All 6 (varies) |
| Pre-Release | Pen Testing, Reverse Engineering, Config Review | All 6 (varies) |
| Production | RASP, CSPM, Vuln Management, Compliance | All 6 (CSPM = Cloud-Native) |
| Ongoing | Vuln Management, Re-testing, Threat Intel | All 6 |

---

## 5. PRIORITY MATRIX

| Priority | Web App | Mobile App | Thick Client | API | Cloud-Native | Hybrid App |
|---|---|---|---|---|---|---|
| 🔴 Critical | DAST, SAST, VAPT | Reverse Eng, SAST, VAPT | Reverse Eng, VAPT, SAST | DAST, SAST, VAPT | IaC Scan, Container Scan, CSPM, SAST | DAST, SAST, Reverse Eng |
| 🟠 High | SCA, IAST, Secret Scan | SCA, Secret Scan, Config | Fuzzing, Config, SCA | SCA, Fuzzing, Secret Scan | SCA, DAST, Secret Scan, Config | SCA, VAPT, Secret Scan |
| 🟡 Medium | Fuzzing, RASP, Config | DAST, Fuzzing, DevSecOps | DevSecOps, Vuln Mgmt | IAST, RASP, Config | VAPT, Fuzzing, DevSecOps | Config, Fuzzing, DevSecOps |
| 🟢 Good to have | Threat Modeling, Compliance | IAST, RASP, Compliance | IAST, Compliance | Threat Modeling, Compliance | RASP, IAST, Compliance | IAST, RASP, Compliance |

---

## Document Information
- Subject: Application Security (AppSec) — Complete Breakdown
- Version: 1.0
- Date: May 2026
