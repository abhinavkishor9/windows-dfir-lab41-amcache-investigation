# Troubleshooting Notes

## Issue 1

I am unable  to locate Amcache hive.

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



---

## Issue 3

DemoApp.exe not found.

### Cause

Copy operation failed.

### Resolution

Verify:

```powershell
Get-ChildItem C:\AmcacheLab
```

---

## Issue 4

I am unable  to remove lab folder.

### Cause

DemoApp.exe was still running.

### Resolution

Close the application before executing:

```powershell
Remove-Item C:\AmcacheLab -Recurse -Force
```
