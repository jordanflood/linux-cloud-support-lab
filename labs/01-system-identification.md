# Lab 01 — Linux System Identification

## Objective

* The objective is to identify an unfamiliar Linux system and confirm the current user’s access and permissions before beginning troubleshooting or support work.

## Environment

- Distribution: Bazzite 44
- Variant: Kinoite
- Base distribution: Fedora 44
- Release type: Stable
- Kernel: 7.1.3-ogc3.4.fc44.x86_64
- Architecture: x86_64
- Username: huzbando
- Hostname: huzbando

## Commands Used

- `cat /etc/os-release`
- `uname -r`
- `whoami`
- `hostname`
- `sudo -l`
- `id`
- `groups`
- `getent passwd huzbando`
- `getent group wheel`

## Findings

Bazzite is based on Fedora.
The system uses the x86_64 architecture.
Username and hostname are both huzbando, but they represent different things.
UID and primary GID are 1000.
Account belongs to the wheel group.
sudo -l confirms that the account can run administrative commands.

## What I Learned

I learned that identifying the environment is a crucial first step before diving into troubleshooting to understand what we are working with. Username and Hostname, while the same in this case, are representative of the current user (Username) and the System used (Hostname). I also learned what wheel and sudo do in relation to administrative actions. Membership in the wheel group gives my account permission to use sudo, while sudo runs individual commands with elevated administrative privileges.
