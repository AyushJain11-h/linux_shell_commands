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


## 📁 Creating Files and Directories

Linux provides simple commands to create directories and files efficiently.

### Create Files

Use the `touch` command to create empty files.

#### Examples:
```bash
touch file1.txt
touch file1.txt file2.txt file3.txt
touch file{1..5}.txt
```

The `touch` command is useful for creating placeholder files quickly.

---

## 📂 Copy, Move, Rename and Delete Operations

File and directory management is a core Linux skill.

### Copy Files and Directories

The `cp` command is used to copy files and folders.

#### Syntax:
```bash
cp [options] source destination
```

#### Common Options:
- `-r` → recursive copy  
- `-v` → verbose output  
- `-f` → force overwrite  

#### Examples:
```bash
cp file1.txt backup/
cp -r myfolder backup/
cp D* backup/
```

### Move Files and Directories

The `mv` command is used to move files or rename them.

#### Examples:
```bash
mv file1.txt /home/user/Documents/
mv oldname.txt newname.txt
```

### Remove Files and Directories

The `rm` command is used to delete files and directories.

#### Examples:
```bash
rm file1.txt
rm -r myfolder
```

These commands are heavily used in Linux administration and scripting.

---

## 👤 User Management

Linux is a multi-user operating system, so managing users is a critical administrative task.

### Common User Management Tasks:
- Creating user accounts  
- Assigning passwords  
- Viewing account details  
- Switching between users  
- Deleting users  
- Modifying login names  

### Common Commands:
```bash
useradd username
passwd username
id username
su - username
userdel username
usermod -l newname oldname
```

User management is especially important for access control and system security.

---

## 👥 Group Management

A **group** in Linux is a collection of users that helps administrators manage permissions more efficiently. Instead of assigning permissions to users one by one, you can assign them to groups.

### Group Management Tasks:
- Create a group  
- View group information  
- Add users to a group  
- Remove users from a group  
- Assign group administrators  
- Delete a group  

### Common Commands:
```bash
groupadd developers
groupdel developers
groupmod -n newgroup oldgroup
gpasswd -a username developers
gpasswd -d username developers
```

Groups are useful in shared server environments where multiple users need access to the same files or directories.

---

## 🔐 Linux File Permissions

Linux uses a permission model to control access to files and directories. Permissions determine who can **read**, **write**, or **execute** a file.

### Permission Categories
- **Owner (u)** → The user who owns the file  
- **Group (g)** → The group assigned to the file  
- **Others (o)** → All other users  

### Permission Types
- `r` → Read = `4`  
- `w` → Write = `2`  
- `x` → Execute = `1`  

### View Permissions
```bash
ls -l
```

### Change Permissions

Use the `chmod` command.

#### Examples:
```bash
chmod u+r file.txt
chmod g+rw file.txt
chmod o-r file.txt
chmod 755 script.sh
chmod 644 file.txt
```

### Change Ownership

Use `chown` and `chgrp`.

#### Examples:
```bash
chown user file.txt
chgrp developers file.txt
chown user:developers file.txt
```

Understanding permissions is essential for Linux security, server management, and DevOps workflows.

---

## 🛡 Access Control Lists (ACL)

ACL (**Access Control List**) provides a more flexible permission mechanism than traditional Linux permissions. ACL allows administrators to assign permissions to **specific users or groups** without changing the main owner/group structure.

This is especially useful when:
- A user is **not part of a group**
- But still needs access to a specific file or directory

### Common ACL Commands

#### Check ACL Permissions
```bash
getfacl filename
```

#### Set ACL for a User
```bash
setfacl -m u:username:rwx filename
```

#### Remove ACL for a User
```bash
setfacl -x u:username filename
```

#### Set ACL for a Group
```bash
setfacl -m g:groupname:rwx filename
```

#### Remove All ACLs
```bash
setfacl -b filename
```

ACLs are commonly used in enterprise Linux systems where fine-grained access control is required.

---

## 🔍 Regular Expressions and Grep

Regular expressions help search and match text patterns efficiently. Linux uses the `grep` command to search for strings and patterns inside files.

### Common `grep` Use Cases

#### Search a word in a file
```bash
grep "error" logfile.txt
```

