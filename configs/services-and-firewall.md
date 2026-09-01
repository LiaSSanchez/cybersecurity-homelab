# Services and Firewall Configuration

## Services

The target machine was configured with two primary network services:

- SSH on TCP port 22
- Apache HTTP on TCP port 80

SSH was used for remote administration and connectivity testing between the virtual machines.

Apache was used to host a simple custom webpage for HTTP testing, service enumeration, and log analysis.

## Apache

Apache2 was installed and configured on `CyberLab-Target`.

The default webpage was replaced with a simple custom page to verify that the web server was serving content correctly.

The web service was tested from `CyberLab-Ubuntu` using `curl`.

## SSH

OpenSSH was enabled on the target machine to allow secure remote access from the analyst machine.

Nmap service detection confirmed that SSH was reachable on TCP port 22.

## UFW Firewall

UFW was enabled on the target machine to control inbound network access.

The following services were allowed:

```bash
sudo ufw allow 22/tcp
sudo ufw allow 80/tcp
```

Firewall status was reviewed using:

```bash
sudo ufw status numbered
```

HTTP access was temporarily blocked during firewall testing to observe how the change affected Nmap results and connectivity.

After testing, HTTP access was restored.

## Security Takeaway

This configuration demonstrated that a service can be installed and running locally while still being inaccessible from another machine if network firewall rules block the traffic.

Firewall configuration is therefore an important part of reducing unnecessary network exposure.
