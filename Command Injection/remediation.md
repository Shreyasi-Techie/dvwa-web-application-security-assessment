# Command Injection Remediation

## Root Cause

The application directly concatenates user input into an operating system command.

---

## Recommendations

### Validate Input

Accept only valid IPv4 or IPv6 addresses.

---

### Avoid Shell Execution

Avoid using shell commands when native programming language APIs are available.

---

### Escape User Input

If shell execution is unavoidable, use secure escaping mechanisms.

---

### Least Privilege

Run the web server using a non-privileged account.

---

### Monitoring

Enable centralized logging and alerting for suspicious command execution attempts.

---

### Input Allowlisting

Reject any characters such as:

```
;
&
|
`
$
(
)
```

that may be interpreted by the operating system shell.
