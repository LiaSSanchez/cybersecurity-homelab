# Network Configuration

## Internal Lab Network

The cybersecurity homelab uses an isolated Hyper-V internal virtual switch for communication between the two Ubuntu virtual machines.

### Static IP Addresses

| Machine | IP Address |
|---|---|
| CyberLab-Ubuntu | 10.10.10.10/24 |
| CyberLab-Target | 10.10.10.20/24 |

The internal network allows the analyst machine to communicate directly with the target machine without exposing the lab services to the external network.

## Internet Connectivity

A second Hyper-V network adapter was added when internet access was needed for package installation and updates.

The internet-facing adapter uses DHCP, while the isolated lab adapter uses static addressing.

## Netplan

Ubuntu networking was configured using Netplan.

Static addressing was used for the internal lab interfaces so the IP addresses remain consistent between reboots.

This makes it easier to perform repeatable scanning, SSH connections, web testing, and other security exercises.
