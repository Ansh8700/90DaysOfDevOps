# 🔧 Task 3: **Configure Remote URL with Your PAT**

### ✅ 1. Configure Remote URL with Your PAT

This allows Git to authenticate using your **Personal Access Token** (PAT) without prompting every time.

#### 🔧 Command if **no remote** is set yet:

```bash
git remote add origin https://<your-username>:<your-PAT>@github.com/<your-username>/90DaysOfDevOps.git
```

#### 🔁 Command if **origin already exists**:

```bash
git remote set-url origin https://<your-username>:<your-PAT>@github.com/<your-username>/90DaysOfDevOps.git
```

🔐 **Example**:
If your GitHub username is `anshgupta`, and your PAT is `ghp_ABC123xyz456`, then:

```bash
git remote set-url origin https://anshgupta:ghp_ABC123xyz456@github.com/anshgupta/90DaysOfDevOps.git
```

> ⚠️ **Security Warning**: Do **not** share your PAT or commit it in any file. This method is only recommended for this learning task.

---

### ✅ 2. **Push Your Commit to Remote**

Make sure you've committed your changes before pushing.

```bash
git push -u origin main
```

If your branch is named `master` or something else, replace `main` accordingly.

---

### ✅ 3. **(Optional) Pull Remote Changes**

To verify everything is working correctly:

```bash
git pull origin main
```

---

### 📌 Bonus Tip (Recommended)

Instead of embedding your PAT in the URL every time, **use Git Credential Manager or SSH** for better long-term security.

<img width="1916" height="973" alt="Image" src="https://github.com/user-attachments/assets/3978f762-a734-4444-a5a6-c852c537c6f9" />

<img width="1919" height="973" alt="Image" src="https://github.com/user-attachments/assets/e2d46891-25cc-4793-bc43-0dd386bd3717" />

<img width="1919" height="1012" alt="Image" src="https://github.com/user-attachments/assets/54b23434-af50-4fb7-a9ef-8fa6fe685569" />
