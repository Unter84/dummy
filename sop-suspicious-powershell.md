# SOP: Suspicious but Safe PowerShell Script

## Purpose

Test PowerShell logging and detection rules.

## Steps

1. Create a script:

```
# Safe test script
$flag = "Invoke-Expression"
Write-Output "Safe detection test"
```

2. Save as:

```
test.ps1
```

3. Run:

```
powershell.exe -ExecutionPolicy Bypass -File test.ps1
```

4. Review:

* PowerShell logs
* Sysmon 4104
* Velociraptor process/script tracking

## Notes

* Script contains suspicious strings but no malicious behavior.

---

