# 🛡️ SIEM Home Lab: Detecting Attacker Activity with Wazuh + Cowrie

A self-built SOC lab simulating attacker detection using an SSH honeypot, a SIEM, and custom detection rules.

---

## 📖 Overview
[2-4 sentences]

---

## 🏗️ Architecture
![Architecture](docs/architecture.png)

- 🖥️ **SIEM VM** — Wazuh manager, receives and correlates logs
- 🍯 **Honeypot VM** — Cowrie SSH honeypot + Wazuh agent
- 💻 **Attacker VM** — Kali Linux, source of simulated attacks
- 🌐 All machines connected through an isolated internal network

---

## ⚙️ Tech Stack

- 🛡️ Wazuh (Manager + Agent)
- 🍯 Cowrie Honeypot
- 🐧 Ubuntu 24.04
- 🐉 Kali Linux
- 📦 VirtualBox Internal Networking

---

## 🔄 How It Works

[flow description]

---

## 🎯 Custom Detection Rules

```xml
[rule snippet]
```

📝 **Purpose:**  
[why]

---

## 🚨 Sample Findings

![Critical alert](docs/screenshots/critical-alert.png)

📄 See **[findings/alert_triage.md](findings/alert_triage.md)** for the complete investigation and triage log.

---

## 📊 Key Learnings

- ✅ [bullet list]
- 🔍 [bullet list]
- 🛡️ [bullet list]
- 📈 [bullet list]

---

## 🚀 Setup

📖 See **[docs/setup.md](docs/setup.md)** for the complete installation and configuration guide.

---

## 🔮 Future Work

- 🤖 [bullet list]
- 📧 [bullet list]
- ☁️ [bullet list]
- 📊 [bullet list]

---

## 📚 References

- 📖 Wazuh Documentation: https://documentation.wazuh.com
- 🍯 Cowrie GitHub: https://github.com/cowrie/cowrie
