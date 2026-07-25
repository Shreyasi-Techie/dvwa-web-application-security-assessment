# File Upload Vulnerability — Evidence

This document provides a brief description of the screenshots collected during the File Upload vulnerability assessment.

The assessment was performed in an isolated laboratory environment using DVWA and Metasploitable 2.

---

## 1. Shell Payload Creation

<img width="943" height="114" alt="image" src="https://github.com/user-attachments/assets/4a22b58a-0942-4e73-884d-b4ed32a5552a" />


A PHP test file containing server-side command execution functionality was created for controlled vulnerability validation.

---

## 2. File Upload Interface

<img width="660" height="610" alt="image" src="https://github.com/user-attachments/assets/77296b79-1588-49d8-8773-235f8f9b8420" />


The DVWA File Upload functionality was accessed and prepared for testing.

---

## 3. Successful File Upload

<img width="724" height="258" alt="image" src="https://github.com/user-attachments/assets/6dab31aa-c6b4-4676-9838-478b79e0b66e" />


The test file was successfully uploaded by the application, demonstrating insufficient restrictions on uploaded file types.

---

## 4. Uploaded File Execution

<img width="961" height="193" alt="image" src="https://github.com/user-attachments/assets/bfed7796-0c91-4f52-a9a6-c28bfcab1c9b" />


The uploaded file was accessed through the web application and server-side execution was confirmed in the controlled lab environment.

---

## 5. Medium Security Level

<img width="403" height="247" alt="image" src="https://github.com/user-attachments/assets/c3167e98-97ab-43ce-842d-c1134a11c397" />


The application security configuration was reviewed while testing the file upload functionality under a different security level.

---

## 6. Burp Suite Upload Request

<img width="753" height="678" alt="image" src="https://github.com/user-attachments/assets/5c6c9eea-45bc-4416-9620-a71f51a74ed3" />


The file upload request was intercepted and analyzed using Burp Suite.

The request used the `multipart/form-data` format and contained the uploaded file.

---

## 7. Modified Content Type

<img width="591" height="114" alt="image" src="https://github.com/user-attachments/assets/e2e01b4f-179b-4854-9b77-caa00ec981bb" />


The uploaded file's client-supplied content type was modified during testing to demonstrate the importance of performing validation on the server rather than trusting client-controlled headers.

---

## 8. File Uploaded Through Burp Suite

<img width="690" height="205" alt="image" src="https://github.com/user-attachments/assets/1d67f3e5-44cb-47aa-ada8-127c0713b5cf" />


The modified upload request was forwarded and the file was successfully accepted by the application.

---

## 9. Metasploit Handler Setup

<img width="706" height="126" alt="image" src="https://github.com/user-attachments/assets/6e92d44d-454f-4b6e-b59d-a063034c41e1" />


Metasploit was configured in the controlled lab environment to receive the reverse shell connection.

---

## 10. Reverse Shell Handler

<img width="904" height="76" alt="image" src="https://github.com/user-attachments/assets/b5cf0ec6-922d-4ac4-a933-4e88e07b74c8" />


The required listener and handler configuration was prepared on the Kali Linux testing machine.

---

## 11. Command Shell Opened

<img width="1456" height="225" alt="image" src="https://github.com/user-attachments/assets/d3e31b60-838e-4269-a5b5-de8a413891cd" />


A command shell was successfully obtained from the target system, demonstrating the potential impact of the file upload vulnerability.

---

## 12. Interactive TTY Shell

<img width="948" height="217" alt="image" src="https://github.com/user-attachments/assets/891fd87f-1aa2-4f72-985a-519d7c953c91" />


An interactive TTY shell was established to improve command-line interaction with the target system.

---

## 13. System Information Enumeration

<img width="1005" height="339" alt="image" src="https://github.com/user-attachments/assets/96f16930-9215-4ee4-9d83-ff675eaa8606" />


Basic system information was enumerated after obtaining command execution on the target.

---

## 14. Network Configuration Enumeration

<img width="1273" height="715" alt="image" src="https://github.com/user-attachments/assets/b97b57ec-3cf8-4357-9961-e3b4e0bdcaef" />


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
