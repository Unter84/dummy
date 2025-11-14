# SOP: EICAR Test File Simulation

## Purpose

Trigger safe antivirus and SIEM alerts using the EICAR standard test string.

## Steps

1. Open a text editor.
2. Paste the exact string:

```
X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*
```

3. Save the file as:

```
eicar.com
```

4. Place it in your test directory.
5. Observe detections in SIEM, EDR, or Velociraptor.

## Notes

* The file does not execute.
* Safe for all testing environments.

---
