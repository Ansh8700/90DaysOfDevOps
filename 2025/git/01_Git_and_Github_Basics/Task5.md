# ✅ Task 5: Advanced Branching and Switching

---

## 🌿 1. Create a New Branch

Create a new branch named `feature-update` from your current branch (usually `main`):

```bash
git branch feature-update
```

---

## 🔀 2. Switch to the New Branch

Switch to the newly created branch:

```bash
git switch feature-update
# OR (legacy command)
git checkout feature-update
```

---

## 📝 3. Modify and Commit Changes

Edit your file `info.txt` to include additional details (e.g., more about your DevOps journey or task progress).

Then stage and commit your changes:

```bash
git add info.txt
git commit -m "Feature update: Enhance info.txt with additional details"
git push origin feature-update
```

---

### Next step: Merge via Pull Request
---

1. Go to your GitHub repository.
2. You will see a banner suggesting to **Compare & Pull Request**.
3. Click it, review your changes, and create the pull request to merge `feature-update` into `main`.
4. Once reviewed, **Merge the PR**.

✅ You have successfully used branching, switching, and remote collaboration.

---

## 🧪 4. Optional Extra Challenge: Simulate a Merge Conflict


#### 1. On feature-update branch:

   ```bash
   vim info.txt
   ```

   ---

#### 2. Edited info.txt:
    
    
   ```bash
   Hi, I'm Ansh Gupta – a DevOps engineer exploring Git fundamentals!
   ```
   To:
   ```bash
   Hi, I'm Ansh Gupta – enhancing Git fundamentals with new features!
   ```
   
   ---
   
   #### 3. Now Stage it using `git add`, then commit it with a meaningful message:
   ```bash
    git add info.txt
    git commit -m "Feature update: Enhanced intro line"
   ```
   ---

   #### 4. Switch to main and create a new branch experimental

   ```bash
   git switch main
   git checkout -b experimental
   ```
   ---

   #### 5. Modify info.txt differently in experimental
   Edit info.txt — change the same line that was changed in the feature-update branch (or a nearby line).

   For example, change:

   ```bash
   Hi, I'm Ansh Gupta – a DevOps engineer exploring Git fundamentals!
   ```
   To:
   ```bash
   Hi, I'm Ansh Gupta – experimenting with Git merge conflicts!
   ```
   Then stage and commit:
   ```bash
   git add info.txt
   git commit -m "Experimental update: Simulate merge conflict"
   ```

   ---

   #### 6. Switch back to feature-update branch
   ```bash
   git switch feature-update
   ```

   ---

   #### 7. Merge experimental into feature-update
   ```bash
   git merge experimental
   ```
   #### You will now see a merge conflict message like:

   ```bash
   Auto-merging info.txt
   CONFLICT (content): Merge conflict in info.txt
   Automatic merge failed; fix conflicts and then commit the result.
   ```

   ---

   #### 8. Open info.txt and resolve the conflict manually
   You will see something like:
   
   ```bash
   <<<<<<< HEAD
Hi, I'm Ansh Gupta – enhancing Git fundamentals with new features!
=======
Hi, I'm Ansh Gupta – experimenting with Git merge conflicts!
>>>>>>> experimental
```
Manually edit it to resolve the conflict. For example:
```bash
Hi, I'm Ansh Gupta – exploring Git fundamentals and resolving merge conflicts!
```
Then save the file.

---

#### 9. Stage and commit the resolved file
```bash
git add info.txt
git commit -m "Resolve merge conflict between feature-update and experimental"
```

---

🎉 Done!
You’ve successfully simulated a merge conflict and resolved it manually — an essential real-world Git skill. If you'd like to push the changes:
