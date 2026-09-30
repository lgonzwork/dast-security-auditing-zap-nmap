# Project 1: Network Reconnaissance & Port Scanning (Nmap CLI)

## Objective

Execute automated network reconnaissance and target enumeration using Nmap CLI to identify active hosts, exposed TCP/UDP ports, running service versions, and target operating systems—establishing a baseline network attack surface audit prior to web application scanning.

---

## Test Specifications

- **Scanner Engine:** Nmap (Network Mapper CLI)
- **Target Environment:** `scanme.nmap.org` / Local Infrastructure Test Bed (`127.0.0.1`)
- **Scope:** Host Discovery, SYN Stealth Scan, Service/Version Detection, OS Fingerprinting, and Default NSE Script Execution (`sC -sV`)
- **Setup Instructions:** Initialize network logging directories, configure administrative privileges, and execute CLI command flags.

---

## Setup Instructions

1. Open PowerShell as Administrator and navigate to your user home directory:

```powershell
cd C:\Users\lugon
```

1. Create and enter a dedicated directory for network security assessment logs:

```powershell
New-Item -ItemType Directory -Force -Path ".\nmap-assessment-results"
```

1. Verify Nmap CLI installation:

```powershell
nmap --version
```

---

## Command Execution & Scan Script

```powershell
# Navigate and initialize working directory
cd C:\Users\lugon
New-Item -ItemType Directory -Force -Path ".\nmap-assessment-results"
cd .\nmap-assessment-results

# Verify Nmap CLI installation
nmap --version

# Execute comprehensive network reconnaissance scan
nmap -sS -sV -sC -O -p 22,80,443,8080 -oA network_recon_audit scanme.nmap.org
```

---

## Expected Test Results

- **Host State:** Host is up (`0.10s` latency)
- **Network Audit Status:** Reconnaissance Audit Complete (PASS)
- **Assertions / Findings Evaluated:**
- PORT 22/tcp OPEN (Service: OpenSSH 6.6.1p1 Ubuntu — SSH Protocol 2.0) — PASS
- PORT 80/tcp OPEN (Service: Apache httpd 2.4.7 — HTTP Web Server "Go ahead and ScanMe!") — PASS
- PORT 443/tcp CLOSED (Service: https — SSL/TLS Interface Inactive) — PASS
- PORT 8080/tcp CLOSED (Service: http-proxy — No unauthorized proxy listener exposed) — PASS


<img width="1910" height="1015" alt="DAST1" src="https://github.com/user-attachments/assets/f5bc3d9c-8186-42d5-bc32-3717cc38f9df" />
