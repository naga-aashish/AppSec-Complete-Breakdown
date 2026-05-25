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

### 3.1 Threat Modeling
| Web App | Mobile App | Thick Client | API | Cloud-Native | Hybrid App |
|---|---|---|---|---|---|
| Threat Dragon, MS TMT | Threat Dragon | Threat Dragon | Threat Dragon | Threat Dragon, STRIDE | Threat Dragon |

### 3.2 SAST (Static Application Security Testing)
| Web App | Mobile App | Thick Client | API | Cloud-Native | Hybrid App |
|---|---|---|---|---|---|
| SonarQube, Checkmarx, Semgrep, CodeQL | Checkmarx, MobSF, Semgrep | Fortify, CodeQL, Checkmarx | Semgrep, CodeQL, Checkmarx | Snyk Code, Semgrep | SonarQube, Semgrep |

### 3.3 DAST (Dynamic Application Security Testing)
| Web App | Mobile App | Thick Client | API | Cloud-Native | Hybrid App |
|---|---|---|---|---|---|
| Burp Suite, ZAP, Invicti | MobSF, Drozer, Frida | Echo Mirage, Burp (proxy) | Burp Suite, ZAP | Burp, ZAP, Nuclei | Burp, ZAP |

### 3.4 IAST (Interactive Application Security Testing)
| Web App | Mobile App | Thick Client | API | Cloud-Native | Hybrid App |
|---|---|---|---|---|---|
| Contrast Security, Seeker | Contrast (limited) | — | Contrast Security | Contrast (limited) | Contrast |

### 3.5 SCA (Software Composition Analysis)
| Web App | Mobile App | Thick Client | API | Cloud-Native | Hybrid App |
|---|---|---|---|---|---|
| Snyk, Dependabot, Mend | Snyk, OWASP Dep-Check | Black Duck, Snyk | Snyk, Dependabot | Snyk, Trivy | Snyk, Dependabot |

### 3.6 RASP (Runtime Application Self-Protection)
| Web App | Mobile App | Thick Client | API | Cloud-Native | Hybrid App |
|---|---|---|---|---|---|
| Contrast, Signal Sciences | Guardsquare | — | Contrast, Imperva | AWS WAF (partial) | Contrast (limited) |

### 3.7 VAPT (Vulnerability Assessment & Penetration Testing)
| Web App | Mobile App | Thick Client | API | Cloud-Native | Hybrid App |
|---|---|---|---|---|---|
| Burp, Nuclei, SQLMap, Nmap | Frida, Objection, Burp | Ghidra, x64dbg, Wireshark | Burp, Postman, Nuclei | ScoutSuite + Burp | Burp, Frida |

### 3.8 Vulnerability Management
| Web App | Mobile App | Thick Client | API | Cloud-Native | Hybrid App |
|---|---|---|---|---|---|
| Qualys, Tenable, Rapid7 | Qualys, NowSecure | Qualys, Tenable | Qualys, Tenable | Wiz, Prisma Cloud | Qualys, Tenable |

### 3.9 Secret Scanning
| Web App | Mobile App | Thick Client | API | Cloud-Native | Hybrid App |
|---|---|---|---|---|---|
| GitGuardian, TruffleHog | GitGuardian, TruffleHog | TruffleHog, custom scripts | GitGuardian, TruffleHog | GitGuardian, TruffleHog | GitGuardian, TruffleHog |

### 3.10 Secure Code Review (Manual)
| Web App | Mobile App | Thick Client | API | Cloud-Native | Hybrid App |
|---|---|---|---|---|---|
| Manual + Semgrep | Manual + MobSF | Manual + dnSpy | Manual + Semgrep | Manual + Semgrep | Manual + Semgrep |

### 3.11 Fuzzing
| Web App | Mobile App | Thick Client | API | Cloud-Native | Hybrid App |
|---|---|---|---|---|---|
| Burp Intruder, AFL | Peach (limited) | WinAFL, Peach | RESTler, Schemathesis | RESTler, custom | Burp Intruder |

### 3.12 Configuration Review
| Web App | Mobile App | Thick Client | API | Cloud-Native | Hybrid App |
|---|---|---|---|---|---|
| ScoutSuite, Lynis | Mobile config audit | Registry/file analysis | API gateway review | Prowler, ScoutSuite | App + container config |

