# Autonomous Network Security & Reconnaissance Toolkit

A production-ready repository containing lightweight, low-level Python automation utilities designed to execute passive network reconnaissance and socket service verification.

## 1. TCP Multi-Port Auditing Utility (`network_recon_scanner.ipynb`)

### Technical Overview
This utility is a multi-port command-line diagnostic tool engineered to probe localized and public-facing network endpoints. It maps open entry points, diagnoses server availability, and parses domain entries back to basic IPv4 targets.

### Architectural Core Concepts & Implementation
- **Low-Level Socket Programming:** Leverages the native Python `socket` API to establish raw structural requests over the internet layer via IPv4 address boundaries (`AF_INET`) using the TCP transport protocol layer (`SOCK_STREAM`).
- **Non-Blocking Execution Strategy:** Utilizes the socket API's `connect_ex()` protocol. Instead of raising complex system-blocking runtime exceptions upon interacting with dropped packets or closed firewalls, the methodology intercepts the underlying kernel status code (`0` for clean handshakes).
- **Latency Optimization Filters:** Configures strict socket timeout limits (`settimeout(2.0)`) across individual probes to prevent the parent environment runtime from locking permanently on unresponsive, firewalled, or heavily rate-limited host machines.
- **Dynamic Sanitization Filters:** Employs runtime string processing engine blocks to scrub web architecture indicators (e.g., protocol prefixes like `https://` or deep subfolder trailing slashes) to enforce endpoint hostname stability during DNS resolution phases.

### Executing the Architecture
1. **Target Point Parsing:** Resolves alphanumeric domain inputs to dedicated IPv4 destinations via local network configuration parameters (`socket.gethostbyname`).
2. **Array Traversal Audits:** Evaluates an initialized index array containing critical enterprise operational connection points (Secure Shell SSH, Simple Mail Protocol SMTP, Hypertext HTTP, Encrypted Web HTTPS, and Remote Desktop RDP).
3. **State Evaluation Logging:** Parses connection criteria directly to command-line dashboards for immediate logging analysis.
