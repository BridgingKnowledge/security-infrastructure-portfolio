# System Analysis – Exposed Telnet Service 

## Overview
During analysis of a target system, network scanning identified an open Telnet service (port 23/tcp).

## Discovery Process
The system was first tested for connectivity using ICMP (ping).  
Subsequently, Nmap was used to enumerate open ports and services:

- Port 23/tcp was identified as open
- Service: Telnet (legacy remote access protocol)

## Finding
The Telnet service allowed login as the root user without requiring a password.

## Risk
This represents a critical security misconfiguration:

- Unauthorized users can gain full system access
- No authentication barrier is present
- The system is fully exposed to anyone with network access

## Root Cause
- Use of insecure legacy protocol (Telnet)
- Missing authentication controls for privileged account
- Lack of access restrictions (no firewall or segmentation)

## Impact
- Full command execution as root
- Access to all files and system resources
- Potential data exposure or system manipulation

## Mitigation
- Disable Telnet service
- Replace with secure protocol (SSH)
- Enforce strong authentication
- Restrict access via firewall or network segmentation
