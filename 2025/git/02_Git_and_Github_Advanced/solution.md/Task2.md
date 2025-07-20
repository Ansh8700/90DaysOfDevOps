# ✅ Task 2: Undoing Changes – Reset & Revert

## 💡 Commands Used:

```bash
echo "Wrong code" >> wrong.txt
git add .
git commit -m "Committed by mistake"
```

#### 1. Soft Reset:

```bash
git reset --soft HEAD~1
```

Keeps changes staged.

#### 2. Mixed Reset:

```bash
git reset --mixed HEAD~1
```

Unstages but keeps the file changes.

#### 3. Hard Reset:

```bash
git reset --hard HEAD~1
```

Completely removes the last commit and changes.

#### 4. Revert:

```bash
git revert HEAD
```

Safely creates a new commit that undoes the previous one.

### 🔍 Reset vs Revert:

| Feature        | `reset`                   | `revert`                      |
| -------------- | ------------------------- | ----------------------------- |
| Use Case       | Undo local commits        | Undo committed changes safely |
| History Change | Yes (can rewrite history) | No (adds a new commit)        |
| Safe for Push  | No (on shared branches)   | Yes                           |

### ✅ When to Use:

* Use **reset** for local, unpushed changes.
* Use **revert** on shared/public branches to avoid rewriting history.

