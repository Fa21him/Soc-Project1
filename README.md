# 🛡️ SIEM Home Lab: Detecting Attacker Activity with Wazuh + Cowrie

A self-built SOC lab that uses **Wazuh** for log correlation and the **Cowrie** SSH honeypot to capture and alert on simulated attacker activity — all inside an isolated internal network.

📷 **[View all screenshots (PDF)](media)**

## 🏗️ Lab Architecture

- 🖥️ **SIEM-Blue VM** — Wazuh manager; correlates logs
- 🍯 **SIEM-Red VM** — Cowrie honeypot + Wazuh agent
- 💻 **Kali VM** — source of simulated attacks
- 🌐 All connected on an isolated internal network

  ![image alt](https://github.com/Fa21him/Soc-Project1/blob/main/Screenshot%202026-07-24%20043942.png?raw=true)

## ⚙️ What It Covers

**Wazuh** is an open-source SIEM providing threat detection, file integrity monitoring, and alerting — a free alternative to Splunk or QRadar.

**🔧 Setup steps:**
1. 🖥️ Install Wazuh Manager on SIEM-Blue and open its agent ports (`1514/tcp`, `1515/tcp`) on the firewall.
2. ✅ Install the Wazuh agent on SIEM-Red and confirm it shows as **Active** in the dashboard.
3. 🍯 Install Cowrie on SIEM-Red, then forward its logs to Wazuh via `ossec.conf`.
4. 🔑 Add fake credentials to `userdb.txt` so attackers can "log in" and generate real auth events.
5. 🔀 Move real SSH to port `22022`, then redirect port `22`/`23` traffic to Cowrie with `iptables`.
6. 📜 Write custom Wazuh rules (`local_rules.xml`) to flag Cowrie login/command events.

## 🚨 Detection & Alerting

Once wired up, Wazuh scores every event with a severity level:

| Level | Meaning |
|---|---|
| 🟢 Low (0–6) | Informational |
| 🟡 Medium (7–11) | Suspicious, needs review |
| 🟠 High (12–14) | Significant security event |
| 🔴 Critical (15+) | Immediate attention required |

A custom rule marks any successful SSH login to the honeypot as **Critical**, making real compromise attempts stand out from routine noise.

> 💡 **Tip:** avoid giveaway usernames like `siem-red` — common ones (`root`, `admin`, `ubuntu`) make the honeypot more convincing. 🕵️

---
📷 Full walkthrough with project **[soc-project-one](soc-project-pdf)** ✨
