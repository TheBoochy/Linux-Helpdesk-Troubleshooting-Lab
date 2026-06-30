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
| Part 4  | Create shared support folders   | Complete |
| Part 5  | Fix permission problem          | Complete |
| Part 6  | Troubleshoot stopped service    | Complete |
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
│   ├── screenshot-03a-linux-users-and-groups-created-and-verified.png
│   ├── screenshot-04a-linux-shared-folders-created.png
│   ├── screenshot-04b-linux-shared-folder-access-test.png
│   ├── screenshot-05a-linux-permission-problem-created.png
│   ├── screenshot-05b-linux-permission-problem-fixed.png
│   ├── screenshot-06a-linux-service-stopped.png
│   └── screenshot-06b-linux-service-started-and-logs.png
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

Shared folders were created under `/shared` for the `support` and `staff` groups. Folder ownership and permissions were configured so that members of the correct group can access their shared folder, while users outside the group are denied access.

A permission problem was created on `/shared/support/support-notes.txt` by changing the file permission to `600`. This blocked `alice` from reading a file she should normally access through the `support` group. The issue was investigated by checking user group membership, folder permissions and file permissions. The file permission was then restored to `660`, allowing `alice` to read the file again while keeping `bob` denied.

A stopped service troubleshooting scenario was completed using `firewalld`. The service was stopped, its inactive state was confirmed with `systemctl`, the service was started again, and the running state was verified. Recent service logs were reviewed with `journalctl`.

The next step is to review simple system logs.

---

## Skills demonstrated

This project will demonstrate:

* Basic Linux administration
* Helpdesk-style troubleshooting
* Linux navigation and command usage
* User and group review
* Linux user creation
* Linux group creation
* Linux folder creation
* Linux ownership management with `chown`
* Linux permission management with `chmod`
* Group-based access control
* Basic permission troubleshooting
* Service troubleshooting with `systemctl`
* Basic service log review with `journalctl`
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
| `screenshot-04a-linux-shared-folders-created.png`                | Shared folder ownership and permission setup    |
| `screenshot-04b-linux-shared-folder-access-test.png`             | Shared folder access and blocked access test    |
| `screenshot-05a-linux-permission-problem-created.png`            | Permission problem created and verified         |
| `screenshot-05b-linux-permission-problem-fixed.png`              | Permission problem investigated and fixed       |
| `screenshot-06a-linux-service-stopped.png`                       | Stopped service problem verified                |
| `screenshot-06b-linux-service-started-and-logs.png`              | Service restored and logs reviewed              |

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

## Part 4 — Create shared support folders

Status: Complete

This part created shared folders for the `support` and `staff` groups and verified that group-based access worked correctly.

The shared folders created were:

```text
/shared/support
/shared/staff
```

The folder ownership was configured as:

```text
/shared/support  -> root:support
/shared/staff    -> root:staff
```

Commands used:

```bash
sudo mkdir -p /shared/support
sudo mkdir -p /shared/staff

sudo chown root:support /shared/support
sudo chown root:staff /shared/staff

sudo chmod 770 /shared/support
sudo chmod 770 /shared/staff

echo "Support team shared folder" | sudo tee /shared/support/support-notes.txt
echo "Staff shared folder" | sudo tee /shared/staff/staff-notes.txt

sudo chown root:support /shared/support/support-notes.txt
sudo chown root:staff /shared/staff/staff-notes.txt

sudo chmod 660 /shared/support/support-notes.txt
sudo chmod 660 /shared/staff/staff-notes.txt

ls -ld /shared
ls -ld /shared/support
ls -ld /shared/staff

sudo ls -l /shared/support
sudo ls -l /shared/staff

sudo -u alice ls -l /shared/support
sudo -u alice cat /shared/support/support-notes.txt

sudo -u bob ls -l /shared/staff
sudo -u bob cat /shared/staff/staff-notes.txt

sudo -u alice ls -l /shared/staff
sudo -u bob ls -l /shared/support
```

Results:

