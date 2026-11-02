# Network Security Tools

A collection of lightweight, cloud-capable Python utilities developed to demonstrate foundational concepts in networking protocols, socket management, and defensive security.

## 1. TCP Port Scanner (`port_scanner.ipynb`)
This script functions as a localized network reconnaissance utility. It maps active network services on a specified target host by systematically initiating TCP socket connections.

### Key Features & Architecture
- **Socket Programming:** Leverages Python’s native `socket` library to manage low-level network connections over IPv4 (`AF_INET`) and TCP (`SOCK_STREAM`).
- **Performance Tuning:** Implements a strict `settimeout(2.0)` condition on each probe. This prevents the cloud container from hanging indefinitely on heavily filtered or dead ports.
- **Graceful Error Handling:** Employs `try-except` blocks to handle network connectivity disruptions and unresolvable hostnames (`socket.gaierror`) dynamically.
- **Non-Disruptive Auditing:** Utilizes the `connect_ex()` method, which returns an integer error indicator rather than raising an execution exception, keeping network sweeps clean and lightweight.

### How It Works
1. Resolves a target domain name (e.g., `scanme.nmap.org`) into an IP address.
2. Loops through a target array of common service ports (22 for SSH, 80 for HTTP, 443 for HTTPS).
3. Evaluates if the port responds to a TCP handshake (`0` indicates an open state).
