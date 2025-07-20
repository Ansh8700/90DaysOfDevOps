# 🔐 Bonus Task: Explore SSH Authentication

### 1. Generate an SSH Key (if not already set up)

#### To generate a new SSH key pair:

```bash
ssh-keygen
```

* When prompted, press `Enter` to accept the default file location (usually `~/.ssh/id_ed25519`).
* Optionally, set a passphrase for added security.

#### After generation, your public key will be located at:

```bash
~/.ssh/id_ed25519.pub
```

#### To display it:

```bash
cat ~/.ssh/id_ed25519.pub
```

---

### 2. Add Your SSH Public Key to GitHub

#### * Copy the contents of your public key:

```bash
cat ~/.ssh/id_ed25519.pub | clip  # (Windows Git Bash)
cat ~/.ssh/id_ed25519.pub         # (Linux/macOS, then copy manually)
```

#### * Go to **GitHub → Settings → SSH and GPG keys → New SSH key**

  * Give it a title (e.g., "My Laptop")
  * Paste the copied key
  * Click **Add SSH key**

[🔗 GitHub Docs: Connecting to GitHub with SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

---

### 3. Switch Your Remote URL to SSH

#### Change your GitHub remote from HTTPS to SSH:

```bash
git remote set-url origin git@github.com:<your-username>/90DaysOfDevOps.git
```

#### ✅ Confirm the change:

```bash
git remote -v
```

#### You should now see something like:

```
origin  git@github.com:your-username/90DaysOfDevOps.git (fetch)
origin  git@github.com:your-username/90DaysOfDevOps.git (push)
```

---

### 4. Push Your Branch Using SSH

#### To test the SSH connection and push your changes:

```bash
git push origin feature-update
```

If everything is set up correctly, you’ll be prompted for your SSH key passphrase (if you set one), and the push will succeed without asking for your GitHub username or password.

<img width="1919" height="1015" alt="Image" src="https://github.com/user-attachments/assets/efbe0a81-eae5-4fa7-8f13-7efe76ff12bd" />

---

<img width="1919" height="973" alt="Image" src="https://github.com/user-attachments/assets/f7c33a22-e783-427f-94d6-da2418a0c579" />

---

<img width="1919" height="976" alt="Image" src="https://github.com/user-attachments/assets/4f4bdf6e-424a-42a4-8777-0bdcfef482a6" />

---

<img width="1919" height="975" alt="Image" src="https://github.com/user-attachments/assets/3f61f081-b223-4871-8888-cf22639d2124" />

---

<img width="1919" height="1016" alt="Image" src="https://github.com/user-attachments/assets/9ef3a8ee-f00a-4832-85cf-38d135f51af8" />