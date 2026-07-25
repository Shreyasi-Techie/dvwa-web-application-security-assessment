# Vulnerability Assessment Report

## Unrestricted File Upload

---

## 1. Executive Summary

During the security assessment of the DVWA application hosted on Metasploitable 2, an **Unrestricted File Upload** vulnerability was identified.

The application allowed a server-side PHP file to be uploaded without adequate validation. The uploaded file was subsequently accessed and executed by the web server, resulting in command execution with the privileges of the web server account.

Further testing in the isolated laboratory environment demonstrated the potential to establish a reverse shell and perform basic system and network enumeration.

**Severity:** Critical

---

## 2. Assessment Details

| Field                    | Details                                  |
| ------------------------ | ---------------------------------------- |
| Target Application       | Damn Vulnerable Web Application (DVWA)   |
| Target Platform          | Metasploitable 2                         |
| Testing Platform         | Kali Linux                               |
| Vulnerable Functionality | File Upload                              |
| Tools Used               | Burp Suite, Metasploit Framework         |
| Assessment Type          | Web Application Vulnerability Assessment |
| Environment              | Isolated Authorized Laboratory           |

---

## 3. Vulnerability Description

The file upload functionality did not adequately validate uploaded files.

Insufficient validation of file extensions, MIME types, file contents, and server-side execution permissions allowed a server-side PHP file to be uploaded and processed by the web server.

Because the uploaded file was stored in a web-accessible location where server-side code execution was permitted, the file could be accessed through the application and executed.

---

## 4. Proof of Concept

The following testing process was performed:

1. A PHP test file was created for controlled validation.
2. The DVWA file upload functionality was accessed.
3. The upload request was intercepted using Burp Suite.
4. The request and uploaded file metadata were inspected.
5. The upload request was modified to demonstrate inadequate reliance on client-controlled file information.
6. The file was successfully uploaded to the target application.
7. The uploaded file was accessed through the web application.
8. Server-side code execution was confirmed.
9. A reverse shell was established within the isolated lab environment.
10. Basic system and network enumeration was performed.

---

## 5. Impact

Successful exploitation of this vulnerability may allow an attacker to:

* Upload arbitrary files to the server.
* Execute server-side code.
* Execute commands with web-server privileges.
* Obtain a remote shell.
* Access sensitive information.
* Perform further reconnaissance and post-exploitation activities.

If successfully exploited against a production application, this vulnerability could potentially lead to significant compromise of the affected server.

---

## 6. Technical Evidence

The following evidence was collected during the assessment:

* PHP test file creation.
* File upload functionality.
* Burp Suite request interception.
* Inspection and modification of upload request parameters.
* Successful file upload.
* Uploaded file execution.
* Command shell access.
* Reverse shell establishment.
* Interactive TTY shell.
* System information enumeration.
* Network configuration enumeration.

Supporting evidence is available in:

`./screenshots/`

---

## 7. Root Cause

The vulnerability was caused by insufficient server-side validation and insecure handling of uploaded files.

Potential contributing factors include:

* Inadequate file type validation.
* Reliance on client-controlled MIME type information.
* Allowing executable server-side files.
* Storing uploaded files in a web-accessible directory.
* Permitting server-side script execution in the upload directory.
* Insufficient file and directory access controls.

---

## 8. Remediation Recommendations

The following controls are recommended:

1. Implement a strict server-side allowlist of permitted file types.
2. Validate actual file contents and file signatures.
3. Do not rely solely on file extensions or client-supplied MIME types.
4. Disable server-side script execution in upload directories.
5. Store uploaded files outside the web root where possible.
6. Generate random server-side filenames.
7. Prevent path traversal and filename manipulation.
8. Apply least-privilege permissions.
9. Enforce appropriate file size limits.
10. Log and monitor file upload activity.

---

## 9. Risk Rating

| Category         | Rating   |
| ---------------- | -------- |
| Confidentiality  | High     |
| Integrity        | High     |
| Availability     | High     |
| Overall Severity | Critical |

The overall severity is rated **Critical** because successful exploitation may allow arbitrary server-side code execution and potentially lead to further compromise of the target system.

---

## 10. Conclusion

The assessment confirmed that inadequate file upload validation allowed a server-side PHP file to be uploaded and executed by the web server.

The vulnerability was successfully validated in an isolated DVWA and Metasploitable 2 laboratory environment. The assessment demonstrated the potential progression from unrestricted file upload to server-side code execution, command execution, reverse shell access, and basic system enumeration.

The issue should be remediated by implementing strict server-side file validation, preventing script execution within upload directories, and applying appropriate file storage and access controls.

---
