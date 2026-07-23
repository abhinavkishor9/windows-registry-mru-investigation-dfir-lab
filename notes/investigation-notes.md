# Investigation Notes

## Investigation Summary

This investigation analyzed Windows Registry MRU artifacts to determine recently executed commands, recently opened files, and Explorer navigation history.

---

# Lab Summary

Windows Registry stores historical information about user activity inside several MRU keys. These artifacts persist across user sessions and can reveal evidence even after files have been removed.

---

# Analyst Methodology

The investigation followed a structured DFIR process:

1. Identify Registry hive containing user artifacts.
2. Load the NTUSER.DAT hive using Registry Explorer.
3. Examine common MRU Registry keys.
4. Record Registry values and timestamps.
5. Compare artifacts across multiple Registry locations.
6. Correlate evidence to reconstruct user activity.
7. Document findings and preserve screenshots.

---

# Artifacts Examined

## RunMRU

Purpose:
Recently executed Run dialog commands.

Evidence:
- Executed commands
- MRU order

---

## RecentDocs

Purpose:
Recently opened documents.

Evidence:
- File names
- Extension groups
- MRU sequence

---

## OpenSavePidlMRU

Purpose:
Files accessed through Open/Save dialogs.

Evidence:
- File names
- Folder locations
- Dialog usage

---

## TypedPaths

Purpose:
Explorer address bar history.

Evidence:
- Recently visited folders
- Typed directory paths

---

# Evidence Collected

- Registry screenshots
- Registry Explorer output
- Registry timestamps
- MRU values
- User activity artifacts

---

# Analysis

Multiple Registry locations independently confirmed user activity.

The artifacts collectively showed:

- Commands executed
- Files opened
- Folders browsed
- Explorer navigation history

---

# Analyst Observations

- Registry retains historical evidence even after files may be deleted.
- Different MRU keys record different aspects of user activity.
- Correlating multiple Registry locations provides a more complete timeline than examining a single artifact.
- Registry Explorer simplifies forensic interpretation by presenting Registry values and timestamps in an investigator-friendly format.

---

# Conclusion

Registry MRU artifacts provide valuable forensic evidence for reconstructing user behavior and should be examined during every Windows DFIR investigation.
