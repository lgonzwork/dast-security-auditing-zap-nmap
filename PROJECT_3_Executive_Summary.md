# Executive Summary: Integrated DAST & Vulnerability Assessment

### Architecture Overview

The development of this dual-phase DAST security assessment module completes a multi-layered security evaluation strategy—transitioning from network-level reconnaissance and service auditing to automated, cloud-native dynamic application security testing.

- **Network Reconnaissance & Surface Mapping (Project 1):** Utilization of Nmap CLI to perform port enumeration, service version fingerprinting, and operating system identification—establishing an audited network baseline before launching web-level attacks.
- **Automated CI/CD DAST Scanning (Project 2):** Integration of OWASP ZAP within GitHub Actions pipelines to execute automated spider crawling, route discovery, and active attack payloads (SQLi, XSS) seamlessly on cloud runners—enforcing Shift-Left DevSecOps principles.
- **Vulnerability Triage & Risk Mitigation:** Automated extraction and consolidation of raw security findings into downloadable HTML artifacts, enabling immediate risk categorization (High, Medium, Low, Informational) and targeted remediation workflows.

With this final component, the entire portfolio establishes a complete DevSecOps testing workflow—spanning API functional validation (Postman/Newman), client-side E2E automation (Cypress), and continuous automated security audits (Nmap & OWASP ZAP GitHub Actions).
