# ✅ Task 4: Cherry-Picking

## 🔧 Steps:

```bash
git log --oneline
git cherry-pick <commit-hash>
```

#### If there are conflicts:

```bash
# Fix conflicts manually
git add .
git cherry-pick --continue
```

### 💡 Usage:

Used to selectively apply a specific commit (e.g., bug fix) from one branch to another.

### ⚠️ Risks:

* **Duplicate commits**: If the same commit is merged later via another method.
* **Conflicts**: Especially if the context has changed.
* **History complexity**: Can make history harder to understand.