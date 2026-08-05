# Investigation Notes

## Lab Summary

This investigation focused on locating and validating the Windows Amcache forensic artifact using native Windows tools while introducing the workflow used to analyze executable metadata.

The investigation demonstrated how executable activity can be generated and how the Amcache database can be validated before attempting forensic parsing.

---

## Analyst Methodology

1. Locate the Amcache Registry hive.
2. Validate the artifact.
3. Generate executable activity.
4. Create a sample executable.
5. Attempt database parsing.
6. Investigate parser issues.
7. Correlate findings.
8. Document evidence.

---

## Investigation Scenario

A Windows system was suspected of executing an unknown application.

The investigation aimed to determine:

- Whether the Amcache artifact existed.
- Whether Windows had observed new executables.
- Whether the Registry hive could be parsed.
- What troubleshooting issues prevented analysis.

---

## Evidence Collected

### Evidence 1 – Amcache Validation

Command Used

```powershell
Test-Path "C:\Windows\AppCompat\Programs\Amcache.hve"
```

Finding:

Confirmed the Amcache Registry hive exists.

---

### Evidence 2 – Registry Hive Information

Command Used

```powershell
Get-Item "C:\Windows\AppCompat\Programs\Amcache.hve"
```

Finding:

Validated artifact size, location, and modification time.

---

### Evidence 3 – Executable Activity

Collected:

- DemoApp.exe
- Notepad
- Calculator
- Paint
- Command Prompt

Finding:

Generated executable activity for investigation.

---

### Evidence 4 – Parser Execution

Tool Used

```
AmcacheParser.exe
```

Finding:

Parser execution was unsuccessful due to permission/output configuration issues.

---

## DFIR Analysis

The investigation confirmed the presence of the Windows Amcache artifact and demonstrated the workflow required to analyze executable metadata. Although parsing was unsuccessful, the investigation highlighted common tool configuration issues encountered during forensic analysis and reinforced the importance of validating artifacts before relying on third-party utilities.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Discovery | File and Directory Discovery | T1083 |
| Defense Evasion | Masquerading | T1036 |

---

## Analyst Observations

- Windows automatically maintains the Amcache database.
- Native PowerShell successfully validated the Registry hive.
- Executable activity was generated successfully.
- Parser execution requires correct permissions and output parameters.
- Troubleshooting forensic tools is part of real-world DFIR investigations.

---

## Conclusion

The investigation successfully validated the Windows Amcache artifact and demonstrated the methodology used during executable artifact analysis. Although the parser could not successfully process the database during this exercise, the investigation established the workflow required for future Amcache analysis.
