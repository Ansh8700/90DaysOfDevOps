# 🎯 Bonus Tasks 🚀

## 🎯 **Bonus Task 1: Top 5 Most Common Log Messages**

**Objective**: Extract frequent log messages using `awk`, `sort`, and `uniq`.

```bash
awk -F':' '{print $NF}' Linux_2k.log | sort | uniq -c | sort -nr | head -5
```

**Explanation**:

* `-F':'` splits lines by colon (assuming message is after timestamp/severity).
* `print $NF` gets the last field (actual message).
* `uniq -c` counts duplicates.
* `sort -nr` sorts by frequency (highest first).

---

## 🎯 **Bonus Task 2: Find Files Modified in Last 7 Days**

**Objective**: Use `find` to locate recently changed files.

```bash
find /path/to/search -type f -mtime -7
```

**Explanation**:

* `-type f` looks only for files.
* `-mtime -7` finds files modified **within the last 7 days**.

📝 *Replace `/path/to/search` with a real path like `/var/log` or `~/projects`.*

---

## 🎯 **Bonus Task 3: Extract ERROR and WARNING Logs Script**

**Objective**: Write a shell script to filter log entries with `ERROR` or `WARNING`.

```bash
#!/bin/bash

# File: extract_errors_warnings.sh
log_file="Linux_2k.log"

grep -E "ERROR|WARNING" "$log_file"
```

> Make the script executable:

```bash
chmod +x extract_errors_warnings.sh
./extract_errors_warnings.sh
```

