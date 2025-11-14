# 📄 sop-suspicious-exe.md

# SOP: Suspicious but Harmless EXE

## Purpose

Test detections that rely on filename, path, or execution patterns.

## Steps

1. Copy a harmless Windows binary:

```
C:\Windows\System32\notepad.exe
```

2. Rename it:

```
payload.exe
```

3. Move it to a suspicious directory:

```
C:\Users\Public\payload.exe
```

4. Run the file:

```
.\payload.exe
```

5. Review logged events:

* Sysmon process creation
* Velociraptor process tracking
* SIEM rules based on filename or path

## Notes

* The binary remains harmless.

---