### 3.13 Reverse Engineering
| Web App | Mobile App | Thick Client | API | Cloud-Native | Hybrid App |
|---|---|---|---|---|---|
| — | JADX, Hopper, Frida, Ghidra | dnSpy, Ghidra, IDA, x64dbg | — | — | JADX, Ghidra (native layer) |

### 3.14 DevSecOps (CI/CD Integration)
| Web App | Mobile App | Thick Client | API | Cloud-Native | Hybrid App |
|---|---|---|---|---|---|
| GitHub Actions, GitLab CI | Fastlane + plugins | Jenkins + custom | GitHub Actions | GitHub Actions, ArgoCD | GitHub Actions |

### 3.15 IaC Security Scanning
| Web App | Mobile App | Thick Client | API | Cloud-Native | Hybrid App |
|---|---|---|---|---|---|
| — | — | — | — | Checkov, KICS, Terraform Scan | — |

### 3.16 Container/Image Scanning
| Web App | Mobile App | Thick Client | API | Cloud-Native | Hybrid App |
|---|---|---|---|---|---|
| — | — | — | — | Trivy, Aqua, Grype | Trivy (if containerized) |

### 3.17 CSPM (Cloud Security Posture Management)
| Web App | Mobile App | Thick Client | API | Cloud-Native | Hybrid App |
|---|---|---|---|---|---|
| — | — | — | — | Wiz, Prisma Cloud, AWS Security Hub | — |

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

## 6. WHAT'S UNIQUE TO EACH APP TYPE

### 6.1 Web Applications
- Most common app type in AppSec
- Highest volume of testing engagements
- Standard: OWASP Top 10
- Key Risks: XSS, SQLi, CSRF, SSRF, Broken Auth

### 6.2 Mobile Applications
- Native (Swift/Kotlin) and Hybrid (React Native, Flutter)
- Standard: OWASP Mobile Top 10
- Key Risks: Insecure data storage, reverse engineering, certificate pinning bypass, IPC flaws

### 6.3 Thick Client (Desktop)
- Two-tier (standalone) or three-tier (client → server → DB)
- Key Risks: DLL hijacking, memory manipulation, local storage, insecure updates, hardcoded creds

### 6.4 API
- REST, SOAP, GraphQL, gRPC
- Standard: OWASP API Top 10
- Key Risks: BOLA, broken auth, mass assignment, injection, rate limiting bypass

### 6.5 Cloud-Native / Serverless
- Lambda, Azure Functions, K8s, Docker microservices
- Standard: OWASP Serverless Top 10, CIS Benchmarks
- Key Risks: Misconfigurations, over-permissive IAM, event injection, container escape, cold start abuse

### 6.6 Hybrid Applications
- Web tech wrapped in native shells (Electron, Cordova, Tauri, React Native)
- Examples: Slack, VS Code, Teams desktop
- Key Risks: Combined web + native attack surface, insecure JS↔Native bridges, Node.js vulnerabilities in Electron

---

## 7. SECURITY STANDARDS & FRAMEWORKS REFERENCE

| Standard | Applies To |
|---|---|
| OWASP Top 10 | Web Apps, Hybrid |
| OWASP Mobile Top 10 | Mobile Apps |
| OWASP API Top 10 | APIs |
| OWASP Serverless Top 10 | Cloud-Native/Serverless |
| OWASP IoT Top 10 | Embedded/IoT (extended) |
| OWASP LLM Top 10 | AI/ML Applications (extended) |
| CIS Benchmarks | Cloud-Native, Infrastructure |
| NIST CSF | All types |
| ISO 27001 | All types |
| PCI-DSS | Financial apps (all types) |
| HIPAA | Healthcare apps (all types) |
| GDPR | Apps handling EU user data |
| SOC 2 | SaaS / Enterprise apps |

---

## 8. FINAL SUMMARY

- Core App Types: 6
- Total Security Activities: 18
- Universal (applies to all 6): 11
- Cloud-Native Specific: 3 (IaC Scanning, Container Scanning, CSPM)
- Mobile/Thick Client Specific: 1 (Reverse Engineering)
- Partial/Varies: 3 (DAST, IAST, RASP)

---

## Document Information
- Subject: Application Security (AppSec) — Complete Breakdown
- Version: 1.0
- Date: May 2026
