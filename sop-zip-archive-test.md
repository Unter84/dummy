# SOP: ZIP Archive Scanning Test

## Purpose

Simulate scenarios where malware is stored inside ZIP archives.

## Steps

1. Create a small folder with harmless files.
2. Compress it:

```
Right-click → Send to → Compressed (zipped) folder
```

3. Place ZIP in:

```
C:\Users\Public\Downloads\
```

4. Test:

* Velociraptor ZIP parsing
* YARA scanning
* SIEM alerts for archive creation or access

## Notes

* Contents are harmless; only structure is tested.

---
