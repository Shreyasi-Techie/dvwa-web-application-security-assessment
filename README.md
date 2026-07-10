# 🔐 DVWA Web Application Security Assessment 

![Platform](https://img.shields.io/badge/Platform-Kali%20Linux-blue)
![Target](https://img.shields.io/badge/Application-DVWA-red)
![Tools](https://img.shields.io/badge/Tools-Burp%20Suite%20%7C%20Browser-green)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## Overview

This repository contains a practical **Web Application Vulnerability Assessment and Penetration Testing (VAPT)** of the **Damn Vulnerable Web Application (DVWA)** conducted in an isolated laboratory environment.

The assessment focuses on identifying, validating, documenting, and recommending remediation for common web application vulnerabilities using industry-standard tools and manual testing techniques.

Each vulnerability has been documented independently with detailed findings, supporting evidence, remediation guidance, and client-style assessment reports.

---

## Objectives

- Identify common web application vulnerabilities
- Analyze HTTP requests and responses
- Validate vulnerabilities through manual testing
- Assess the security impact of identified issues
- Document findings following professional VAPT reporting practices
- Recommend secure coding and mitigation strategies

---

## Assessment Environment

| Component | Details |
|-----------|---------|
| Target Application | Damn Vulnerable Web Application (DVWA) |
| Operating System | Kali Linux |
| Web Server | Apache |
| Database | MySQL |
| Proxy Tool | Burp Suite Community Edition |
| Browser | Firefox |
| Additional Tools | Netcat |

---

# Vulnerabilities Assessed

## 1. SQL Injection

**Severity:** High

The SQL Injection assessment demonstrated how insufficient validation of user input can allow attackers to manipulate backend SQL queries.

### Activities Performed

- Captured HTTP requests using Burp Suite
- Performed manual SQL Injection testing
- Executed UNION-based SQL Injection
- Enumerated database information
- Retrieved user records from the database
- Assessed application response behavior
- Documented findings and remediation recommendations

**Skills Demonstrated**

- SQL Injection Testing
- Database Enumeration
- Burp Suite Proxy & Repeater
- HTTP Request Analysis
- Manual Vulnerability Validation

**Documentation**

```
sql-injection/
```

---

## 2. Reflected Cross-Site Scripting (XSS)

**Severity:** High

The Reflected XSS assessment verified that user-supplied input was reflected into the application's response without proper output encoding, allowing arbitrary JavaScript execution within the browser.

### Activities Performed

- Captured and modified HTTP requests
- Executed JavaScript payloads
- Verified reflected input
- Demonstrated browser-side script execution
- Analyzed server responses
- Documented findings and mitigation strategies

**Skills Demonstrated**

- Cross-Site Scripting (XSS) Testing
- HTTP Request & Response Analysis
- Burp Suite Proxy & Repeater
- Client-Side Security Testing
- Manual Vulnerability Validation

**Documentation**

```
reflected-xss/
```

---

## 3. Command Injection

**Severity:** Critical

The Command Injection assessment demonstrated how unsanitized user input can be executed as operating system commands, potentially leading to complete server compromise.

### Activities Performed

- Captured HTTP POST requests
- Modified request parameters
- Verified operating system command execution
- Retrieved server information
- Accessed sensitive system files
- Established a reverse shell within the controlled lab environment
- Documented findings and remediation recommendations

**Skills Demonstrated**

- Command Injection Testing
- Burp Suite Proxy & Repeater
- Linux Command Line
- HTTP Request Analysis
- Reverse Shell Fundamentals
- Security Documentation

**Documentation**

```
command-injection/
```

---

# Repository Structure

```
dvwa-web-application-security-assessment/

├── README.md
│
├── sql-injection/
│   ├── README.md
│   ├── findings.md
│   ├── remediation.md
│   ├── report.md
│   ├── screenshots.md
│   └── screenshots/
│
├── reflected-xss/
│   ├── README.md
│   ├── findings.md
│   ├── remediation.md
│   ├── report.md
│   ├── screenshots.md
│   └── screenshots/
│
├── command-injection/
    ├── README.md
    ├── findings.md
    ├── remediation.md
    ├── report.md
    ├── screenshots.md
    └── screenshots/

```

---

# Tools Used

- Burp Suite Community Edition
- Firefox Browser
- Kali Linux
- DVWA
- Apache
- MySQL
- Netcat

---

# Skills Demonstrated

- Web Application Penetration Testing (VAPT)
- Vulnerability Assessment
- Manual Security Testing
- HTTP Request & Response Analysis
- Burp Suite Proxy & Repeater
- SQL Injection Testing
- Cross-Site Scripting (XSS) Testing
- Command Injection Testing
- Database Enumeration
- Linux Fundamentals
- Technical Documentation
- Vulnerability Reporting
- OWASP Top 10 Awareness

---

# Learning Outcomes

This project provided practical experience in:

- Identifying common web application vulnerabilities
- Understanding insecure coding practices
- Intercepting and modifying HTTP traffic
- Assessing the security impact of vulnerabilities
- Preparing professional penetration testing documentation
- Recommending secure coding practices and remediation techniques

---

# Disclaimer

This assessment was conducted **only within an authorized DVWA laboratory environment** for educational purposes. All testing was performed against an intentionally vulnerable application running in a local virtual machine. No unauthorized systems or production environments were targeted.

---
