# 2️⃣ File & Directory Permissions

## 📝 Task

Create a directory `/devops_workspace` and a file `project_notes.txt` inside it.

### 🔒 Set the following permissions:
- **Owner**: Read and Write (edit)
- **Group**: Read-only
- **Others**: No access

Use `ls -l` to verify the permissions.

---

## 🧪 Steps

### 1. Create the directory:
```bash
mkdir /devops_workspace
```


### 2. Create the file:
```bash
touch /devops_workspace/project_notes.txt
```

### 3. Set permissions (Owner: rw, Group: r, Others: -):
```bash
chmod 640 /devops_workspace/project_notes.txt
```

### 4. Verify using ls -l:
```bash
ls -l /devops_workspace/project_notes.txt
```

### ✅ Expected output:
```bash
-rw-r----- 1 your_user your_group 0 Jul  5 14:00 /devops_workspace/project_notes.txt
```

## 📌 Notes

#### 6 = Read (4) + Write (2) for owner

#### 4 = Read-only for group

#### 0 = No access for others

---
#### You can update ownership using chown if needed:
```bash
chown username:groupname /devops_workspace/project_notes.txt
```


