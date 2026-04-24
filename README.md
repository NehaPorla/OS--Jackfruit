# 🐳 OS Jackfruit - Container Runtime

---

## 👩‍💻 Team Members

| Role | Name | SRN |
|------|------|-----|
| Member 1 | Porla Neha | PES1UG25AM808 |
| Member 2 | Pradeep R | PES1UG25AM810 |

---

## 📌 Project Overview

This project implements a basic **container runtime** using **C programming** and **Linux system calls**.  
The goal is to understand how containers work internally **without using tools like Docker**.

The container runtime provides **process isolation** using `chroot()` and executes commands inside an isolated filesystem *(rootfs)*.

---

## 🎯 Objectives

- 📦 Understand container fundamentals
- 🔒 Implement process isolation using `chroot()`
- ⚙️ Execute commands inside isolated environments
- 🛠️ Manage containers using custom commands
- 📚 Learn Linux system calls like `fork()`, `exec()`, `kill()`

---

## 🚀 Tasks Implemented

| Task | Description | Status |
|------|-------------|--------|
| Task 1 | Run Container (Foreground) | ✅ Done |
| Task 2 | Background Container Execution | ✅ Done |
| Task 3 | Logging Mechanism | ✅ Done |
| Task 4 | Stop Container | ✅ Done |
| Task 5 | Root Filesystem Isolation | ✅ Done |
| Task 6 | Multiple Container Execution | ✅ Done |

### ✅ Task 1: Run Container (Foreground)
- Implemented container execution using `fork()` and `chroot()`
- Runs commands inside isolated root filesystem

### ✅ Task 2: Background Container Execution
- Used `fork()` to run containers in background
- Allows multiple containers to run simultaneously

### ✅ Task 3: Logging Mechanism
- Redirected container output using `dup2()`
- Logs stored in `logs.txt` inside rootfs

### ✅ Task 4: Stop Container
- Implemented container stopping using `kill()` / `pkill`
- Allows termination of running container processes

### ✅ Task 5: Root Filesystem Isolation
- Used **Alpine Linux** rootfs
- Verified isolation using `/etc/os-release`

### ✅ Task 6: Multiple Container Execution
- Demonstrated running multiple containers simultaneously
- Managed using process IDs (PID)

---

## ⚙️ Commands Used

### 🔹 Compile the Project
```bash
make
```

### 🔹 Run Container (Foreground)
```bash
sudo ./engine run c1 ../rootfs-alpha /bin/sh
```

### 🔹 Start Container (Background)
```bash
sudo ./engine start c1 ../rootfs-alpha sleep 100
```

### 🔹 View Running Processes
```bash
ps aux | grep sleep
```

### 🔹 View Logs
```bash
cat ../rootfs-alpha/logs.txt
```

### 🔹 Stop Container
```bash
sudo pkill sleep
```

---

## 📸 Screenshots

### 🔹 Task 1: Run Container
<img width="707" height="456" alt="Screenshot 2026-04-24 150629" src="https://github.com/user-attachments/assets/1f27e7ed-9baa-4074-aca7-d44763f894e3" />

### 🔹 Task 2: Background Container Execution
<img width="698" height="447" alt="Screenshot 2026-04-24 150618" src="https://github.com/user-attachments/assets/5cd65d8b-1ed7-49e0-bb61-2251740a0e5d" />

### 🔹 Task 3: Logs Output
<img width="693" height="454" alt="Screenshot 2026-04-24 150609" src="https://github.com/user-attachments/assets/b475d1d2-9388-4f58-840a-ce0b64780bc2" />

### 🔹 Task 4: Stop Container
<img width="697" height="450" alt="Screenshot 2026-04-24 150600" src="https://github.com/user-attachments/assets/14c2a545-7d19-42ee-9418-984ff6f38547" />

### 🔹 Task 5: Root Filesystem (Alpine Linux)
<img width="697" height="450" alt="Screenshot 2026-04-24 150550" src="https://github.com/user-attachments/assets/c1ae4ed3-8917-42ea-a5a2-59baeba9f98c" />

### 🔹 Task 6: Multiple Containers
<img width="701" height="447" alt="Screenshot 2026-04-24 150538" src="https://github.com/user-attachments/assets/087f4cc2-1482-4934-a9d3-ac676db746e4" />

---

## 🧠 Key Concepts Used

| System Call | Purpose |
|-------------|---------|
| `fork()` | Creates a new process for container execution |
| `chroot()` | Changes root directory to isolate filesystem |
| `exec()` / `execl()` | Executes commands inside the container |
| `dup2()` | Redirects output to log files |
| `kill()` / `pkill` | Terminates running container processes |
| Process Isolation | Each container runs independently |
| Root Filesystem (rootfs) | Provides separate environment for container |

---

## 🎯 Conclusion

This project successfully demonstrates the working of a **basic container runtime** using low-level Linux system calls.  
It provides insights into how modern container technologies like **Docker** operate internally.

Through this implementation, we learned:
- ✅ Process creation
- ✅ Filesystem isolation
- ✅ Command execution
- ✅ Logging mechanisms
- ✅ Container lifecycle management

> The project serves as a strong foundation for understanding advanced containerization technologies and system-level programming.

---
