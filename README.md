# SIEM Home Lab: Detecting Attacker Activity with Wazuh + Cowrie

A self-built SOC lab simulating attacker detection using an SSH honeypot, a SIEM, and custom detection rules.

## Overview
[2-4 sentences]

## Architecture
![Architecture](docs/architecture.png)
- **SIEM VM** — Wazuh manager, receives and correlates logs
- **Honeypot VM** — Cowrie SSH honeypot + Wazuh agent
- **Attacker VM** — Kali, source of simulated attacks
- All on an isolated internal network

## Tech Stack
- Wazuh (manager + agent)
- Cowrie honeypot
- Ubuntu 24.04, Kali Linux
- VirtualBox internal networking

## How It Works
[flow description]

## Custom Detection Rules
```xml
[rule snippet]
```
[why]

## Sample Findings
![Critical alert](docs/screenshots/critical-alert.png)
See [findings/alert_triage.md](findings/alert_triage.md) for full triage log.

## Key Learnings
- [bullet list]

## Setup
See [docs/setup.md](docs/setup.md) for full install/config steps.

## Future Work
- [bullet list]

## References
- Wazuh docs: https://documentation.wazuh.com
- Cowrie: https://github.com/cowrie/cowrie
