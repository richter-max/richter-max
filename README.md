# Hello, I'm Max

<a href="https://www.linkedin.com/in/maximilian-richter-40697a298/">
  <img src="https://img.shields.io/badge/-LinkedIn-0072b1?&style=for-the-badge&logo=linkedin&logoColor=white" />
</a>

I'm a German IT Specialist in Application Development, I completed my vocational Training January 2026 as Software Developer and will continue  with a **dual study program starting October 2026**.

My core interests are **cybersecurity** and **secure software engineering**, with a strong focus on
understanding systems end-to-end, identifying realistic weaknesses, and building **practical security tooling**
around visibility, risk, and control.

---

## Current Focus

I focus on **hands-on security engineering**, especially:

- understanding real-world attack surfaces of cloud and SaaS systems
- transport security and configuration weaknesses
- deterministic, explainable security signals instead of black-box tooling
- building small, reliable tools that support consistent decision-making

I strongly prefer **practical systems** over theoretical abstractions.

---

## 🔐 Flagship Project — Attack Surface Scanner for SaaS

**Non-intrusive attack surface and transport security scanner** designed for real-world SaaS environments.

This project is intentionally built as a **security engineering signal** (not a pentesting tool) and reflects
how security teams reason about **exposure, misconfiguration, and prioritization**.

**Key aspects:**
- Passive asset discovery via **Certificate Transparency logs**
- Deterministic fallback behavior for **enterprise proxy-restricted networks**
- DNS resolution + HTTP/HTTPS probing (redirect-aware)
- Security checks:
  - Deprecated TLS versions (1.0 / 1.1)
  - TLS certificate expiration
  - HTTP security headers (HSTS, CSP, X-Frame-Options, nosniff, Referrer-Policy)
- **Deterministic, explainable risk scoring** (low / medium / high)
- Outputs:
  - Structured JSON artifacts
  - Rich CLI summary for fast triage
- Engineering quality:
  - Typed data models (Pydantic)
  - Unit tests + GitHub Actions CI
  - Python 3.10–3.12 compatibility

**Repository:**  
https://github.com/cleamax/attack-surface-scanner

**Documentation:**  
- Threat Model  
- Design Decisions

This project is designed to be discussed in **security engineering interviews**.

---

## Skills (selected)

### Security & Systems
- Cloud security fundamentals (AWS, IAM, logging, detection)
- Attack surface analysis & threat modeling
- Web security & transport-layer security
- Incident response concepts & log analysis

### Software Engineering
- Secure backend & web application design
- Automation-focused internal tooling
- Clear, maintainable codebases
- Deterministic systems with explainable outputs

### Blockchain Security
- Solidity smart contract development
- Vulnerability analysis & exploit simulation
- Secure design patterns (OpenZeppelin)

---

## Tools & Technologies

### Cloud & IaC
<div>
  <img src="https://img.shields.io/badge/-Terraform-623CE4?&style=for-the-badge&logo=terraform&logoColor=white" />
  <img src="https://img.shields.io/badge/-AWS-232F3E?&style=for-the-badge&logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/-CloudTrail-FF9900?&style=for-the-badge&logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/-GuardDuty-FF4F00?&style=for-the-badge&logo=amazonaws&logoColor=white" />
</div>

### Monitoring & Detection
<div>
  <img src="https://img.shields.io/badge/-Wireshark-1679A7?&style=for-the-badge&logo=Wireshark&logoColor=white" />
  <img src="https://img.shields.io/badge/-Suricata-EF3B2D?&style=for-the-badge&logo=Suricata&logoColor=white" />
  <img src="https://img.shields.io/badge/-Zeek-777BB4?&style=for-the-badge&logo=Zeek&logoColor=white" />
</div>

### SIEM / IR
<div>
  <img src="https://img.shields.io/badge/-Microsoft_Sentinel-0078D4?&style=for-the-badge&logo=Microsoft&logoColor=white" />
  <img src="https://img.shields.io/badge/-Splunk-000000?&style=for-the-badge&logo=Splunk&logoColor=white" />
  <img src="https://img.shields.io/badge/-Elastic-005571?&style=for-the-badge&logo=Elastic&logoColor=white" />
</div>

### Blockchain
<div>
  <img src="https://img.shields.io/badge/-Solidity-363636?&style=for-the-badge&logo=solidity&logoColor=white" />
  <img src="https://img.shields.io/badge/-OpenZeppelin-4C8BF5?&style=for-the-badge&logo=openzeppelin&logoColor=white" />
  <img src="https://img.shields.io/badge/-Foundry-FF9900?&style=for-the-badge&logo=rust&logoColor=white" />
</div>

---

## Other Projects

### Security & Labs
- **Cloud Pentest Lab** — intentionally vulnerable AWS configurations with detection strategies  
- **SOC Automation Project** — automated SIEM / SOAR workflows  
- **SecCheck** — lightweight CI-focused web security scanner  
- **Blockchain Attack Playground** — vulnerable smart contracts with exploit write-ups  

### Personal Tools (PWA)
- **Arise** — personal performance and consistency tracking  
- **Candle** — rule-based trading execution & discipline enforcement  

These tools are private-first, internal systems that I actively use.

---

## Contact

📧 **max.richter.dev@proton.me**

<a href="https://www.linkedin.com/in/maximilian-richter-40697a298/">
  <img src="https://img.shields.io/badge/-LinkedIn-0072b1?&style=for-the-badge&logo=linkedin&logoColor=white" />
</a>

<a href="https://github.com/cleamax">
  <img src="https://img.shields.io/badge/-GitHub-181717?&style=for-the-badge&logo=github&logoColor=white" />
</a>

> All testing and experimentation is performed legally and only with explicit consent.
