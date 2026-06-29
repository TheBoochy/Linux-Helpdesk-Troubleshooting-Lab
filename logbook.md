# Linux Helpdesk Troubleshooting Lab — Logbook

## 2026-06-29 — Part 1: Repository setup

### Goal

Start the Linux Helpdesk Troubleshooting Lab by creating the local project structure, initial documentation files and project folders.

### Work completed

* Created the local project folder.
* Created the main documentation folders:

  * docs
  * screenshots
  * scripts
  * results
* Created `README.md`.
* Created `logbook.md`.
* Created `.gitkeep` files so Git can track empty folders.
* Opened the project in VS Code.
* Saved screenshot evidence.

### Project structure

```text
Linux-Helpdesk-Troubleshooting-Lab/
├── docs/
│   └── .gitkeep
├── results/
│   └── .gitkeep
├── screenshots/
│   └── .gitkeep
├── scripts/
│   └── .gitkeep
├── logbook.md
└── README.md
```

### Commands used

```powershell
cd C:\Users\rband
mkdir Linux-Helpdesk-Troubleshooting-Lab
cd Linux-Helpdesk-Troubleshooting-Lab

mkdir docs
mkdir screenshots
mkdir scripts
mkdir results

New-Item README.md
New-Item logbook.md

New-Item docs\.gitkeep
New-Item screenshots\.gitkeep
New-Item scripts\.gitkeep
New-Item results\.gitkeep

code .
```

### Command purpose

| Command                                    | Purpose                                                |
| ------------------------------------------ | ------------------------------------------------------ |
| `cd C:\Users\rband`                        | Moves PowerShell to the user folder.                   |
| `mkdir Linux-Helpdesk-Troubleshooting-Lab` | Creates the main project folder.                       |
| `cd Linux-Helpdesk-Troubleshooting-Lab`    | Moves into the project folder.                         |
| `mkdir docs`                               | Creates the documentation folder.                      |
| `mkdir screenshots`                        | Creates the screenshot evidence folder.                |
| `mkdir scripts`                            | Creates the script storage folder.                     |
| `mkdir results`                            | Creates the command output and result storage folder.  |
| `New-Item README.md`                       | Creates the main README file.                          |
| `New-Item logbook.md`                      | Creates the project logbook file.                      |
| `New-Item .gitkeep`                        | Creates placeholder files so Git tracks empty folders. |
| `code .`                                   | Opens the current project folder in VS Code.           |

### Notes

This part creates the documentation base for the Linux Helpdesk Troubleshooting Lab.

The project will continue with a Linux baseline check before users, groups, permissions or troubleshooting scenarios are created.

Only safe lab data should be used in this project. No real secrets, credentials, private files or production data should be included.

### Evidence

Screenshot:

![screenshot-01-project-structure.png](screenshots/screenshot-01-project-structure.png)

---

## 2026-06-29 — Part 2: Linux baseline check

### Goal

Review the Linux system baseline before creating helpdesk troubleshooting scenarios.

### Work completed

* Reviewed hostname and system information.
* Verified the current logged-in user.
* Reviewed user ID and group membership information.
* Reviewed the Linux operating system version.
* Reviewed the kernel version.
* Reviewed current date and uptime.
* Reviewed disk usage.
* Reviewed memory and swap usage.
* Reviewed IP address and network interface information.
* Reviewed routing information.
* Checked SSH service status.
* Checked firewalld service status.
* Saved screenshot evidence.

### Verification results

| Item                | Result                          |
| ------------------- | ------------------------------- |
| System identity     | Reviewed with `hostnamectl`     |
| Current user        | Reviewed with `whoami`          |
| User and groups     | Reviewed with `id`              |
| OS version          | Reviewed with `/etc/os-release` |
| Kernel version      | Reviewed with `uname -r`        |
| Date and uptime     | Reviewed                        |
| Disk usage          | Reviewed with `df -h`           |
| Memory usage        | Reviewed with `free -h`         |
| Network interfaces  | Reviewed with `ip addr`         |
| Routing information | Reviewed with `ip route`        |
| SSH service         | Reviewed with `systemctl`       |
| Firewall service    | Reviewed with `systemctl`       |

### Commands used

```bash
hostnamectl
whoami
id
cat /etc/os-release
uname -r
date
uptime

df -h
free -h

ip addr
ip route

systemctl status sshd --no-pager
systemctl status firewalld --no-pager
```

### Command purpose

| Command                                 | Purpose                                                    |
| --------------------------------------- | ---------------------------------------------------------- |
| `hostnamectl`                           | Shows hostname, operating system, kernel and architecture. |
| `whoami`                                | Shows the current logged-in user.                          |
| `id`                                    | Shows user ID, group ID and group memberships.             |
| `cat /etc/os-release`                   | Shows the Linux distribution and version.                  |
| `uname -r`                              | Shows the running kernel version.                          |
| `date`                                  | Shows the current system date and time.                    |
| `uptime`                                | Shows how long the system has been running.                |
| `df -h`                                 | Shows disk usage in human-readable format.                 |
| `free -h`                               | Shows memory and swap usage in human-readable format.      |
| `ip addr`                               | Shows network interfaces and IP addresses.                 |
| `ip route`                              | Shows routing information and the default route.           |
| `systemctl status sshd --no-pager`      | Checks whether the SSH service is running.                 |
| `systemctl status firewalld --no-pager` | Checks whether the firewall service is running.            |

### Notes

This baseline check gives the project a clear starting point before helpdesk troubleshooting tasks are created.

The commands used in this part are common beginner Linux support commands and are useful for helpdesk, junior sysadmin and troubleshooting work.

### Evidence

Screenshots:

![screenshot-02a-linux-baseline-system-info.png](screenshots/screenshot-02a-linux-baseline-system-info.png)

![screenshot-02b-linux-baseline-resources.png](screenshots/screenshot-02b-linux-baseline-resources.png)

![screenshot-02c-linux-baseline-network.png](screenshots/screenshot-02c-linux-baseline-network.png)

![screenshot-02d-linux-baseline-services.png](screenshots/screenshot-02d-linux-baseline-services.png)
