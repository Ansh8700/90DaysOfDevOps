# 4️⃣ Volume Management & Disk Usage

## 📝 Objective

The goal of this task is to understand basic volume management in Linux by creating a mount point, mounting a volume (or loop device), and verifying disk usage. This is essential for managing persistent storage in real-world DevOps environments.

---

## 📂 Steps to Follow

### 1️⃣ Create a Mount Point
```bash
sudo mkdir -p /mnt/devops_data
````

---

### 2️⃣ Create and Mount a Loop Device (For Practice)

If you're practicing locally and don't have an extra volume, you can use a file as a loopback device.

#### Step A: Create a 100MB file

```bash
sudo dd if=/dev/zero of=/devops_volume.img bs=1M count=100
```

#### Step B: Format the file with ext4 filesystem

```bash
sudo mkfs.ext4 /devops_volume.img
```

#### Step C: Mount the file to the mount point

```bash
sudo mount -o loop /devops_volume.img /mnt/devops_data
```

---

## ✅ Verification

### Check if the volume is mounted

```bash
mount | grep devops_data
```

### Check disk space usage

```bash
df -h | grep devops_data
```

---

## 📌 Notes

* If you’re working in a cloud VM or server with an extra block volume attached, replace the loop device step with actual device mount:

  ```bash
  sudo mount /dev/xvdf1 /mnt/devops_data
  ```

* Don’t forget to unmount when done:

  ```bash
  sudo umount /mnt/devops_data
  ```

---

## 🎯 Outcome

By completing this task, you'll gain hands-on experience with:

* Creating mount points
* Using loop devices
* Mounting volumes
* Verifying disk usage with `df` and `mount`


