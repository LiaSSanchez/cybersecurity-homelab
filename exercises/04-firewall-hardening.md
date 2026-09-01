# Firewall Hardening and Testing

## Objective

Configure firewall rules on the target machine and test how those rules affect the services visible from the analyst machine.

## Lab Environment

- Analyst machine: `CyberLab-Ubuntu`
- Target machine: `CyberLab-Target`
- Target IP: `10.10.10.20`
- Firewall: UFW
- SSH port: `22`
- HTTP port: `80`

## Commands Used

```bash
sudo ufw allow 22/tcp
sudo ufw allow 80/tcp
sudo ufw enable
sudo ufw status numbered
```

To test the effect of blocking HTTP:

```bash
sudo ufw deny 80/tcp
```

From the analyst machine:

```bash
nmap -Pn -sV 10.10.10.20
```

After testing, HTTP access was restored:

```bash
sudo ufw delete deny 80/tcp
sudo ufw allow 80/tcp
```

## Results

Before blocking HTTP, Nmap identified both SSH on port 22 and Apache HTTP on port 80 as open services.

After the firewall rule was changed, SSH remained accessible while HTTP was no longer shown as an open service.

The scan reported filtered ports with no response, demonstrating that the firewall was preventing traffic from reaching the HTTP service.

After restoring the HTTP rule, the web server became reachable again.

## What I Learned

This exercise demonstrated how firewall rules can directly change a system's exposed attack surface.

I learned how UFW can be used to allow or block specific TCP ports and how those changes appear from another machine during network scanning.

I also learned the difference between a service being installed and running on a system versus that service actually being reachable over the network.
