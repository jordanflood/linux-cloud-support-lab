# Linux Cloud Support Lab

A growing collection of hands-on Linux administration, troubleshooting, networking, and cloud-support labs.

This repository documents practical work completed in a local virtualised environment. Each lab includes the objective, commands used, verification steps, findings, and lessons learned.

## Labs

| Lab | Topic | Skills Demonstrated |
| --- | --- | --- |
| [Lab 01 — System Identification](labs/01-system-identification.md) | Identifying the operating system, kernel, user, hostname, groups, and administrative permissions | Linux CLI, users and groups, permissions, system identification |
| [Lab 02 — Ubuntu Server VM Setup](labs/02-ubuntu-server-vm-setup.md) | Creating and verifying an Ubuntu Server virtual machine | Virtualisation, KVM, Ubuntu Server installation, networking, SSH service verification |
| [Lab 03 — Nginx Installation and Verification](labs/03-nginx-installation-and-verification.md) | Installing Nginx and verifying the service from process to HTTP response | APT, systemd, TCP ports, HTTP testing, log inspection, configuration validation |

## Skills Demonstrated

- Linux command-line administration
- Operating system and hardware identification
- User, group, and sudo permission inspection
- Package installation with APT
- Service management with `systemctl`
- Network socket and listening-port inspection with `ss`
- HTTP testing with `curl`
- Log inspection with `journalctl` and `tail`
- Nginx configuration validation
- Virtual machine deployment with GNOME Boxes and KVM
- Technical documentation using Markdown
- Git and GitHub version control

## Lab Environment

- **Host operating system:** Bazzite
- **Virtualisation:** GNOME Boxes with KVM
- **Guest operating system:** Ubuntu Server 26.04 LTS
- **Web server:** Nginx
- **Version control:** Git and GitHub

## Repository Structure

```text
linux-cloud-support-lab/
├── labs/
│   ├── 01-system-identification.md
│   ├── 02-ubuntu-server-vm-setup.md
│   └── 03-nginx-installation-and-verification.md
├── commands.md
└── README.md
