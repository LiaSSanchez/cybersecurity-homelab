# HTTP Service Analysis

## Objective

Inspect the HTTP service running on the target machine and review information exposed through HTTP responses.

## Lab Environment

- Analyst machine: `CyberLab-Ubuntu`
- Target machine: `CyberLab-Target`
- Target IP: `10.10.10.20`
- Web service: Apache2

## Commands Used

```bash
curl http://10.10.10.20
curl -I http://10.10.10.20
```

## Results

The first command successfully retrieved the custom webpage hosted on the target machine.

The second command displayed the HTTP response headers returned by the Apache web server.

The response included information such as:

- HTTP status code
- Web server software
- Apache version
- Content type
- Content length

## What I Learned

This exercise demonstrated how HTTP responses can expose useful information about a web server.

Response headers can reveal technologies and software versions running on a system. During security assessments, this information can help identify the services in use and determine whether additional investigation is needed.

Using `curl` also provided a simple way to test connectivity and interact with the web service directly from the command line.
