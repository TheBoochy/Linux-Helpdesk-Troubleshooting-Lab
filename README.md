# Linux Helpdesk Troubleshooting Lab

## Overview

Linux Helpdesk Troubleshooting Lab is a beginner-friendly sysadmin portfolio project focused on basic Linux support and troubleshooting tasks.

The lab is designed to practice Linux system checks, user and group review, permissions, services, logs, resource checks and simple documentation.

Public documentation uses the name **Vulkan**.

---

## Scenario

A small organization uses a Linux server for internal support practice.

The goal of this lab is to act as a junior helpdesk or junior system administrator and investigate common Linux support tasks in a structured way.

The lab focuses on safe beginner-level troubleshooting in a controlled environment. It uses test data only and does not include real personal data, passwords, secrets or production files.

---

## Lab goals

The goals of this lab are to:

* Create a clean Linux helpdesk troubleshooting project.
* Verify the Linux system baseline.
* Review current user and group information.
* Check disk and memory usage.
* Review network information.
* Check basic service status.
* Create test users and groups.
* Create shared support folders.
* Fix basic permission problems.
* Troubleshoot a stopped service.
* Review simple logs.
* Document findings with screenshots.
* Track work through Git and GitHub.

---

## Planned parts

| Part    | Topic                           | Status   |
| ------- | ------------------------------- | -------- |
| Part 1  | Repository setup                | Complete |
| Part 2  | Linux baseline check            | Complete |
| Part 3  | Create test users and groups    | Complete |
| Part 4  | Create shared support folders   | Planned  |
| Part 5  | Fix permission problem          | Planned  |
| Part 6  | Troubleshoot stopped service    | Planned  |
| Part 7  | Review logs                     | Planned  |
| Part 8  | Check disk and system resources | Planned  |
| Part 9  | Create troubleshooting report   | Planned  |
| Part 10 | Final README and GitHub polish  | Planned  |

---

## Project structure

```text
Linux-Helpdesk-Troubleshooting-Lab/
├── docs/
│   └── .gitkeep
├── results/
│   └── .gitkeep
├── screenshots/
│   ├── .gitkeep
│   ├── screenshot-01-project-structure.png
│   ├── screenshot-02a-linux-baseline-system-info.png
│   ├── screenshot-02b-linux-baseline-resources.png
│   ├── screenshot-02c-linux-baseline-network.png
│   ├── screenshot-02d-linux-baseline-services.png
│   └── screenshot-03a-linux-users-and-groups-created-and-verified.png
├── scripts/
│   └── .gitkeep
├── logbook.md
└── README.md
```

---

## Current progress

The project structure has been created.

The Linux system baseline has been reviewed, including hostname, current user, user ID, group memberships, operating system version, kernel version, date and uptime.

System resources were reviewed with disk usage and memory usage commands.

Network information was reviewed, including IP address information and routing information.

Basic service status was reviewed for SSH and firewalld.

Test users and groups were created for future helpdesk troubleshooting tasks. The lab users `alice` and `bob` were created with home directories. The `support` and `staff` groups were also created, and group membership was verified with `id` and `getent`.

The next step is to create shared support folders for permission testing.

---

## Skills demonstrated

This project will demonstrate:

* Basic Linux administration
* Helpdesk-style troubleshooting
* Linux navigation and command usage
* User and group review
* Linux user creation
* Linux group creation
* Disk and memory checks
* Network information review
* Service status checks with `systemctl`
* Screenshot-based evidence collection
* Markdown documentation
* Git and GitHub workflow

---

## Documentation and evidence

Main documentation files:

| File         | Purpose                      |
| ------------ | ---------------------------- |
| `README.md`  | Main GitHub project overview |
| `logbook.md` | Step-by-step project notes   |

Screenshot evidence is stored in the `screenshots/` folder.

Current screenshot evidence:

| Screenshot                                                       | Purpose                                         |
| ---------------------------------------------------------------- | ----------------------------------------------- |
| `screenshot-01-project-structure.png`                            | Initial project structure                       |
| `screenshot-02a-linux-baseline-system-info.png`                  | Linux system identity and user info             |
| `screenshot-02b-linux-baseline-resources.png`                    | Disk and memory usage review                    |
| `screenshot-02c-linux-baseline-network.png`                      | Network interface and route review              |
| `screenshot-02d-linux-baseline-services.png`                     | SSH and firewall service review                 |
| `screenshot-03a-linux-users-and-groups-created-and-verified.png` | Test users and groups creation and verification |

Command results and verification output may be stored in:

```text
results/
```

Scripts may be stored in:

```text
scripts/
```

---

## Part 2 — Linux baseline check

Status: Complete

This part reviewed the Linux system baseline before creating test users, groups, folders or troubleshooting scenarios.

Commands used:

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

Results:

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

Notes:

This baseline check gives the project a clear starting point before troubleshooting tasks are created.

The commands used in this part are common beginner Linux support commands and are useful for helpdesk, junior sysadmin and troubleshooting work.

Screenshot links:

[screenshot-02a-linux-baseline-system-info.png](screenshots/screenshot-02a-linux-baseline-system-info.png)

[screenshot-02b-linux-baseline-resources.png](screenshots/screenshot-02b-linux-baseline-resources.png)

[screenshot-02c-linux-baseline-network.png](screenshots/screenshot-02c-linux-baseline-network.png)

[screenshot-02d-linux-baseline-services.png](screenshots/screenshot-02d-linux-baseline-services.png)

---

## Part 3 — Create test users and groups

Status: Complete

This part created safe lab users and groups for future helpdesk troubleshooting and permissions testing.

The groups created were:

```text
support
staff
```

The test users created were:

```text
alice
bob
```

Commands used:

```bash
sudo groupadd support
sudo groupadd staff

sudo useradd -m -G support alice
sudo useradd -m -G staff bob

sudo passwd alice
sudo passwd bob

id alice
id bob

getent passwd alice
getent passwd bob

getent group support
getent group staff

ls -ld /home/alice
ls -ld /home/bob
```

Results:

* Created the `support` group.
* Created the `staff` group.
* Created the `alice` test user.
* Created the `bob` test user.
* Created home folders for both test users.
* Added `alice` to the `support` group.
* Added `bob` to the `staff` group.
* Verified both users with `id`.
* Verified both user database entries with `getent passwd`.
* Verified both groups with `getent group`.
* Verified both user home folders with `ls -ld`.

Notes:

The users and groups are safe lab accounts created only for troubleshooting practice.

These accounts will be used later to test folder access, group permissions and basic helpdesk troubleshooting scenarios.

Screenshot link:

[screenshot-03a-linux-users-and-groups-created-and-verified.png](screenshots/screenshot-03a-linux-users-and-groups-created-and-verified.png)

---

## Notes

This is a lab environment and not a production system.

The project is created for learning, documentation and portfolio demonstration.

Only safe test data should be used in this lab.

No real personal data, passwords, SSH keys, tokens, production configuration files or sensitive business files should be included in screenshots or public documentation.