#### Search in multiple files
```bash
grep "error" *.txt
```

#### Case-insensitive search
```bash
grep -i "linux" notes.txt
```

#### Recursive search
```bash
grep -r "config" /etc/
```

#### Invert match
```bash
grep -v "success" logfile.txt
```

#### Show line numbers
```bash
grep -n "main" app.py
```

#### Search lines starting with a string
```bash
grep "^start" file.txt
```

#### Search lines ending with a string
```bash
grep "end$" file.txt
```

`grep` is one of the most powerful tools for searching logs, configurations, scripts, and source code.

---

## 🔎 Find Command

The `find` command is one of the most useful Linux commands for locating files and directories based on various conditions. It is commonly used by administrators and DevOps engineers to search files by name, size, permissions, user ownership, and more.

### Common Examples

#### Find files in home directory
```bash
find /home -type f
```

#### Find files with SUID permission
```bash
find / -perm -4000
```

#### Find files with SGID permission
```bash
find / -perm -2000
```

#### Find files with sticky bit
```bash
find / -perm -1000
```

#### Find files by user
```bash
find / -user username
```

#### Find files by group
```bash
find / -group groupname
```

#### Find files smaller than 10MB
```bash
find /folder -size -10M
```

#### Find files larger than 10MB
```bash
find /folder -size +10M
```

This command is extremely useful in troubleshooting, cleanup tasks, and system audits.

---

## 📊 Word Count, Head and Tail

These commands are used for viewing and analyzing file content quickly.

### `wc` – Word Count

Used to count lines, words, and characters.

#### Examples:
```bash
wc file.txt
wc -l file.txt
wc -w file.txt
```

### `head`

Displays the top lines of a file.

#### Examples:
```bash
head file.txt
head -n 20 file.txt
```

### `tail`

Displays the bottom lines of a file.

#### Examples:
```bash
tail file.txt
tail -n 20 file.txt
```

These are commonly used while checking logs and configuration files.

---

## 📦 Archiving with Tar

The `tar` command is used for **archiving and compressing files/directories** in Linux. It is especially useful for backups, packaging, and transferring multiple files as a single archive. Linux supports multiple compression formats such as **gzip**, **bzip2**, and **xz**.

### Common Tar Options
- `c` → Create archive  
- `x` → Extract archive  
- `v` → Verbose output  
- `f` → File name  
- `t` → List archive contents  
- `z` → gzip compression  
- `j` → bzip2 compression  
- `J` → xz compression  
- `C` → Extract to a specific location  

### Examples

#### Create a tar archive
```bash
tar -cvf backup.tar folder/
```

#### Extract a tar archive
```bash
tar -xvf backup.tar
```

#### Extract to a specific location
```bash
tar -xvf backup.tar -C /destination/path
```

#### Create gzip-compressed archive
```bash
tar -czvf backup.tar.gz folder/
```

#### Extract gzip archive
```bash
tar -xzvf backup.tar.gz
```

#### Create bzip2 archive
```bash
tar -cjvf backup.tar.bz2 folder/
```

#### Extract bzip2 archive
```bash
tar -xjvf backup.tar.bz2
```

#### Create xz archive
```bash
tar -cJvf backup.tar.xz folder/
```

#### Extract xz archive
```bash
tar -xJvf backup.tar.xz
```

Archiving is a very important Linux skill for backups and deployment packaging.

---

## ⏰ Job Automation (`at` and `cron`)

Linux supports job automation, allowing users and administrators to schedule tasks to run automatically. This is extremely useful for backups, scripts, updates, maintenance tasks, and recurring jobs.

### Two Types of Job Automation

#### 1. `at`
Used to execute a job **only once** at a specified time.

#### 2. `crontab`
Used to execute a job **repeatedly** at scheduled intervals.

### `at` Command Examples
```bash
at 10:30 PM
atq
atrm 1
```

### `cron` Command Examples
```bash
crontab -e
crontab -l
crontab -r
```

### Example Cron Job
```bash
0 2 * * * /home/user/backup.sh
```

This runs the script every day at **2:00 AM**.

Job automation is a core skill for DevOps engineers because many server operations must run without manual intervention.

