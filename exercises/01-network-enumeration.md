# Network Enumeration

## Objective

Identify active services running on the target machine and determine their versions using Nmap.

## Lab Environment

- Analyst machine: `CyberLab-Ubuntu`
- Target machine: `CyberLab-Target`
- Target IP: `10.10.10.20`

## Command Used

```bash
nmap -Pn -sV 10.10.10.20
