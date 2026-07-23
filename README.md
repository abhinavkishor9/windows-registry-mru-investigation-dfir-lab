# windows-registry-mru-investigation-dfir-lab
## Overview

Windows stores numerous artifacts inside the Registry that record user activity. These artifacts are commonly called **MRU (Most Recently Used)** entries and are frequently examined during Digital Forensics and Incident Response (DFIR) investigations.

This lab demonstrates how Registry Explorer can be used to investigate Windows Registry MRU locations and reconstruct recent user activity.

---

# Executive Summary

This investigation analyzed Windows Registry MRU artifacts to determine recently opened documents, executed commands, and user navigation history.

Multiple Registry keys containing MRU data were examined to understand how Windows records user interaction with the operating system. The investigation confirmed that Registry artifacts provide valuable evidence even when files have been deleted or application logs are unavailable.

---

# Objectives

- Understand Windows Registry MRU artifacts
- Examine user activity recorded inside the Registry
- Investigate Run dialog history
- Analyze Recent Documents entries
- Examine Open/Save dialog history
- Investigate Windows Explorer Typed Paths
- Correlate Registry evidence with user activity

---

# What are MRU Artifacts?

MRU stands for **Most Recently Used**.

Windows stores information about recently accessed items inside Registry keys.

Examples include:

- Recently opened files
- Commands executed from Run dialog
- Recently browsed folders
- Files selected through Open/Save dialog
- Explorer address bar history

These artifacts are extremely valuable during DFIR investigations because they help reconstruct user activity.

---

# Lab Environment

| Component | Details |
|----------|---------|
| OS | Windows 10 x64 |
| VM | VMware Workstation Player |
| Tools | Registry Explorer, Registry Editor |
| Registry Hive | NTUSER.DAT |
| Investigation Type | Windows Registry Forensics |

---

# Tools Used

- Registry Explorer (Eric Zimmerman)
- Registry Editor (regedit)
- Windows Explorer
- PowerShell

---

# Registry Keys Investigated

## RunMRU

```
HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\RunMRU
```

Stores commands executed through Windows Run dialog.

---

## RecentDocs

```
HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs
```

Stores recently opened files.

---

## OpenSavePidlMRU

```
HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSavePidlMRU
```

Stores files selected through Open/Save dialog boxes.

---

## TypedPaths

```
HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\TypedPaths
```

Stores paths typed into Windows Explorer address bar.

---

# Evidence Collected

- RunMRU Registry entries
- RecentDocs entries
- OpenSavePidlMRU entries
- TypedPaths entries
- Registry Explorer screenshots
- Registry timestamps

---

# Evidence Correlation

The Registry artifacts collectively reconstructed user behavior:

- RunMRU showed commands manually executed through the Run dialog.
- RecentDocs confirmed recently opened documents.
- OpenSavePidlMRU revealed files selected through Windows Open/Save dialogs.
- TypedPaths identified directories manually accessed through Explorer.

Correlating these artifacts provided a timeline of user interaction with the operating system.

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1083 | File and Directory Discovery |
| T1082 | System Information Discovery |
| T1005 | Data from Local System |

Although MRU artifacts are not malicious themselves, they are frequently analyzed to investigate attacker behavior and reconstruct user actions following compromise.

---

# Skills Demonstrated

- Windows Registry Forensics
- Registry Explorer usage
- User Activity Reconstruction
- Artifact Correlation
- Windows DFIR Investigation
- Timeline Analysis
- Evidence Documentation
- Registry Artifact Interpretation

---

# Investigation Findings

The Registry successfully retained evidence of recent user activity across multiple MRU locations. Even without relying on application logs, investigators could identify executed commands, recently opened files, and accessed folders. This demonstrates the evidentiary value of Windows Registry artifacts during forensic investigations.

---

# Key Takeaway

Windows Registry MRU artifacts provide reliable evidence of user activity and are among the most valuable forensic artifacts examined during Windows DFIR investigations.

---

