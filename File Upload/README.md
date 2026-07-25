# File Upload Vulnerability

## Overview

This section documents the exploitation of a file upload vulnerability in **Damn Vulnerable Web Application (DVWA)** running on **Metasploitable 2**.

The vulnerability occurs when an application fails to properly validate uploaded files, allowing an attacker to upload a server-side executable file. In this lab, a PHP file was uploaded and successfully executed by the web server.

---

## Testing Environment

- **Attacker:** Kali Linux
- **Target:** Metasploitable 2
- **Application:** DVWA
- **Tools:** Burp Suite and Metasploit Framework

---

## Assessment Summary

During testing, a PHP file containing a command-execution payload was created and uploaded through the DVWA File Upload functionality.

The upload request was intercepted using **Burp Suite**, where the file's MIME type was modified to demonstrate inadequate server-side validation. The file was then successfully uploaded to the target server.

After accessing the uploaded file, command execution was confirmed on the target system. A reverse shell was subsequently established, providing a command shell running with `www-data` privileges.

Basic post-exploitation enumeration was then performed, including:

- Current user identification
- Operating system identification
- Uploaded file verification
- Network interface enumeration
- Routing table enumeration

---

## Impact

Successful exploitation of this vulnerability can allow an attacker to:

- Upload unauthorized files
- Execute server-side code
- Execute commands on the target system
- Obtain a remote shell
- Perform further system reconnaissance

The impact can be **Critical** when arbitrary server-side code execution is possible.

---

## Evidence

Screenshots documenting the testing process are available in the [`screenshots`](./screenshots/) directory.

The evidence includes:

- File creation
- File upload
- Burp Suite request interception
- MIME type modification
- Successful upload
- Command execution
- Reverse shell establishment
- Interactive shell access
- System and network enumeration

---

## Remediation

Recommended security controls include:

- Validate file extensions using a strict allowlist.
- Validate the actual contents of uploaded files.
- Do not rely solely on the client-supplied MIME type.
- Prevent execution of server-side scripts in upload directories.
- Store uploaded files outside the web root where possible.
- Rename uploaded files using server-generated filenames.
- Apply least-privilege permissions to the web server.

---

## Disclaimer

This assessment was performed in an intentionally vulnerable and isolated laboratory environment using DVWA and Metasploitable 2 for educational and cybersecurity training purposes.
