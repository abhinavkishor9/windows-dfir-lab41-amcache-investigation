# Investigation Notes

## Lab Summary

In this lab, we focused on locating and validating Amcache hive, and attempting to parse Amcache. We generated executable activity by opening Notepad, Paint, Calculator, and Command Prompt, and at the same time, created a new executable as well. This involved tools such as Amcache Parser and PowerShell.

---

## Analyst Methodology

1. Locate the Amcache Registry hive.
2. Validate the database/hive.
3. Generate executable activity by opening Notepad, Paint, Calculator, Command Prompt.
4. Create a sample executable.
5. Attempt database parsing.
6. Investigate parser issues.

---

## Investigation Scenario

A SOC analyst receives this alert:

SuspiciousTool.exe executed yesterday

The file is gone.

Questions:

Did it really exist?
Where was it located?
Who created it?
Was it signed?
Which version was it?

---

## Evidence Collected

### Evidence 1 

Command Used

```powershell
Test-Path "C:\Windows\AppCompat\Programs\Amcache.hve"
```

Finding:
 Amcache Registry hive exists.

---

### Evidence 2 

Command Used

```powershell
Get-Item "C:\Windows\AppCompat\Programs\Amcache.hve"
```

Finding:

Validated artifact size, location, and modification time.

---

### Evidence 3 

Collected:

- DemoApp.exe
- Notepad
- Calculator
- Paint
- Command Prompt

Finding:

Generated executable activity.

---

### Evidence 4 – Parser

Tool Used

```
AmcacheParser.exe
```

Finding:

Parser execution was unsuccessful due to permission/output configuration issues.

---


## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Discovery | File and Directory Discovery | T1083 |
| Defense Evasion | Masquerading | T1036 |

---



