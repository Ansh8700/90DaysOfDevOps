# ✅ Task 1: Working with Pull Requests (PRs)

## 🔧 Steps to Create a Pull Request:

#### 1. **Fork and Clone the Repository:**

   ```bash
   git clone <your-forked-repo-url>
   cd <repo-name>
   ```

#### 2. **Create a Feature Branch:**

   ```bash
   git checkout -b feature-branch
   echo "New Feature" >> feature.txt
   git add .
   git commit -m "Added a new feature"
   ```

#### 3. **Push to GitHub and Create PR:**

   ```bash
   git push origin feature-branch
   ```

   * Go to your forked repository on GitHub.
   * Click on “Compare & Pull Request.”
   * Add a meaningful title and description.
   * Request a review and merge once approved.

### 🧠 Best Practices for PR Descriptions:

* **Title:** Clear and concise summary of the changes.
* **Description:**

  * What does this PR do?
  * Why is it needed?
  * Screenshots or logs if UI-related or bug fixes.
  * Mention related issues (e.g., “Fixes #42”).

### 💬 Handling Review Comments:

* Always respond professionally.
* Make requested changes or explain why not.
* Push updates using `git push` (GitHub auto-updates the PR).
* Mark conversations as resolved when appropriate.

