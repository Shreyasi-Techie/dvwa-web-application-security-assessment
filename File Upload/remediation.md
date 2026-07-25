# File Upload Vulnerability – Remediation

## Overview

The identified vulnerability was caused by insufficient validation and handling of uploaded files. An attacker was able to upload a server-side executable file, which could then be accessed and executed by the web server.

The following security controls should be implemented to prevent exploitation.

---

## 1. Use a Strict File-Type Allowlist

Only allow file types that are explicitly required by the application.

For example:

```text
.jpg
.jpeg
.png
.gif
