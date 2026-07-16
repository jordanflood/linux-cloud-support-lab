# Lab 03 — Nginx Installation and Verification

## Objective

The goal was to install a web service and verify the entire chain: service state, listening port, HTTP response, logs, and configuration.

## Environment

- Ubuntu Server 26.04 LTS
- Hostname: `ubuntu-support-lab`
- Nginx installed through `apt`

## Installation

- `sudo apt update`
- `sudo apt install nginx`

`apt update` refreshed the available package information, while `apt install nginx` installed Nginx and its required dependencies.

## Service Verification

- `systemctl status nginx --no-pager`

Nginx was:

- loaded by systemd;
- enabled to start at boot;
- `active (running)`.

## Listening Ports

- `sudo ss -ltnp | grep nginx`

Nginx showed it was listening on TCP port 80 through both:

- `0.0.0.0:80` — all IPv4 interfaces
- `[::]:80` — all IPv6 interfaces

## HTTP Testing

- `curl http://localhost`
- `curl -I http://localhost`

`localhost` referred to the Ubuntu VM itself. The first command returned the default Nginx HTML page, while the second returned only the response headers and showed `HTTP/1.1 200 OK`.

## Log Inspection

- `sudo journalctl -u nginx --since "15 minutes ago" --no-pager`
- `sudo tail -n 10 /var/log/nginx/access.log`
- `sudo tail -n 10 /var/log/nginx/error.log`

- `journalctl` showed the Nginx service startup events.
- `access.log` recorded the `GET` and `HEAD` requests made by `curl`.
- `error.log` contained an informational notice but no actual errors.

## Configuration Validation

- `sudo nginx -t`

The test confirmed that the Nginx configuration syntax was valid and that the configuration files could be read successfully.

## Findings

- Nginx installed successfully.
- The service was running and enabled.
- It was listening on TCP port 80.
- It returned a successful HTTP response.
- Requests appeared in the access log.
- The configuration passed validation.
- No genuine errors were present.

## What I Learned

- “Listening” means Nginx is waiting for network connections on port 80.

- A running process does not necessarily prove that a web service is reachable or responding correctly.

- `systemctl`, `ss`, `curl`, and the logs each verified a different layer. `nginx -t` should be used before applying configuration changes. Command flags are specific to each command: `ss -n` means numeric output, while `tail -n 10` means the last ten lines.

- nginx -t should be used before applying configuration changes.

- Command flags are specific to the command: ss -n means numeric output, while tail -n 10 means the last ten lines.