* Created `/shared/support`.
* Created `/shared/staff`.
* Set `/shared/support` group ownership to `support`.
* Set `/shared/staff` group ownership to `staff`.
* Set folder permissions to `770`.
* Created a support test file.
* Created a staff test file.
* Set file permissions to `660`.
* Verified folder ownership and permissions.
* Verified that `alice` could access `/shared/support`.
* Verified that `bob` could access `/shared/staff`.
* Verified that `alice` was denied access to `/shared/staff`.
* Verified that `bob` was denied access to `/shared/support`.

Notes:

This part demonstrates basic Linux group-based folder access.

The folder permission `770` allows the owner and group to read, write and enter the folder, while blocking all other users.

The file permission `660` allows the owner and group to read and write the files, while blocking all other users.

Screenshot links:

[screenshot-04a-linux-shared-folders-created.png](screenshots/screenshot-04a-linux-shared-folders-created.png)

[screenshot-04b-linux-shared-folder-access-test.png](screenshots/screenshot-04b-linux-shared-folder-access-test.png)

---

## Part 5 — Fix permission problem

Status: Complete

This part created a basic Linux permission problem, investigated the cause and fixed it.

The affected file was:

```text
/shared/support/support-notes.txt
```

The problem was created by changing the file permission to:

```text
600
```

This removed group access from the file and prevented `alice`, a member of the `support` group, from reading it.

Commands used:

```bash
sudo chmod 600 /shared/support/support-notes.txt
sudo ls -l /shared/support/support-notes.txt

sudo -u alice cat /shared/support/support-notes.txt

id alice
getent group support
ls -ld /shared/support
sudo ls -l /shared/support/support-notes.txt

sudo chmod 660 /shared/support/support-notes.txt
sudo ls -l /shared/support/support-notes.txt

sudo -u alice cat /shared/support/support-notes.txt
sudo -u bob cat /shared/support/support-notes.txt
```

Results:

* Changed `/shared/support/support-notes.txt` to permission `600`.
* Verified that `alice` could not read the support file.
* Checked Alice’s user and group information.
* Verified that Alice belonged to the `support` group.
* Verified the `/shared/support` folder ownership and permissions.
* Verified that the file permission was the cause of the issue.
* Restored the file permission to `660`.
* Verified that `alice` could read the file again.
* Verified that `bob` was still denied access to the support file.

Notes:

This part demonstrates a common beginner Linux troubleshooting workflow.

The issue was caused by file permissions, not by Alice’s user account or group membership.

The permission `600` allowed only the file owner to read and write the file.

The permission `660` restored read and write access for the file owner and group while keeping other users blocked.

Screenshot links:

[screenshot-05a-linux-permission-problem-created.png](screenshots/screenshot-05a-linux-permission-problem-created.png)

[screenshot-05b-linux-permission-problem-fixed.png](screenshots/screenshot-05b-linux-permission-problem-fixed.png)

---

## Part 6 — Troubleshoot stopped service

Status: Complete

This part created a basic stopped-service troubleshooting scenario and restored the service.

The service used was:

```text
firewalld
```

Commands used:

```bash
systemctl status firewalld --no-pager

sudo systemctl stop firewalld
systemctl status firewalld --no-pager

sudo systemctl start firewalld
systemctl status firewalld --no-pager

journalctl -u firewalld -n 20 --no-pager
```

Results:

* Checked the initial `firewalld` service status.
* Stopped the `firewalld` service.
* Verified that the service was inactive.
* Started the `firewalld` service again.
* Verified that the service was active and running.
* Reviewed recent `firewalld` service logs with `journalctl`.

Notes:

This part demonstrates basic Linux service troubleshooting.

The `systemctl status` command was used to check whether the service was running or stopped.

The `systemctl stop` command was used to create the stopped-service problem.

The `systemctl start` command was used to restore the service.

The `journalctl` command was used to review recent service logs.

`firewalld` was used instead of `sshd` because stopping `sshd` can break the active SSH connection used by VS Code.

Screenshot links:

[screenshot-06a-linux-service-stopped.png](screenshots/screenshot-06a-linux-service-stopped.png)

[screenshot-06b-linux-service-started-and-logs.png](screenshots/screenshot-06b-linux-service-started-and-logs.png)

---

## Notes

This is a lab environment and not a production system.

The project is created for learning, documentation and portfolio demonstration.

Only safe test data should be used in this lab.

No real personal data, passwords, SSH keys, tokens, production configuration files or sensitive business files should be included in screenshots or public documentation.
