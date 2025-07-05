# 3️⃣ Analyzing System Logs using AWK, Grep, and Sed

## 🎯 Goal

Use Linux command-line utilities to analyze logs from the `Linux_2k.log` file and extract meaningful insights.

---

## 📂 1. Setup & File Retrieval

### 1.1 Clone the Repository

Clone the [LogHub GitHub repository](https://github.com/logpai/loghub) to access the sample log file:

```bash
git clone https://github.com/logpai/loghub.git
```

### 1.2 Navigate to the Correct Directory

```bash
cd loghub/Linux/
```

### 1.3 Confirm File Availability

Ensure `Linux_2k.log` is present:

```bash
ls -lh Linux_2k.log
```

You should see a file similar to this in the output:

```bash
-rw-r--r-- 1 user user 211K Feb  6 09:26 Linux_2k.log
```

---

## 🔎 2. Log Analysis Tasks

### 2.1 Identify All Error Logs (case-insensitive)

```bash
grep -i "error" Linux_2k.log
```

> This command highlights any entries indicating errors, regardless of case.

---

### 2.2 Extract Timestamps and Categorize Log Levels

Using `awk`, extract key information from each log entry:

```bash
awk '{
  timestamp = $1 " " $2 " " $3;
  if ($0 ~ /authentication failure/) log_level = "ERROR";
  else if ($0 ~ /session (opened|closed)/) log_level = "INFO";
  else if ($0 ~ /ALERT/) log_level = "ALERT";
  else log_level = "INFO";
  print timestamp, log_level;
}' Linux_2k.log
```

> This script maps patterns in log messages to specific log levels based on their content.

---

### 2.3 Mask IP Addresses for Privacy

To redact all IPv4 addresses from the file:

```bash
sed -E 's/([0-9]{1,3}\.){3}[0-9]{1,3}/[REDACTED]/g' Linux_2k.log
```

> Helps ensure data sanitization when sharing logs externally.

---

## 🧠 3. Bonus: Determine Most Repeated Log Messages

### 3.1 Extract Message Content (excluding initial metadata)

```bash
awk '{for (i=5; i<=NF; i++) printf $i " "; print ""}' Linux_2k.log
```

### 3.2 Find Top 10 Most Frequent Messages

```bash
awk '{for (i=5; i<=NF; i++) printf $i " "; print ""}' Linux_2k.log | sort | uniq -c | sort -nr | head -10
```

> This sequence processes the log content and highlights the most frequent messages by occurrence count.

---

## 🧾 Summary Table

| Description                     | Command                                               |      |         |          |            |
| ------------------------------- | ----------------------------------------------------- | ---- | ------- | -------- | ---------- |
| Match lines with "error"        | `grep -i "error" Linux_2k.log`                        |      |         |          |            |
| Extract timestamps & log levels | See `awk` script above                                |      |         |          |            |
| Anonymize IP addresses          | `sed -E 's/([0-9]{1,3}\.){3}[0-9]{1,3}/[REDACTED]/g'` |      |         |          |            |
| Most common log messages        | \`awk ...                                             | sort | uniq -c | sort -nr | head -10\` |

---

✅ This task demonstrates practical log analysis skills using core Linux tools that are essential for every DevOps engineer or system administrator.

