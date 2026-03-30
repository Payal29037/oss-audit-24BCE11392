# -LINUX-OSS-audit-24BCE11392
# OSS Audit — Git (Version Control System)
### Open Source Software | VIT Bhopal University

| Field | Detail |
|-------|--------|
| **Student Name** | Payal Kushwaha|
| **Registration No.** | [24BCE11392] |
| **Course** | Open Source Software (OSS NGMC) |
| **Institution** | VIT Bhopal University |
| **Software Audited** | Git — Version Control System |
| **License** | GNU GPL v2 |

---

## About This Project

This repository contains the complete submission for the **Open Source Audit** capstone project for the OSS NGMC course at VIT Bhopal. The project involves a structured audit of **Git**, one of the most important open-source tools ever created, covering its origin story, license analysis, Linux footprint, FOSS ecosystem, and a critical comparison with proprietary alternatives.

The repository also contains five shell scripts that demonstrate practical Linux command-line skills, written and tested on Ubuntu (WSL).

---

## Chosen Software — Git

**Git** is a free and open-source distributed version control system created by Linus Torvalds in 2005. It was built in response to the revocation of the free-of-charge BitKeeper license used by the Linux kernel community. Licensed under **GNU GPL v2**, Git is the most widely used version control system in the world and forms the backbone of platforms like GitHub, GitLab, and Bitbucket.

- **Official Website:** https://git-scm.com
- **Source Code:** https://github.com/git/git
- **License:** GNU General Public License v2.0

---

## Repository Structure

```
oss-audit-[24BCE11392]/
│
├── README.md                          ← This file
├── OSS_Capstone_Git_Report.pdf        ← Project report (upload separately
├── script1_system_identity.sh     ← System Identity Report
├── script2_foss_inspector.sh      ← FOSS Package Inspector
├── script3_disk_permission_auditor.sh  ← Disk and Permission Auditor
├── script4_log_analyzer.sh        ← Log File Analyzer
└── script5_manifesto_generator.sh ← Open Source Manifesto Generator
```

---

## Script Descriptions

### Script 1 — System Identity Report
Displays a formatted welcome-screen style system report including the Linux distribution name, kernel version, logged-in user, home directory, system uptime, current date/time, and the OS license information.

**Concepts used:** Variables, command substitution `$()`, `echo`, `uname`, `whoami`, `uptime`, `date`, `if/elif/else`

---

### Script 2 — FOSS Package Inspector
Checks whether a given open-source package is installed on the system. Detects the package manager (dpkg or rpm), displays version and metadata, and uses a `case` statement to print a philosophy note about the package.

**Concepts used:** Command-line arguments `$1`, `if-then-else`, `case` statement, `dpkg -l`, `rpm -qi`, pipe with `grep`

---

### Script 3 — Disk and Permission Auditor
Loops through a list of important Linux system directories and reports each directory's permissions, owner, group, and disk usage in a formatted table. Also audits Git-specific paths.

**Concepts used:** Bash arrays, `for` loop, `ls -ld`, `awk`, `du -sh`, `cut`, `printf` for formatted output

---

### Script 4 — Log File Analyzer
Reads a log file line by line, counts how many lines contain a specified keyword (case-insensitive), and prints the last 5 matching lines. Includes retry logic if the file is empty.

**Concepts used:** `while IFS= read -r` loop, `if-then`, counter variables `$(())`, command-line arguments, `grep -i`, `tail`, `wc -l`

---

### Script 5 — Open Source Manifesto Generator
Interactively asks the user three questions and generates a personalised open-source philosophy statement, saving it to a `.txt` file named after the current user.

**Concepts used:** `read -p` for user input, string concatenation, file output with `>` and `>>`, `date` command, alias concept (demonstrated in comments)

---

## How to Run the Scripts on Linux

### Prerequisites
- A Linux system (Ubuntu recommended) — or WSL (Windows Subsystem for Linux) on Windows
- Bash shell (pre-installed on all Linux/WSL systems)
- Git installed: `sudo apt install git`

### Setup Instructions

**Step 1 — Clone the repository**
```bash
git clone https://github.com/[your-username]/oss-audit-[rollnumber].git
cd oss-audit-[rollnumber]/scripts
```

**Step 2 — Make all scripts executable**
```bash
chmod +x *.sh
```

**Step 3 — Run each script**

```bash
# Script 1 — No arguments required
./script1_system_identity.sh

# Script 2 — Pass a package name (defaults to 'git' if omitted)
./script2_foss_inspector.sh git

# Script 3 — No arguments required
./script3_disk_permission_auditor.sh

# Script 4 — Pass log file path and optional keyword (defaults to 'error')
./script4_log_analyzer.sh /var/log/kern.log error

# Script 5 — Interactive, no arguments required
./script5_manifesto_generator.sh
```

---

## Dependencies

All dependencies are standard on Ubuntu/Debian Linux systems.

| Dependency | Purpose | Install Command |
|-----------|---------|----------------|
| `bash` | Shell interpreter for all scripts | Pre-installed |
| `git` | Required for Script 2 package check | `sudo apt install git` |
| `dpkg` | Package manager query (Script 2) | Pre-installed on Ubuntu |
| `coreutils` | `du`, `df`, `ls`, `wc`, `cut`, `date` | Pre-installed |
| `grep` | Keyword matching (Script 4) | Pre-installed |
| `nano` | Text editor to create/edit scripts | `sudo apt install nano` |

No third-party libraries or external packages are required beyond standard Linux utilities.

---

## Notes

- All scripts were written and tested on **Ubuntu 24.04 LTS** via WSL2
- Scripts use `#!/bin/bash` shebang and are **not** compatible with plain `sh`
- Script 4 requires a readable log file — use `/var/log/kern.log` or create a test log
- Script 5 saves output to `manifesto_[username].txt` in the current directory

---

## References

- GNU Project — The Free Software Definition: https://gnu.org/philosophy/free-sw.html
- Git Official Documentation: https://git-scm.com/doc
- Pro Git Book (free): https://git-scm.com/book
- GPL v2 License Text: https://spdx.org/licenses/GPL-2.0-only.html
- The Linux Command Line (free): https://linuxcommand.org
