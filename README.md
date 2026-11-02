# Autonomous Network Security, Reconnaissance & Cryptography Toolkit

A production-ready repository containing lightweight, low-level Python automation utilities designed to execute passive network reconnaissance, localized intrusion triage parsing, and bitwise data payload obfuscation.

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

---

## 3. Symmetric Payload Cryptography Engine (`network_crypto_engine.ipynb`)

### Technical Overview
A secure programmatic script implementing symmetric stream cipher logic to secure data packets during transit. The framework applies mathematical manipulation over raw ASCII value text elements to enforce cryptographic data confidentiality and integrity controls.

### Architectural Core Concepts & Implementation
- **Bitwise Algorithmic Transformations:** Implements custom algorithmic logic utilizing the native bitwise XOR (`^`) operator gate structure. This serves as a fundamental primer on the mechanics governing stream ciphers and modern block cipher initialization vectors.
- **Dual-Phase Symmetric Reversibility:** Proves basic properties of symmetric cryptography systems—demonstrating that passing obfuscated ciphertext arrays back through the identical bitwise key space reconstructs the original payload block without structural data decay.
- **ASCII Code Parsing Core:** Dynamically maps plain characters directly to native numerical memory addresses via the system's character-integer mapping core engines (`ord()` and `chr()`).
- **Cryptographic Validation Gateways:** Integrates an automated validation check that dynamically cross-references input-output array spaces to guarantee cryptographic integrity across transformation cycles.
