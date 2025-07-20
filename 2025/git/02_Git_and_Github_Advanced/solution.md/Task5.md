# ✅ Task 5: Rebasing – Clean Commit History

## 🛠️ Commands:

```bash
git fetch origin main
git rebase origin/main
# Resolve conflicts if any
git rebase --continue
```

### 🔄 Merge vs Rebase:

| Feature        | `merge`                    | `rebase`                 |
| -------------- | -------------------------- | ------------------------ |
| Commit History | Keeps all branch histories | Linear, clean history    |
| Merge Commits  | Yes                        | No                       |
| Use Case       | Collaborative dev          | Clean and linear history |

### ✅ Best Practices:

* Rebase **before merging** to keep history clean.
* Avoid rebasing **shared branches** (rewrites history).
* Use merge in collaborative settings; rebase for solo or pre-merge cleanup.