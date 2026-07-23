# Troubleshooting Notes

## Registry Explorer cannot open hive

Cause:
Incorrect Registry hive selected.

Resolution:
Load the user's NTUSER.DAT file instead of SYSTEM or SOFTWARE.

---

## RunMRU key appears empty

Cause:
No commands have been executed using the Run dialog.

Resolution:
Execute a few Run commands (Win + R) before repeating the investigation.

---

## RecentDocs contains no entries

Cause:
No recent documents opened.

Resolution:
Open multiple files using Windows Explorer before examining the Registry.

---

## TypedPaths key missing

Cause:
Explorer address bar has not been used.

Resolution:
Manually type several folder paths into Explorer.

---

## OpenSavePidlMRU empty

Cause:
No files opened using Windows Open/Save dialog.

Resolution:
Use Notepad or another application and open files through the File → Open dialog.

---

## Registry timestamps not updating

Cause:
Changes not yet written to the Registry.

Resolution:
Close applications and reopen Registry Explorer or refresh the hive.

---

## Incorrect Registry path

Resolution:
Verify the Registry path before analysis.

```
HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer
```
