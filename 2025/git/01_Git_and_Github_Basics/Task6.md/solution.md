# ✅ Task 6: Explain Branching Strategies



## 🔧 Git Commands Used in Tasks 1–5:



#### **Task 1: Fork and Clone the Repository**

```bash
# Fork the repository from GitHub manually
# Then clone your forked repo
git clone https://github.com/<your-username>/90DaysOfDevOps.git
cd 2025/git/01_Git_and_Github_Basics
```

---

<img width="1915" height="964" alt="Image" src="https://github.com/user-attachments/assets/bd4a61ec-f6df-4f20-9454-558d458bd733" />

---

<img width="1919" height="1008" alt="Image" src="https://github.com/user-attachments/assets/c2c8b81a-1ce6-4e35-a68a-246064b4b018" />


---

#### **Task 2: Initialize a Local Repository and Create a File**

```bash
mkdir week-4-challenge
cd week-4-challenge

# Initialize a new Git repository
git init

# Create a file with initial content
echo "Hi, I'm Ansh Gupta – a DevOps engineer exploring Git fundamentals!" > info.txt

# Stage and commit the file
git add info.txt
git commit -m "Initial commit: Add info.txt with introductory content"
```

---

<img width="1919" height="1006" alt="Image" src="https://github.com/user-attachments/assets/f0abff06-f2a8-4d13-bd42-dfe4dc0234d6" />


---

#### **Task 3: Configure Remote URL with PAT and Push/Pull**

```bash
# Configure or update the remote URL with PAT (for this exercise only)
git remote add origin https://<your-username>:<your-PAT>@github.com/<your-username>/90DaysOfDevOps.git
# Or update existing remote
git remote set-url origin https://<your-username>:<your-PAT>@github.com/<your-username>/90DaysOfDevOps.git

# Push changes to main
git branch -M main
git push -u origin main

# Optional: Pull from remote to verify connection
git pull origin main
```

---


<img width="1916" height="973" alt="Image" src="https://github.com/user-attachments/assets/3978f762-a734-4444-a5a6-c852c537c6f9" />

<img width="1919" height="973" alt="Image" src="https://github.com/user-attachments/assets/e2d46891-25cc-4793-bc43-0dd386bd3717" />

<img width="1919" height="1012" alt="Image" src="https://github.com/user-attachments/assets/54b23434-af50-4fb7-a9ef-8fa6fe685569" />



---

#### **Task 4: Explore Your Commit History**

```bash
# View commit history
git log
```

---

<img width="1919" height="1010" alt="Image" src="https://github.com/user-attachments/assets/b95216e9-5c66-48da-97c0-3288629dff12" />

---

#### **Task 5: Advanced Branching and Switching**

```bash
# Create and switch to a new branch
git branch feature-update
git switch feature-update
# OR
git checkout feature-update

# Edit the file and add more information
# e.g., using vim/nano/VS Code
vim info.txt

# Stage and commit the changes
git add info.txt
git commit -m "Feature update: Enhance info.txt with additional details"

# Push the new branch to remote
git push origin feature-update

# Merge to main via Pull Request on GitHub
```


**Optional Challenge – Merge Conflict Simulation**

```bash
# Create a conflicting branch
git checkout main
git checkout -b experimental

# Make a conflicting change in info.txt and commit
# Then switch back to feature-update
git switch feature-update

# Try to merge experimental into feature-update
git merge experimental

# Resolve conflict manually in info.txt using vim
# After resolving:
git add info.txt
git commit -m "Resolve merge conflict between feature-update and experimental"
```

---


<img width="1919" height="1012" alt="Image" src="https://github.com/user-attachments/assets/400bbb0a-8544-4483-b30b-925e7769b54b" />

---

<img width="1919" height="1017" alt="Image" src="https://github.com/user-attachments/assets/9314f3dd-85b7-47db-a0a1-362eccb8a1fe" />

---

<img width="1919" height="1014" alt="Image" src="https://github.com/user-attachments/assets/a9633fae-7ff6-437a-a8a6-567ed3d69aef" />

---

<img width="1919" height="1017" alt="Image" src="https://github.com/user-attachments/assets/e6e893cf-13a1-4255-b92c-941c202cc28d" />



---

## 🧠 Why Are Branching Strategies Important in Collaborative Development?

Branching strategies are critical in managing parallel work streams, improving collaboration, and ensuring a clean codebase.

#### ✅ 1. **Isolating Features and Bug Fixes**

By creating feature branches (e.g., `feature/signup-form`) or hotfix branches (e.g., `hotfix/login-error`), changes can be developed independently without affecting the main production-ready branch.

#### ✅ 2. **Facilitating Parallel Development**

Multiple team members can work on different features or bug fixes simultaneously without stepping on each other’s toes. This improves velocity and productivity.

#### ✅ 3. **Reducing Merge Conflicts**

Smaller and focused branches reduce the chances of merge conflicts. And when they occur, resolving them is easier in isolated code scopes.

#### ✅ 4. **Enabling Effective Code Reviews**

Pull Requests (PRs) from branches make it easier to track what changed, why, and allow other team members to give feedback before merging into the main branch.

---

## 🌿 Common Branching Strategies

| Strategy        | Description                                                                                                                                                             |
| --------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Git Flow**    | A structured model using multiple long-running branches (`main`, `develop`, `feature/`, `release/`, `hotfix/`). Great for complex projects with formal release cycles.  |
| **GitHub Flow** | Simple model. Create a branch → open a PR → review → merge into `main`. Works well for teams practicing continuous deployment.                                          |
| **Trunk-Based** | Developers commit directly to `main` (or short-lived branches) with frequent integration. Often combined with feature toggles. Suitable for high-velocity environments. |

