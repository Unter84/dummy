# SOP: Load a Test Kernel Driver for Detection and Analysis

## Purpose

You load a harmless test driver to study how Windows logs driver installation and loading events. This helps build SIEM rules, detection logic, and Velociraptor demo workflows.

## Prerequisites

* Administrator privileges
* A Windows test system
* A dummy driver file named **test.sys**

## Steps

### 1. Create the driver file

Place **test.sys** in the directory where you will run the command. Example:

```
C:\Users\***\Desktop\
```

### 2. Open an elevated Command Prompt

* Search for “cmd”
* Right click
* Select “Run as administrator”

### 3. Create the driver service

Run this command inside the directory containing **test.sys**:

```
sc create notsuspicious type=kernel start=demand error=normal binpath=C:\Users\***\Desktop\test.sys displayname="Nothing to see here"
```

### 4. Start the driver

Run:

```
sc start notsuspicious
```

### 5. Stop the driver

When you finish testing:

```
sc stop notsuspicious
```

### 6. Remove the driver service

Run:

```
sc delete notsuspicious
```

## Observations to Collect

Monitor the system for:

* Driver load events (e.g., Sysmon Event ID 6)
* Service creation events
* File access activity
* Registry modifications
* Velociraptor process tracking
* Kernel-mode load behavior in EDR or logging tools

## Notes

* Use only on lab or non-production machines
* Replace **test.sys** with any other safe driver when testing different scenarios
* Results help build detection logic for kernel driver loading activity

---
