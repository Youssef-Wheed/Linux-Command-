# 🐧 Linux Command Line Guide – Complete with Explanation & Examples

This document summarizes essential Linux command-line concepts and tools, presented with clear explanations and practical examples. It is formatted for a `README.md` file on GitHub.

---

## 📁 Linux Directory Structure (FHS - Filesystem Hierarchy Standard)

| Directory                  | Description                                                                               |
| -------------------------- | ----------------------------------------------------------------------------------------- |
| `/`                        | Root directory – the top-level of the filesystem. All other directories branch from here. |
| `/boot`                    | Contains boot files (e.g., Linux kernel, GRUB).                                           |
| `/bin`                     | Essential command binaries (e.g., `ls`, `cp`).                                            |
| `/sbin`                    | System binaries for superuser tasks (e.g., `shutdown`, `ifconfig`).                       |
| `/lib`, `/lib64`           | Shared libraries for binaries in `/bin` and `/sbin`.                                      |
| `/home`                    | User home directories (e.g., `/home/ahmed`).                                              |
| `/root`                    | Root user’s home directory.                                                               |
| `/usr`                     | User-installed apps, docs, and libraries.                                                 |
| `/etc`                     | System-wide configuration files.                                                          |
| `/tmp`                     | Temporary files (deleted on reboot).                                                      |
| `/opt`                     | Optional and 3rd-party software packages.                                                 |
| `/proc`, `/sys`, `/run`    | Virtual filesystems for kernel, runtime, and system data.                                 |
| `/dev`                     | Device files (e.g., `/dev/sda`).                                                          |
| `/mnt`, `/media`, `/cdrom` | Mount points for devices or removable media.                                              |
| `/srv`                     | Service data for servers (e.g., FTP, HTTP).                                               |
| `/var`                     | Variable files (logs, emails, etc.).                                                      |

---

## 💼 File Management Interfaces

* **CLI (Command Line Interface)** – Powerful, scriptable terminal-based interface.
* **GUI (Graphical User Interface)** – Visual file managers like Nautilus, Dolphin.

---

## 🧾 Basic File Operations

* **Browse**: `ls`, `cd`, `pwd`
* **Create & Rename**: `touch`, `mv`
* **Move**: `mv file path`
* **Delete**: `rm`, `rm -r`
* **Copy**: `cp`, `cp -r`

---

## 🧪 Terminal & System Commands

### User & System Info

```bash
who         # Logged-in users
uname -a    # System & kernel info
cal         # Calendar
date        # Current date & time
```

### Network & Monitoring

```bash
ifconfig    # Network interfaces
 top         # Live process viewer
time cmd    # Time taken by a command
times       # Shell and child process times
```

### Output

```bash
echo "text"     # Print text
printf "%s" text # Formatted output
```

### Help

```bash
man command     # Manual page
info command    # Info page
help            # Built-in command help
```

### Terminal Utilities

```bash
clear       # Clear terminal
reset       # Reset terminal
exit        # Close terminal
history     # Show command history
```

---

## 📂 Navigating Files and Directories

```bash
pwd              # Show current directory
ls               # List directory contents
cd folder        # Change directory
touch file.txt   # Create file
cat file.txt     # View file content
```

Special Paths:

* `~` = Home
* `..` = Parent directory

---

## 📤 Copying, Moving, Deleting

```bash
cp file1 path/           # Copy file
cp -r dir path/          # Copy directory
mv file1 path/           # Move/rename file
rm file1                 # Remove file
rm -r dir                # Remove directory
```

---

## 📁 Directory Management

```bash
mkdir new_folder         # Create directory
rmdir empty_folder       # Remove empty directory
```

---

## 📄 Listing and Creating Files

### Using `ls` Options:

```bash
ls -a        # All files (incl. hidden)
ls -l        # Long listing with details
ls -R        # Recursive listing
ls -la       # Combined view
```

### Creating and Editing Files:

```bash
touch file.txt       # Empty file
cat > file.txt       # Overwrite file with input
cat >> file.txt      # Append to file
nano file.txt        # Easy text editor
vi file.txt          # Advanced text editor
```

---

## ✏️ File Content Management

```bash
cat file1 > file2     # Copy
cat file1 >> file2    # Append
cat file1 file2 > file3  # Merge files
```

### Viewing Content:

```bash
cat file.txt       # Normal
nl file.txt        # With line numbers
tac file.txt       # Reverse
```

### Search & Count:

```bash
grep "word" file.txt     # Search
wc file.txt              # Count lines, words, characters
wc -l/-w/-c file.txt     # Specific counts
```

---

## 🔐 File Permissions

### Entities:

* **User** (owner)
* **Group**
* **Others**

### Permission Types:

| Symbol | Meaning |
| ------ | ------- |
| r      | Read    |
| w      | Write   |
| x      | Execute |

### Numeric (Octal) Mode:

| Value | Permission |
| ----- | ---------- |
| 7     | rwx (full) |
| 6     | rw-        |
| 5     | r-x        |
| 4     | r--        |
| 0     | ---        |

```bash
chmod 755 file.txt      # Owner: all, others: read/execute
```

### Symbolic Mode:

```bash
chmod g+w file.txt      # Add write to group
chmod o-r file.txt      # Remove read from others
```

---

## 👑 Ownership and Groups

```bash
chown user file.txt            # Change owner
chown user:group file.txt      # Change owner & group
chgrp group file.txt           # Change group only
groups                        # View current user groups
```

---

## 🔍 Advanced File Tools

### `head` & `tail`

```bash
head file.txt             # First 10 lines
head -n 5 file.txt        # First 5 lines
tail file.txt             # Last 10 lines
tail -n +20 file.txt      # From line 20 onward
```

### File Search & Location

```bash
which ls                     # Full path
whereis ls                   # Binary + source + man page
locate filename              # Fast search
find /home -name "*.txt"     # Deep search
```

---

## 🧠 System Info

```bash
ps aux                  # Running processes
w                       # Who is logged in
id                      # User & group ID
df -h                   # Disk usage
free -m                 # RAM usage
cat /proc/cpuinfo       # CPU info
cat /proc/meminfo       # RAM details
```

---

## 🧩 Special Characters

| Symbol | Use                       |
| ------ | ------------------------- |
| \\     | Escape                    |
| /      | Path separator            |
| .      | Current dir / hidden file |
| ..     | Parent directory          |
| \~     | Home directory            |
| \*     | Wildcard                  |
| >      | Redirect output           |
| >>     | Append output             |
| <      | Input redirection         |
| ;      | Run multiple commands     |

```bash
echo Hello > file.txt     # Create or overwrite
cat file.txt | grep word # Pipe example
cd ~/Docs; ls -l         # Chained commands
```

---

> *This guide covers essential Linux basics for navigating, managing, and interacting with the system via the command line. Perfect for beginners and intermediate* users!
