# File Upload Vulnerability — Evidence

This document provides a brief description of the screenshots collected during the File Upload vulnerability assessment.

The assessment was performed in an isolated laboratory environment using DVWA and Metasploitable 2.

---

## 1. Shell Payload Creation

**File:** `1)shell_payload_creation.png`

A PHP test file containing server-side command execution functionality was created for controlled vulnerability validation.

---

## 2. File Upload Interface

**File:** `2)file_upload_interface.png`

The DVWA File Upload functionality was accessed and prepared for testing.

---

## 3. Successful File Upload

**File:** `3) successful_file_upload.png`

The test file was successfully uploaded by the application, demonstrating insufficient restrictions on uploaded file types.

---

## 4. Uploaded File Execution

**File:** `4) uploaded_shell_execution.png`

The uploaded file was accessed through the web application and server-side execution was confirmed in the controlled lab environment.

---

## 5. Medium Security Level

**File:** `5) security_level_medium.png`

The application security configuration was reviewed while testing the file upload functionality under a different security level.

---

## 6. Burp Suite Upload Request

**File:** `6) burp_upload_request.png`

The file upload request was intercepted and analyzed using Burp Suite.

The request used the `multipart/form-data` format and contained the uploaded file.

---

## 7. Modified Content Type

**File:** `7) modified_content_type.png`

The uploaded file's client-supplied content type was modified during testing to demonstrate the importance of performing validation on the server rather than trusting client-controlled headers.

---

## 8. File Uploaded Through Burp Suite

**File:** `8) burp_upload_success.png`

The modified upload request was forwarded and the file was successfully accepted by the application.

---

## 9. Metasploit Handler Setup

**File:** `9) metasploit_handler_setup.png`

Metasploit was configured in the controlled lab environment to receive the reverse shell connection.

---

## 10. Reverse Shell Handler

**File:** `10) reverse_shell_handler.png`

The required listener and handler configuration was prepared on the Kali Linux testing machine.

---

## 11. Command Shell Opened

**File:** `11) command_shell_opened.png`

A command shell was successfully obtained from the target system, demonstrating the potential impact of the file upload vulnerability.

---

## 12. Interactive TTY Shell

**File:** `12) interactive_tty_shell.png`

An interactive TTY shell was established to improve command-line interaction with the target system.

---

## 13. System Information Enumeration

**File:** `13) system_information_enumeration.png`

Basic system information was enumerated after obtaining command execution on the target.

---

## 14. Network Configuration Enumeration

**File:** `14) network_configuration_enumeration.png`

The target's network configuration and routing information were examined as part of basic post-exploitation enumeration.

---

## Assessment Summary

The collected evidence demonstrates the progression from:

```text
File Creation
      ↓
File Upload
      ↓
Upload Request Interception
      ↓
Request Modification
      ↓
Successful File Upload
      ↓
Server-Side File Execution
      ↓
Command Execution
      ↓
Reverse Shell
      ↓
System & Network Enumeration
```

Together, these screenshots support the finding that insufficient file upload validation can lead to server-side code execution and further compromise of the target system.

---

## Disclaimer

All testing was performed in an intentionally vulnerable and isolated laboratory environment using DVWA and Metasploitable 2 for educational and cybersecurity training purposes.
