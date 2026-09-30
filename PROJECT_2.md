# Project 2: Active DAST Web & API Vulnerability Assessment (OWASP ZAP)

## Objective

Perform dynamic application security testing (DAST) on target web routes using OWASP ZAP to automatically crawl endpoints, execute active attack payloads (SQLi, XSS, DOM-based attacks), and generate structured audit documentation.

## Test Specifications

- **Scanner Engine:** OWASP ZAP (`zaproxy/zap-stable` Docker Image)
- **Target Environment:** `http://scanme.nmap.org` / Target Web Application Staging Environment
- **Scope:** Automated Spider Crawling, Active Attack Scanning, Vulnerability Severity Triage, and HTML Audit Report Generation
- **Execution Environment:** Headless Container Execution via `zap-full-scan.py`

## Setup Instructions

```powershell
# Navigate to assessment workspace directory
cd C:\Users\lugon\nmap-assessment-results

# Pull official OWASP ZAP stable container image
docker pull zaproxy/zap-stable

# Execute containerized full DAST scan and generate HTML audit report
docker run --rm -v C:\Users\lugon\nmap-assessment-results:/zap/wrk/:rw -t zaproxy/zap-stable zap-full-scan.py -t http://scanme.nmap.org -g gen.conf -r OWASP_ZAP_Vulnerability_Report.html
```

## Command Execution & Scan Script

```powershell
docker run --rm -v C:\Users\lugon\nmap-assessment-results:/zap/wrk/:rw -t zaproxy/zap-stable zap-full-scan.py -t <http://scanme.nmap.org> -g gen.conf -r OWASP_ZAP_Vulnerability_Report.html
```

## Expected Test Results

- **Scan Status:** Active DAST Scan Complete (PASS)
- **Execution Summary:** Fully automated spider crawl and active scan completed using `zap-full-scan.py`
- **Assertions / Findings Evaluated:**
    - Active Scan Rule — `SqlInjectionScanRule` — 0 Vulnerabilities Identified — PASS
    - Active Scan Rule — `PersistentXssScanRule` — 0 Vulnerabilities Identified — PASS
    - Active Scan Rule — `DomXssScanRule` — 0 Vulnerabilities Identified — PASS
    - Active Scan Rule — `SqlInjectionOracleTimingScanRule` — 0 Vulnerabilities Identified — PASS
    - Artifact Generation — `OWASP_ZAP_Vulnerability_Report.html` created in output directory — PASS
