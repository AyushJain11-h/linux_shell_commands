# 🐧 Linux Learning Notes for DevOps Engineers

A structured and beginner-friendly collection of **Linux concepts, commands, file system basics, permissions, user management, networking, automation, and archiving** — especially useful for **DevOps Engineers, System Administrators, and Linux beginners**.

This repository is based on Linux short notes and serves as a practical quick-reference guide for learning and revising essential Linux topics. It covers the most commonly used commands and administrative concepts that are important in real-world server environments. :contentReference[oaicite:0]{index=0}

---

# 📌 Table of Contents

- [Introduction to Linux](#-introduction-to-linux)
- [History of Linux](#-history-of-linux)
- [Linux File System Hierarchy](#-linux-file-system-hierarchy)
- [Basic Linux Commands](#-basic-linux-commands)
- [Creating Files and Directories](#-creating-files-and-directories)
- [Copy, Move, Rename and Delete Operations](#-copy-move-rename-and-delete-operations)
- [User Management](#-user-management)
- [Group Management](#-group-management)
- [Linux File Permissions](#-linux-file-permissions)
- [Access Control Lists (ACL)](#-access-control-lists-acl)
- [Regular Expressions and Grep](#-regular-expressions-and-grep)
- [Find Command](#-find-command)
- [Word Count, Head and Tail](#-word-count-head-and-tail)
- [Archiving with Tar](#-archiving-with-tar)
- [Job Automation (at and cron)](#-job-automation-at-and-cron)
- [Sudo Privileges](#-sudo-privileges)
- [Linux Networking Basics](#-linux-networking-basics)
- [Who Should Use These Notes?](#-who-should-use-these-notes)
- [Conclusion](#-conclusion)

---

# 🐧 Introduction to Linux

Linux is a **free and open-source operating system** widely used in servers, cloud environments, DevOps pipelines, cybersecurity, embedded systems, and enterprise infrastructure. It is highly stable, secure, and customizable, making it one of the most important operating systems in modern IT environments. :contentReference[oaicite:1]{index=1}

For DevOps engineers, Linux is a foundational skill because most servers, containers, CI/CD runners, and cloud systems are Linux-based.

---

# 📖 History of Linux

Linux belongs to the **Unix family** and was created by **Linus Torvalds** in **1991**. The initial Linux kernel source code was first shared publicly in September 1991, and it quickly gained popularity among developers and open-source communities. Over time, Linux evolved into one of the most powerful and widely adopted operating systems in the world. :contentReference[oaicite:2]{index=2}

Today, Linux powers:

- Web servers
- Cloud platforms
- DevOps infrastructure
- Containers and Kubernetes clusters
- Supercomputers
- Networking devices
- Enterprise systems

Linux has become a must-learn technology for anyone pursuing careers in **DevOps, Cloud Computing, Site Reliability Engineering (SRE), Cybersecurity, or System Administration**.

---

# 🗂 Linux File System Hierarchy

One of the most important Linux concepts is that **everything is treated as a file**, including devices and hardware. Linux follows a **single-rooted hierarchical file system**, represented by `/`, which is called the **root directory**. :contentReference[oaicite:3]{index=3}

## Important Linux Directories

### `/`
The root of the entire Linux file system. Every file and directory starts from here.

### `/root`
The home directory of the **root user** (superuser).

### `/bin`
Contains essential **binary executable files** used by all users, such as common Linux commands.

### `/sbin`
Contains **system binaries** generally used by administrators for system maintenance and configuration.

### `/dev`
Stores **device files** such as terminal devices, USB devices, disks, and other hardware interfaces.

### `/var`
Contains **variable data** such as:
- Logs (`/var/log`)
- Package databases (`/var/lib`)
- Mail files (`/var/mail`)
- Temporary system files (`/var/tmp`)

### `/mnt`
Used for **temporary mounting** of file systems.

### `/media`
Used for mounting **removable media devices** like USB drives, CDs, and external storage.

### `/usr`
Contains **user applications, libraries, and command binaries**.

### `/etc`
Stores **system-wide configuration files** and startup scripts.

### `/boot`
Contains files required for **booting the system**, including the Linux kernel and bootloader files.

### `/opt`
Used for **optional third-party software installations**.

### `/home`
Contains home directories for **normal users**.

### `/tmp`
Stores **temporary files** created by the system and users. These may be cleared on reboot.

Understanding the Linux file system hierarchy is essential for managing servers, troubleshooting issues, and navigating the operating system efficiently. :contentReference[oaicite:4]{index=4}

---

# 💻 Basic Linux Commands

Linux commands are the foundation of working in a terminal-based environment. Below are some commonly used commands every beginner should know. :contentReference[oaicite:5]{index=5}

| Command | Description |
|--------|-------------|
| `pwd` | Shows the present working directory |
| `ls` | Lists files and directories |
| `uname` | Displays system/kernel information |
| `uname -r` | Shows the kernel version |
| `cd` | Changes directory |
| `clear` | Clears the terminal screen |
| `whoami` | Displays the current logged-in user |
| `history` | Shows previously used commands |
| `date` | Displays current date and time |

These commands are used daily by Linux users, system administrators, and DevOps engineers.

---

# 📁 Creating Files and Directories

Linux provides simple commands to create directories and files efficiently. :contentReference[oaicite:6]{index=6}

## Create Directories
Use the `mkdir` command to:
- Create a single directory
- Create multiple directories
- Create nested directories
- Create numbered directories

### Examples:
```bash
mkdir project
mkdir dir1 dir2 dir3
mkdir -p parent/child/grandchild
mkdir folder{1..5}
