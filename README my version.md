# windows-dfir-lab41-amcache-investigation

## Overview

Imagine Windows keeps a notebook.

Every time Windows notices a new program (an executable file), it writes down some information about it.

Not the whole program.

Just information about the program.

That notebook is called Amcache.
Windows uses Amcache for:

Program compatibility
Application inventory
Software management
System optimization

It was not originally designed for forensics.

However…

Forensic investigators discovered that it records valuable evidence.

Today, Amcache is considered one of the best Windows forensic artifacts.

---

# Executive Summary

Imagine malware runs on a computer.

After attacking the system, the attacker deletes:

malware.exe
logs
shortcuts

Everything appears clean.

But…

Windows may already have recorded the program inside Amcache.

Even though the executable no longer exists, investigators can still find evidence that Windows saw it.

That is why Amcache is extremely valuable.
A SOC analyst receives this alert:

SuspiciousTool.exe executed yesterday

The file is gone.

Questions:

Did it really exist?
Where was it located?
Who created it?
Was it signed?
Which version was it?

Amcache may answer all of those questions.

---

# Investigation Objectives

After completing this lab, we will understand:

What Amcache is and why Windows creates it.
Why investigators use it during DFIR.
The difference between file metadata and file contents.
How to locate the Amcache hive.
How to generate executable activity.
How to parse the Amcache database.
How to correlate executable records with real-world evidence.

---



# Tools Used

- Windows 10 VM
- PowerShell
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
2. Validate the Registry hive-do we have the hive and the database inside it?
3. Generate executable activity-opening Notepad, Command Prompt, Calculator, Paint for 5 seconds each.
4. Create sample executable.
5. Attempt Amcache parsing.
6. Investigate parser errors.


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

---

