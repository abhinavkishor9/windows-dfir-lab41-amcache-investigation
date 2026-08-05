# Troubleshooting Notes

## Issue 1

Unable to locate Amcache.

### Cause

Incorrect file path.

### Resolution

Verify:

```powershell
Test-Path "C:\Windows\AppCompat\Programs\Amcache.hve"
```

---

## Issue 2

AmcacheParser returned:

```
CSV required - exiting
```

### Cause

The parser version requires an output directory for CSV export.

### Resolution

Specify an output folder using the appropriate CSV parameter supported by the parser version.

---

## Issue 3

Typing:

```
AmcacheParser.exe help
```

returned:

```
Access is denied
```

### Cause

Incorrect command syntax or insufficient permissions.

### Resolution

Run the parser using its supported help syntax (such as `--help` or `-h`) from an elevated Command Prompt and verify execution permissions.

---

## Issue 4

DemoApp.exe not found.

### Cause

Copy operation failed.

### Resolution

Verify:

```powershell
Get-ChildItem C:\AmcacheLab
```

---

## Issue 5

Unable to remove investigation folder.

### Cause

DemoApp.exe was still running.

### Resolution

Close the application before executing:

```powershell
Remove-Item C:\AmcacheLab -Recurse -Force
```
