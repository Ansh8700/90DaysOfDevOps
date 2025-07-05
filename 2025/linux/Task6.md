# 6️⃣ Scheduled Backup Automation using Shell Script 💾

## 🎯 Goal

* Develop a shell script that compresses a given directory into a `.tar.gz` file with the current date and time in the filename.
* Store the backup in a specified destination.
* Print status messages in **green (success)** and **red (failure)**.
* Schedule it to run automatically using `cron`.

---

## ✅ Script Overview

```bash
#!/bin/bash

# === Script: auto_backup.sh ===
# Arguments: $1 = source_dir, $2 = destination_dir

SRC="$1"
DEST="$2"
DATE_TAG=$(date '+%Y-%m-%d_%H-%M')
FILENAME="backup_${DATE_TAG}.tar.gz"

# Create destination directory if it doesn't exist
mkdir -p "$DEST"

# Perform backup
echo -e "\e[32m[INFO] Initiating backup process...\e[0m"
tar -czf "${DEST}/${FILENAME}" "$SRC" 2>/dev/null

# Check exit code and display message
if [ $? -eq 0 ]; then
  echo -e "\e[32m[SUCCESS] Backup saved to: ${DEST}/${FILENAME}\e[0m"
else
  echo -e "\e[31m[ERROR] Backup failed. Check directory paths and permissions.\e[0m"
  exit 1
fi
```

---

## 🛠️ Implementation Steps

### 1. Create the Shell Script

```bash
mkdir -p ~/scripts
nano ~/scripts/auto_backup.sh
```

Paste the script above and save it using `Ctrl+O`, then exit with `Ctrl+X`.

---

### 2. Set Execute Permission

```bash
chmod +x ~/scripts/auto_backup.sh
```

---

### 3. Test It Manually

```bash
./scripts/auto_backup.sh ~/devops_workspace ~/backups
```

**Expected output:**

```bash
[INFO] Initiating backup process...
[SUCCESS] Backup saved to: /home/ansh/backups/backup_2025-07-05_17-00.tar.gz
```

---

### 4. Schedule via Cron

```bash
crontab -e
```

Add the following line to run it every midnight:

```bash
0 0 * * * /home/ansh/scripts/auto_backup.sh /home/ansh/devops_workspace /home/ansh/backups
```

**Optional (for testing every minute):**

```bash
* * * * * /home/ansh/scripts/auto_backup.sh /home/ansh/devops_workspace /home/ansh/backups
```

---

## 🔍 Verifying Backups

### Check Backup Files

```bash
ls -lh ~/backups
```

### Check Cron Execution

```bash
grep auto_backup /var/log/syslog
```

---

## 🔐 Bonus: Retention & Cloud Sync

### Auto-delete Old Backups

Add to script:

```bash
find "$DEST" -name "backup_*.tar.gz" -mtime +30 -exec rm {} \;
```

### Upload to AWS S3 (Optional)

```bash
aws s3 sync "$DEST" s3://your-s3-bucket/backups/
```

---

## 📌 Quick Reference

| Color Code | Purpose         |
| ---------- | --------------- |
| `\e[32m`   | Green - Success |
| `\e[31m`   | Red - Error     |
| `\e[0m`    | Reset           |

| Cron Syntax | Schedule       |
| ----------- | -------------- |
| `0 0 * * *` | Every midnight |
| `* * * * *` | Every minute   |

