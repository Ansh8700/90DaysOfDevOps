# Linux User & Access Configuration

This task outlines the configuration of a secure user environment on a Linux system. We will create a new user, assign them to a team group, enable administrative privileges, and restrict SSH access to control remote logins.

---

## 🗂️ Section 1: Creating a User and a Group

### Creating a User: `devops_user`

To initiate user setup, begin by adding a new user to the system. The `adduser` utility simplifies the process by also prompting for password and metadata input.

```bash
sudo adduser devops_user
```

If a more manual approach is preferred (e.g., in scripts), `useradd` can be used with the `-m` flag to ensure a home directory is created:

```bash
sudo useradd -m devops_user
```

---

### Creating a Group: `devops_team`

A group is essential for managing permission boundaries among related users.

```bash
sudo groupadd devops_team
```

---

### Associating the User with the Group

Users can belong to multiple groups. To add `devops_user` to `devops_team`, use either of the following:

```bash
sudo usermod -aG devops_team devops_user
```

or

```bash
sudo gpasswd -a devops_user devops_team
```

---

### Verifying Membership

Use these commands to confirm that the user and group are properly configured:

```bash
id devops_user
groups devops_user
```

The expected output should show `devops_user` as a member of both their default group and `devops_team`.

---

## 🔐 Section 2: Setting Passwords and Privileges

### Defining a Password

If not already configured during creation, assign a password using:

```bash
sudo passwd devops_user
```

---

### Enabling Sudo Rights

To delegate administrative (sudo) capabilities:

```bash
sudo usermod -aG sudo devops_user
```

To test sudo functionality, switch to the user and run a privileged command:

```bash
su - devops_user
sudo whoami
```

---

### Sudo Access by Group (Optional)

To authorize all members of `devops_team` with sudo access, modify the `/etc/sudoers` file via the recommended tool:

```bash
sudo visudo
```

Add the line:

```
%devops_team ALL=(ALL:ALL) ALL
```

This allows any member of the group to execute commands as root.

---

## 🔐 Section 3: Restricting SSH Logins

### Modifying SSHD Configuration

To control which users are allowed to log in via SSH, edit the SSH daemon configuration:

```bash
sudo nano /etc/ssh/sshd_config
```

To allow only specific users:

```
AllowUsers devops_user
```

Alternatively, to block specific users:

```
DenyUsers testuser admin
```

---

### Restarting SSH

After making changes, the SSH service must be reloaded:

```bash
sudo systemctl restart sshd
```

---

### Validating SSH Access

Determine the system's IP address with:

```bash
ip a
```

Then test access from a client machine:

```bash
ssh devops_user@<IP_ADDRESS>
```

Replace `<IP_ADDRESS>` with the actual address of the machine.

---

## ✅ Summary of Changes

✅ **User Created**: `devops_user`

✅ **Group Created**: `devops_team`

✅ **User Added to Group**

✅ **Password Assigned**

✅ **Sudo Access Granted**

✅ **SSH Access Controlled**

✅ **Service Restarted and Verified**

---

## 📁 Files Impacted

- `/etc/passwd` — User record
- `/etc/group` — Group definitions
- `/etc/sudoers` — Administrative policy (if modified)
- `/etc/ssh/sshd_config` — SSH login rules
