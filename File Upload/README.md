# File Upload Vulnerability

## Overview

This section documents the exploitation of an unrestricted file upload vulnerability in **Damn Vulnerable Web Application (DVWA)** running on a Metasploitable 2 virtual machine.

The vulnerability allows an attacker to upload a malicious file containing server-side code to the web server. When the uploaded file is accessed through the browser, the server executes the code, resulting in remote command execution.

The testing was performed in a controlled lab environment using:

- Kali Linux
- Burp Suite
- DVWA
- Metasploitable 2
- Metasploit Framework

---

## Vulnerability Description

The file upload functionality does not properly validate uploaded files.

Insufficient validation of:

- File extensions
- MIME types
- File contents
- Server-side execution permissions

allows an attacker to upload a server-side script disguised as an image or other permitted file type.

In this assessment, a PHP file containing a command-execution payload was uploaded successfully. The uploaded file was then accessed through the web application, allowing commands to be executed on the target system.

---

## Lab Environment

| Component | Details |
|---|---|
| Attacker Machine | Kali Linux |
| Target Machine | Metasploitable 2 |
| Application | DVWA |
| Vulnerable Functionality | File Upload |
| Web Server | Apache |
| Testing Tool | Burp Suite |
| Post-Exploitation Tool | Metasploit Framework |

---

## Methodology

### 1. Create a Test PHP File

A simple PHP file was created in the Kali Linux terminal containing a command execution function.

The file was created for testing purposes in the isolated DVWA lab environment.

---

### 2. Access the File Upload Functionality

The DVWA File Upload page was accessed and the PHP file was selected for upload.

The application was configured with a security level that allowed the vulnerable behavior to be demonstrated.

---

### 3. Capture the Upload Request with Burp Suite

The upload request was intercepted using Burp Suite.

The request used a `multipart/form-data` body and contained the uploaded PHP file.

---

### 4. Modify the Content-Type

The file upload request was inspected and the uploaded file's MIME type was modified to resemble an image file.

This demonstrated that relying only on the client-supplied MIME type is insufficient for secure file validation.

---

### 5. Upload the File

The modified request was forwarded to the server.

The application accepted the uploaded file and returned a successful upload message.

The file was stored in the web application's upload directory.

---

### 6. Access the Uploaded File

The uploaded PHP file was accessed through the browser.

Because the uploaded file was stored in a web-accessible directory and server-side script execution was permitted, the PHP code was executed by the server.

This resulted in command execution on the target system.

---

## Remote Command Execution

The uploaded PHP file was used to execute commands on the target system.

The following commands were used for lab validation:

```bash
whoami
