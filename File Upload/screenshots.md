# File Upload Vulnerability — Evidence

This document provides a brief description of the screenshots collected during the File Upload vulnerability assessment.

The assessment was performed in an isolated laboratory environment using DVWA and Metasploitable 2.

---

## 1. Shell Payload Creation

File Upload/screenshots/1) shell_payload_creation.png

A PHP test file containing server-side command execution functionality was created for controlled vulnerability validation.

---

## 2. File Upload Interface

![File Upload Interface](2%29%20file_upload_interface.png)

The DVWA File Upload functionality was accessed and prepared for testing.

---

## 3. Successful File Upload

![File Upload Interface](3%29%20successful_file_upload.png)

The test file was successfully uploaded by the application, demonstrating insufficient restrictions on uploaded file types.

---

## 4. Uploaded File Execution

![File Upload Interface](4%29%20uploaded_shell_execution.png)

The uploaded file was accessed through the web application and server-side execution was confirmed in the controlled lab environment.

---

## 5. Medium Security Level

![File Upload Interface](5%29%20security_level_medium.png)

The application security configuration was reviewed while testing the file upload functionality under a different security level.

---

## 6. Burp Suite Upload Request

![File Upload Interface](6%29%20burp_upload_request.png)

The file upload request was intercepted and analyzed using Burp Suite.

The request used the `multipart/form-data` format and contained the uploaded file.

---

## 7. Modified Content Type

![File Upload Interface](7%29%20modified_content_type.png)

The uploaded file's client-supplied content type was modified during testing to demonstrate the importance of performing validation on the server rather than trusting client-controlled headers.

---

## 8. File Uploaded Through Burp Suite

![File Upload Interface](8%29%20burp_upload_success.png)

The modified upload request was forwarded and the file was successfully accepted by the application.

---

## 9. Metasploit Handler Setup

![File Upload Interface](9%29%20metasploit_handler_setup.png)

Metasploit was configured in the controlled lab environment to receive the reverse shell connection.

---

## 10. Reverse Shell Handler

![File Upload Interface](10%29%20reverse_shell_handler.png)

The required listener and handler configuration was prepared on the Kali Linux testing machine.

---

## 11. Command Shell Opened

![File Upload Interface](11%29%20command_shell_opened.png)

A command shell was successfully obtained from the target system, demonstrating the potential impact of the file upload vulnerability.

---

## 12. Interactive TTY Shell

![File Upload Interface](12%29%20interactive_tty_shell.png)

An interactive TTY shell was established to improve command-line interaction with the target system.

---

## 13. System Information Enumeration

![File Upload Interface](13%29%20system_information_enumeration.png)

Basic system information was enumerated after obtaining command execution on the target.

---

## 14. Network Configuration Enumeration

![File Upload Interface](14%29%20network_configuration_enumeration.png)

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
