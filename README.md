# Tracing and Managing Server IP for BGMI on Android Using Termux

This README provides detailed instructions on how to trace and manage the server IP for BGMI (Battlegrounds Mobile India) using Termux on an Android device. These steps include tracing the server IP, identifying the server IP during gameplay, and optionally blocking the server IP. It's important to note that these actions should only be used for educational purposes and not for disrupting gameplay or engaging in unethical behavior.

## Getting Started

Ensure you have Termux installed on your Android device before proceeding with the following steps. Termux can be downloaded from the Google Play Store.

## Installation of Necessary Tools

### Install traceroute

To install traceroute, which is used for tracing the path packets take to a network host, use the following command in Termux:

```bash
pkg install traceroute
```

### Install net-tools

Net-tools includes the netstat command, which is useful for displaying network connections, routing tables, and a number of network interface statistics:

```bash
pkg install net-tools
```

### Install iptables

Iptables is a powerful firewall tool used to manage network traffic rules:

```bash
pkg install iptables
```

## Tracing and Blocking Server IP

### Trace the Server IP

To trace the path to the BGMI server IP:

```bash
traceroute <server IP>
```

Replace `<server IP>` with the actual IP address of the BGMI game server you wish to trace.

### Get the Server IP

To find the server IP during gameplay, you can view all established TCP connections:

```bash
netstat -n | grep tcp | grep ESTABLISHED
```

This command filters the list of established TCP connections to find the one related to BGMI. Note down the server IP from this output.

### Block the Server IP

To block the server IP, which prevents incoming connections from that IP address (note this is generally not recommended unless for specific testing purposes):

```bash
iptables -A INPUT -s <server IP> -j DROP
```

Replace `<server IP>` with the IP address you want to block.

## Disclaimer

All commands and techniques described here are for educational purposes only. Misusing these commands to disrupt game servers or for any other malicious activities is illegal and unethical. Users should comply with all applicable laws and respect the terms of service of the game.

## Summary of Commands

Here's a quick reference to all the commands mentioned above for easy access:

```bash
# Install traceroute
pkg install traceroute

# Trace the server IP
traceroute <server IP>

# Install net-tools
pkg install net-tools

# Get the server IP
netstat -n | grep tcp | grep ESTABLISHED

# Install iptables
pkg install iptables

# Block the server IP
iptables -A INPUT -s <server IP> -j DROP
```

By following these instructions, users can understand the network interactions of BGMI and use this knowledge responsibly to enhance their understanding of network communications and security measures.
```

This README is structured to guide users step-by-step through the process of installing necessary tools in Termux, tracing the server IP, and managing server IPs through iptables. It emphasizes the importance of ethical use and compliance with legal standards.
