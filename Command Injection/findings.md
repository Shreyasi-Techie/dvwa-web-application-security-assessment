# Command Injection

## Severity

Critical

---

## Description

The application fails to properly validate user input before incorporating it into an operating system command.

An attacker can append additional shell commands using command separators, resulting in arbitrary command execution under the privileges of the web server process.

---

## Affected Page

```
DVWA → Command Execution
```

---

## Evidence

The following commands were successfully executed.

### whoami

```
127.0.0.1; whoami
```

Result:

```
www-data
```

---

### Reading /etc/passwd

```
127.0.0.1; cat /etc/passwd
```

Result:

Sensitive system account information was disclosed.

---

### Reverse Shell

A reverse shell was successfully established using Netcat.

Commands executed:

- whoami
- hostname
- ls

confirming full remote command execution.

---

## Risk

Successful exploitation allows an attacker to:

- Execute arbitrary operating system commands
- Read sensitive files
- Enumerate the operating system
- Establish remote shell access
- Potentially escalate privileges

---

## CVSS v3.1

9.8 (Critical)
