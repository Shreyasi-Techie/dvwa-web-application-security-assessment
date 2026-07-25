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

## Vulnerabilities Assessed

### 1. SQL Injection

Tested the application's handling of user-supplied input and demonstrated SQL query manipulation through manual SQL Injection techniques.

**Key areas covered:**
- SQL Injection validation
- HTTP request analysis using Burp Suite
- Database enumeration
- UNION-based SQL Injection
- Impact assessment and remediation

📁 [View SQL Injection Assessment](SQL injection)

---

### 2. Reflected Cross-Site Scripting (XSS)

Assessed whether user-controlled input was reflected without proper output encoding, allowing JavaScript execution within the browser.

**Key areas covered:**
- Reflected XSS validation
- JavaScript execution
- HTTP request and response analysis
- Impact assessment and remediation

📁 [View Reflected XSS Assessment](./XSS-Reflected/)

---

### 3. Command Injection

Tested whether user-controlled input could be used to execute operating system commands on the underlying server.

**Key areas covered:**
- Command injection validation
- HTTP POST request analysis
- Operating system command execution
- Reverse shell demonstration in a controlled lab environment
- Impact assessment and remediation

📁 [View Command Injection Assessment](./Command-Injection/)

---

### 4. File Upload

Assessed the application's file upload functionality and demonstrated the security impact of insufficient validation of uploaded files.

**Key areas covered:**
- File upload validation testing
- HTTP request interception using Burp Suite
- MIME type manipulation
- Server-side file execution
- Command execution and reverse shell demonstration in a controlled lab environment
- Impact assessment and remediation

📁 [View File Upload Assessment](./File-Upload/)

---

## Tools Used

- Kali Linux
- Burp Suite Community Edition
- DVWA
- Metasploitable 2
- Metasploit Framework
- Netcat
- Firefox

---

## Skills Demonstrated

- Web Application VAPT
- Manual Vulnerability Assessment
- HTTP Request and Response Analysis
- Burp Suite Proxy and Repeater
- SQL Injection Testing
- Reflected XSS Testing
- Command Injection Testing
- File Upload Vulnerability Testing
- Linux Fundamentals
- Vulnerability Documentation and Reporting
- Remediation Recommendations

---

## Disclaimer

This assessment was conducted only within an authorized and isolated laboratory environment using intentionally vulnerable applications for educational and cybersecurity training purposes. No unauthorized systems or production environments were targeted.
