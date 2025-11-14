# SOP: Safe Kernel Driver Load Simulation

## Purpose

Test Windows driver load detections using a harmless `.sys` file.

## Prerequisites

* Administrator access
* A safe test driver:

```
test.sys
```

## Steps

1. Place `test.sys` in your working directory.
2. Open elevated Command Prompt.
3. Create the driver service:

```
sc create notsuspicious type=kernel start=demand error=normal binpath=C:\Users\mfhus\OneDrive\Desktop\test.sys displayname="Nothing to see here"
```

4. Start it:

```
sc start notsuspicious
```

5. Collect logs:

* Sysmon driver load events
* Velociraptor driver analysis
* SIEM service creation events

6. Stop and delete:

```
sc stop notsuspicious
sc delete notsuspicious
```

## Notes

* Use only on test machines.
* The driver must be non-malicious.

---
