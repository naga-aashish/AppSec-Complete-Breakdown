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

## 3. TOOLS MAPPED PER METHOD × APP TYPE

| # | Web App | Mobile App | Thick Client | API | Cloud-Native | Hybrid App |
|---|---|---|---|---|---|---|
| 1 | Threat Modeling | Threat Dragon, MS TMT | Threat Dragon | Threat Dragon | Threat Dragon | Threat Dragon, STRIDE | Threat Dragon |
| 2 | SAST (Static Application Security Testing) | SonarQube, Checkmarx, Semgrep, CodeQL | Checkmarx, MobSF, Semgrep | Fortify, CodeQL, Checkmarx | Semgrep, CodeQL, Checkmarx | Snyk Code, Semgrep | SonarQube, Semgrep |
| 3 | DAST (Dynamic Application Security Testing) | Burp Suite, ZAP, Invicti | MobSF, Drozer, Frida | Echo Mirage, Burp (proxy) | Burp Suite, ZAP | Burp, ZAP, Nuclei | Burp, ZAP |
| 4 | IAST (Interactive Application Security Testing) | Contrast Security, Seeker | Contrast (limited) | — | Contrast Security | Contrast (limited) | Contrast |
| 5 | SCA (Software Composition Analysis) | Snyk, Dependabot, Mend | Snyk, OWASP Dep-Check | Black Duck, Snyk | Snyk, Dependabot | Snyk, Trivy | Snyk, Dependabot |
| 6 | RASP (Runtime Application Self-Protection) | Contrast, Signal Sciences | Guardsquare | — | Contrast, Imperva | AWS WAF (partial) | Contrast (limited) |
| 7 | VAPT (Vulnerability Assessment & Penetration Testing) | Burp, Nuclei, SQLMap, Nmap | Frida, Objection, Burp | Ghidra, x64dbg, Wireshark | Burp, Postman, Nuclei | ScoutSuite + Burp | Burp, Frida |
| 8 | Vulnerability Management | Qualys, Tenable, Rapid7 | Qualys, NowSecure | Qualys, Tenable | Qualys, Tenable | Wiz, Prisma Cloud | Qualys, Tenable |
| 9 | Secret Scanning | GitGuardian, TruffleHog | GitGuardian, TruffleHog | TruffleHog, custom scripts | GitGuardian, TruffleHog | GitGuardian, TruffleHog | GitGuardian, TruffleHog |
| 10 | Secure Code Review (Manual) | Manual + Semgrep | Manual + MobSF | Manual + dnSpy | Manual + Semgrep | Manual + Semgrep | Manual + Semgrep |
| 11 | Fuzzing | Burp Intruder, AFL | Peach (limited) | WinAFL, Peach | RESTler, Schemathesis | RESTler, custom | Burp Intruder |
| 12 | Configuration Review | ScoutSuite, Lynis | Mobile config audit | Registry/file analysis | API gateway review | Prowler, ScoutSuite | App + container config |
| 13 | Reverse Engineering | — | JADX, Hopper, Frida, Ghidra | dnSpy, Ghidra, IDA, x64dbg | — | — | JADX, Ghidra (native layer) |
| 14 | DevSecOps (CI/CD Integration) | GitHub Actions, GitLab CI | Fastlane + plugins | Jenkins + custom | GitHub Actions | GitHub Actions, ArgoCD | GitHub Actions |
| 15 | Compliance/Regulatory | Qualys, Nessus, Drata, Vanta, OneTrust | NowSecure, Ostorlab, Drata | Qualys, Nessus, Drata | Qualys, Drata, Vanta | Prowler, AWS Audit Manager, Wiz, Prisma Cloud, Drata | Qualys, Drata, Vanta |
| 16 | IaC Security Scanning | — | — | — | — | Checkov, KICS, Terraform Scan | — |
| 17 | Container/Image Scanning | — | — | — | — | Trivy, Aqua, Grype | Trivy (if containerized) |
| 18 | CSPM (Cloud Security Posture Management) | — | — | — | — | Wiz, Prisma Cloud, AWS Security Hub | — |

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