---

## 🔑 Sudo Privileges

The `sudo` command allows a permitted user to run commands as another user, usually the **root user**. It is one of the most important security and administration features in Linux.

### Why `sudo` is Important
- Prevents direct root login for routine tasks  
- Improves security  
- Allows controlled privilege escalation  
- Enables administrative actions safely  

### Granting Sudo Access

Sudo permissions are typically managed using:

```bash
/etc/sudoers
```

#### Example Entry
```bash
username ALL=(ALL) ALL
```

#### Passwordless Sudo
```bash
username ALL=(ALL) NOPASSWD: ALL
```

### Wheel Group

Linux systems often use the **wheel** group to grant sudo privileges.

#### Example:
```bash
usermod -aG wheel username
```

This is a common practice in Red Hat-based systems.

---

## 🌐 Linux Networking Basics

Networking is a critical part of Linux administration, especially in server and DevOps environments. Linux provides tools to manage IP addresses, interfaces, connections, and hostnames.

### Check IP Address
```bash
ip a
```

### Network Management Tools

#### `nmcli`

A command-line tool used to manage networking through **NetworkManager**.

### Common `nmcli` Commands
```bash
nmcli con show
nmcli con show --active
nmcli dev status
nmcli con up connection_name
nmcli con down connection_name
nmcli con delete connection_name
hostnamectl set-hostname new-hostname
hostname
```

### Example Static IP Configuration
```bash
nmcli con mod "citynet" ipv4.addresses 192.168.0.100/24
nmcli con mod "citynet" ipv4.gateway 192.168.0.254
nmcli con mod "citynet" ipv4.dns 192.168.0.254
nmcli con mod "citynet" ipv4.method manual
nmcli con down citynet
nmcli con up citynet
```

### `nmtui`

A text-based interface for configuring network settings interactively.

Networking knowledge is essential for managing Linux servers, cloud VMs, and enterprise infrastructure.

---

## 🎯 Who Should Use These Notes?

These Linux notes are especially useful for:

- Beginners learning Linux  
- DevOps Engineers  
- System Administrators  
- Cloud Engineers  
- Site Reliability Engineers (SREs)  
- Students preparing for Linux interviews  
- Anyone working with servers or terminal environments  

---

## 🚀 Why Linux is Important for DevOps

Linux is the backbone of modern DevOps and cloud infrastructure. Most tools and platforms used in DevOps run on Linux, including:

- Docker  
- Kubernetes  
- Jenkins  
- GitLab CI/CD  
- Ansible  
- Terraform  
- Nginx  
- Apache  
- Cloud Virtual Machines  

A strong Linux foundation helps in:

- Managing servers  
- Writing shell scripts  
- Troubleshooting applications  
- Automating deployments  
- Configuring permissions and networking  
- Handling production environments  

---

## ✅ Conclusion

Linux is one of the most essential skills for anyone entering the world of **DevOps**, **Cloud**, or **System Administration**. These notes provide a compact yet practical overview of the most important Linux topics, from basic commands and file management to permissions, networking, automation, and system administration.

This repository can be used as:

- A quick Linux revision guide  
- A DevOps interview preparation resource  
- A beginner Linux reference  
- A practical command handbook  

If you're learning Linux for DevOps, this README is a strong starting point for building your command-line and administration skills.

---

## ⭐ Support

If you found this helpful, feel free to:

- ⭐ Star this repository  
- 🍴 Fork this repository  
- 🛠 Contribute improvements  
- 📘 Use it for your Linux learning journey  

---

# 🔥 Suggested Repository Titles

Use one of these:

- **Linux Learning Notes for DevOps**
- **Linux Short Notes for Beginners & DevOps Engineers**
- **Linux Essentials for DevOps Engineers**
- **Complete Linux Basics for DevOps**

---

# ✅ Best GitHub README Intro

```md
# 🐧 Linux Learning Notes for DevOps Engineers

A well-structured collection of Linux notes covering **commands, file system hierarchy, permissions, user management, automation, networking, and system administration**.

This repository is designed for **beginners, students, and DevOps engineers** who want a quick yet practical Linux reference for learning, revision, and interview preparation.
```
