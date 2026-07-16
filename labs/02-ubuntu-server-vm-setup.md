# Lab 02 — Ubuntu Server Virtual Machine Setup

## Objective

The objective was to create and run successfully an isolated Ubuntu Server environment for safe administration and troubleshooting practice.

## Host Virtualization Checks

- Host CPU supports `AMD-V`
- KVM modules `kvm` and `kvm_amd` were loaded
- GNOME Boxes was used to create the VM

## Virtual Machine Configuration

- Ubuntu Server 26.04 LTS
- UEFI firmware
- 4 GiB memory
- 30 GiB virtual storage
- Normal Ubuntu Server installation
- DHCP networking
- OpenSSH Server installed
- System updated using `sudo apt update` and `sudo apt upgrade`

## Installation Choices

Ubuntu Server was selected instead of Ubuntu Desktop because the lab is intended for command-line server administration and troubleshooting. The server edition also requires fewer system resources and more closely resembles a typical cloud server.

UEFI was used as the modern firmware option. The VM was allocated 4 GBs of memory and 30 GBs of virtual storage, providing enough capacity for updates, services, logs, and future labs without allocating excessive host resources.

DHCP was used for the initial network configuration so that the VM could obtain an IP address and internet access automatically. A static address can be configured in a later networking lab.

OpenSSH Server was installed to support remote administration. Optional server snaps were skipped so that additional software can be installed deliberately during later labs.

## Verification

- `hostnamectl` — confirmed the hostname, operating system, kernel, architecture, and KVM virtualization.
- `ip -br address` — confirmed that the network interface was active and had received an IP address.
- `systemctl status ssh --no-pager` — confirmed that the SSH service was active and listening.

## What I Learned

I learned that AMD-V is the hardware virtualization feature provided by the CPU, while KVM is the Linux virtualization technology that uses this feature to run virtual machines. The Ubuntu Server VM provides a separate guest environment where I can practise administration and troubleshooting without making changes directly to my Bazzite host. 

DHCP automatically supplied the VM with an IP address and network configuration, and I used systemctl to confirm that the SSH service was active. I also discovered that the Ubuntu text console does not support normal clipboard pasting and that the VM’s default user-mode networking did not allow a direct SSH connection from the host without additional configuration.

I also learned why Ubuntu Server is more suitable than a desktop installation for this lab, as it uses fewer resources and focuses on command-line administration. The verification stage showed me that completing an installation is not enough on its own; the hostname, network connection, and required services should be checked to confirm that the server is functioning as intended.
