# Autonomous Network Security & Reconnaissance Toolkit

A production-ready repository containing lightweight, low-level Python automation utilities designed to execute passive network reconnaissance, socket service verification, and localized intrusion triage parsing.

---

## 1. TCP Multi-Port Auditing Utility (`network_recon_scanner.ipynb`)

### Technical Overview
This utility is a multi-port command-line diagnostic tool engineered to probe localized and public-facing network endpoints. It maps open entry points, diagnoses server availability, and parses domain entries back to basic IPv4 targets.

### Architectural Core Concepts & Implementation
- **Low-Level Socket Programming:** Leverages the native Python `socket` API to establish raw structural requests over the internet layer via IPv4 address boundaries (`AF_INET`) using the TCP transport protocol layer (`SOCK_STREAM`).
- **Non-Blocking Execution Strategy:** Utilizes the socket API's `connect_ex()` protocol. Instead of raising complex system-blocking runtime exceptions upon interacting with dropped packets or closed firewalls, the methodology intercepts the underlying kernel status code (`0` for clean handshakes).
- **Latency Optimization Filters:** Configures strict socket timeout limits (`settimeout(2.0)`) across individual probes to prevent the parent environment runtime from locking permanently on unresponsive, firewalled, or heavily rate-limited host machines.

---

## 2. Automated Log Parsing & Intrusion Detection System (`log_intrusion_detector.ipynb`)

### Technical Overview
An automated event data monitoring script built to simulate Security Information and Event Management (SIEM) pipeline mechanics. The system ingests standard unstructured server access audit trails, filters authentication discrepancies, maps risk distribution metrics, and identifies live automated password-spraying attacks.

### Architectural Core Concepts & Implementation
- **Dynamic File Ingestion:** Employs buffered file I/O operations (`with open()`) to read server logs line-by-line streaming context patterns smoothly without filling runtime computing memory overhead structures.
- **Data Tokenization & Parsing:** Isolates discrete networking components out of string text rows via split configurations, isolating target elements such as unique source IPs (`IPv4 Pattern Map Extraction`).
- **State Evaluation Arrays:** Manages persistent state counting maps using Hash Mapping / Python Dictionaries to log event totals dynamically per operational identifier across multi-line logs.
- **Threshold Risk Aggregation Engine:** Dynamically measures counts against parameterized boundaries (`failure_threshold=3`) to automatically flag and differentiate normal user authorization mistakes from high-frequency brute-force dictionary attack scripts.
