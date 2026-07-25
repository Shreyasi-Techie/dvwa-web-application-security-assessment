# Finding: Unrestricted File Upload

## Finding ID

FILE-UPLOAD-001

## Vulnerability

Unrestricted File Upload

## Severity

Critical

## Description

The DVWA file upload functionality does not adequately validate uploaded files. During testing, a PHP file containing server-side command execution functionality was successfully uploaded to the target web application.

The uploaded file was stored in a web-accessible directory and could subsequently be accessed through the browser. Since PHP execution was permitted in the upload location, the uploaded file was executed by the server.

This resulted in command execution with the privileges of the web server account.

---

## Affected Functionality

**DVWA File Upload**

---

## Proof of Concept

Testing was performed in an isolated DVWA and Metasploitable 2 laboratory environment.

The assessment demonstrated that:

1. A PHP test file was created.
2. The file was submitted through the file upload functionality.
3. The upload request was intercepted using Burp Suite.
4. The uploaded file's MIME type was modified to demonstrate insufficient validation.
5. The file was successfully uploaded to the server.
6. The uploaded file was accessed through the web application.
7. Command execution was confirmed on the target system.
8. A reverse shell was established in the controlled lab environment.
9. Basic system and network enumeration was performed.

---

## Impact

Successful exploitation may allow an attacker to:

- Upload arbitrary files to the server.
- Execute server-side code.
- Execute commands with web-server privileges.
- Obtain a remote shell.
- Access sensitive information.
- Perform further reconnaissance and post-exploitation activities.

The vulnerability can have a **Critical** impact when arbitrary server-side code execution is possible.

---

## Evidence

The following evidence was collected:

- Creation of a PHP test file.
- Successful file upload through DVWA.
- Burp Suite capture of the upload request.
- Modification of the uploaded file's MIME type.
- Successful upload confirmation.
- Execution of the uploaded file.
- Command execution as `www-data`.
- Reverse shell establishment.
- Interactive TTY shell.
- System information enumeration.
- Network configuration and routing enumeration.

Detailed screenshots are available in:

```text
./screenshots/
