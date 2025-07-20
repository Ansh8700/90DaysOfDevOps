# ✅ Task 3: Git Stashing

## 📌 Scenario:

```bash
echo "Temporary Change" >> temp.txt
git add temp.txt
git stash
```

#### 🔄 Switching Branches:

```bash
git checkout main
git stash pop
```

### 💬 When to Use:

Use when you need to:

* Temporarily save uncommitted work.
* Switch branches to fix something else.

### ⚠️ `stash pop` vs `stash apply`:

| Command       | Behavior                            |
| ------------- | ----------------------------------- |
| `stash pop`   | Applies changes & removes the stash |
| `stash apply` | Applies changes but keeps stash     |


