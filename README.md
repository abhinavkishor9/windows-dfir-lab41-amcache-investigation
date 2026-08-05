# windows-dfir-lab41-amcache-investigation

## Overview

Windows Amcache is one of the most valuable forensic artifacts used during Digital Forensics and Incident Response (DFIR). It stores metadata about executables observed by Windows, allowing investigators to identify applications that existed on a system even after they have been removed.

In this hands-on DFIR lab, native Windows tools were used to locate the Amcache database, generate executable activity, validate the artifact, and attempt forensic parsing using AmcacheParser. Although the parser could not be executed successfully due to a permissions/output configuration issue, the investigation demonstrates the methodology analysts follow when examining Amcache during real-world investigations.

---

# Executive Summary

This investigation demonstrates how Windows Amcache can be located and validated using native Windows tools. The lab simulated executable activity, confirmed the existence of the Amcache Registry hive, and introduced the workflow used to parse forensic artifacts. The investigation also documented troubleshooting steps encountered while attempting to analyze the database using AmcacheParser.

---

# Investigation Objectives

- Understand the Windows Amcache artifact.
- Locate the Amcache Registry hive.
- Generate executable activity.
- Validate the Amcache database.
- Attempt to parse the hive.
- Document parser issues.
- Correlate investigation evidence.

---

# Skills Demonstrated

- Windows Amcache Investigation
- Windows Registry Artifact Analysis
- Windows DFIR Methodology
- Host-Based Forensic Investigation
- PowerShell Investigation
- Executable Activity Generation
- Artifact Validation
- Tool Troubleshooting
- Investigation Documentation
- Incident Reporting

---

# Tools Used

- Windows 10
- Windows PowerShell
- File Explorer
- AmcacheParser (Eric Zimmerman)

---

# Lab Environment

| Component | Details |
|-----------|---------|
| Operating System | Windows 10 |
| Investigation Type | Host-Based DFIR |
| Analysis Method | Native Windows Tools |
| Primary Artifact | Amcache.hve |
| Shell | Windows PowerShell |
| Additional Tool | AmcacheParser |
| Privileges | Administrator |

---

# Investigation Workflow

1. Locate Amcache.
2. Validate the Registry hive.
3. Generate executable activity.
4. Create sample executable.
5. Attempt Amcache parsing.
6. Investigate parser errors.
7. Document findings.

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1083 | File and Directory Discovery |
| T1005 | Data from Local System |
| T1036 | Masquerading |

---

# Evidence Collected

- Amcache Registry hive
- Executable activity
- DemoApp.exe
- PowerShell outputs
- Parser execution attempt
- Error messages
- Cleanup validation

---

# Evidence Correlation

The investigation confirmed the presence of the Windows Amcache artifact and generated new executable activity through DemoApp.exe. Native Windows tools successfully validated the Registry hive while parser execution identified configuration and permission issues that prevented full database parsing. These observations mirror common troubleshooting scenarios encountered during forensic investigations.

---

# Investigation Findings

The investigation successfully identified and validated the Windows Amcache database. Executable activity was generated for later forensic analysis, while parser execution highlighted common operational issues involving permissions and required output parameters. Although the database could not be parsed during this lab, the investigation established the complete workflow used during Windows Amcache analysis.

---

# Key Takeaway

Amcache is one of the most valuable Windows forensic artifacts for identifying executable files observed by the operating system. Even when analysis tools encounter configuration issues, investigators can still validate the artifact, preserve evidence, document observations, and troubleshoot parsing methods as part of a structured DFIR investigation.
