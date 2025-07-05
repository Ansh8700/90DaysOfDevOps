# 5️⃣ Process Management & Monitoring

## 🎯 Objective

Learn how to manage and monitor processes on a Linux system using built-in utilities like `ps`, `top`, and `htop`.

---

## 📌 Task Steps

### 1. **Start a Background Process**

Use the `ping` command to continuously ping `google.com` and redirect the output to a file in the background:

```bash
ping google.com > ping_test.log &
```

This will start the ping process and run it in the background.

> 💡 The `&` symbol sends the process to the background. The shell will output a job ID and PID.

---

### 2. **Monitor the Process**

#### a. **Using `ps`**

List all running processes and filter for `ping`:

```bash
ps aux | grep ping
```

#### b. **Using `top`**

Launch the interactive `top` command and look for the `ping` process:

```bash
top
```

Use `/` inside `top` to search for "ping".

#### c. **Using `htop`** *(if installed)*

Start `htop`:

```bash
htop
```

Scroll or search (`F3`) for the `ping` process.

> ✅ You can install `htop` via `sudo apt install htop` or `sudo yum install htop` if not available.

---

### 3. **Kill the Process**

First, find the PID using `ps` or `htop`, then terminate it:

```bash
kill <PID>
```

Or use `killall`:

```bash
killall ping
```

---

### 4. **Verify the Process is Terminated**

Check again using:

```bash
ps aux | grep ping
```

You should no longer see the `ping` process running.

Also check if the output file exists:

```bash
cat ping_test.log
```

---

## ✅ Outcome

You should now be able to:

* Run a process in the background
* Monitor it using `ps`, `top`, and `htop`
* Safely terminate a running process
* Confirm its removal from the system

