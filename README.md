
# Project T1 

Tier-1 Adversary Emulation & EDR Defense Validation

---

## 📌 Overview

Project T1 is an end-to-end security engineering initiative conducted at Virtual Testing Foundation (VTF), focused on simulating realistic adversary behavior and validating endpoint detection and response (EDR) capabilities using Palo Alto Cortex XDR.

The project is designed to emulate Tier-1 attack sequences aligned to the MITRE ATT&CK framework, measure detection efficacy, and identify defensive gaps across an enterprise-style hybrid environment.
Internally, T1 represents Trust Layer 1 - the foundational layer of endpoint visibility, detection, and response maturity.

---

## 📌 Project Objective

To simulate realistic attacker behavior across enterprise endpoints and evaluate how effectively **Cortex XDR** detects, correlates, and alerts on those activities using:

- MITRE ATT&CK framework
- Endpoint telemetry
- Identity telemetry
- Network behavior
- Firewall enforcement

The goal was **not** to bypass security, but to **measure detection fidelity**, analyst visibility, and control effectiveness.

---

## 🧠 Core Idea

Most labs focus on *how to attack*.  
Project T1 focuses on **how attacks look from the defender’s console**.

This project bridges:

> **Adversary behavior → EDR telemetry → SOC analysis**

---

## 🔭 Project Scope

In-Scope;
- Endpoint-focused adversary emulation
- ATT&CK-aligned attack chains (Initial Access → Execution → C2 → Impact)
- Cortex XDR detection, telemetry, and alert analysis
- Hybrid enterprise network simulation
<br>

Out-of-Scope;
- Red team exploitation depth
- Production data or live user impact
- Automated response enforcement (observe-first model)

---

## 🏗️ Lab Architecture

<img height="500" src="" alt="Project Network Diag"/>

The lab environment mirrored a small-to-mid enterprise network and included:
- Hybrid identity and access control
- Windows and Linux endpoints
- Centralized EDR telemetry via Cortex XDR
- Simulated attacker host (Kali Linux)
- Controlled C2-style communication paths
- MFA-protected access layers

**Components**
- Windows 11 endpoint
- Ubuntu endpoint
- Kali Linux (Red Team)
- Windows Server 2022 - On prem AD
- Azure AD / Entra ID with MFA - Cloud AD
- Palo Alto Cortex XDR tenant
- Segmented internal network

---

## 🎯 Attack Scenarios Executed

Three full attack paths were designed and executed.

## Scenario 1 - Credential Abuse & Suspicious Logon

Focus: Identity + Endpoint correlation

- Use of valid credentials from non-standard host
- MFA interaction observed
- Endpoint activity after successful authentication
- Identity telemetry correlated with endpoint events
<br>

## Scenario 2 - Privilege Escalation & Defense Evasion

Focus: Endpoint behavioral monitoring

- Enumeration of system privileges
- Abuse of Windows native binaries (LOLBins)
- Attempts to modify or evade security controls
- Preparation for persistence
<br>

## Scenario 3 - Command & Control & Lateral Preparation

Focus: Network + EDR correlation

- Suspicious outbound connections
- Beacon-like behavior patterns
- Process-to-network mapping inside Cortex XDR
- Pre-lateral movement staging behavior

---

## 🛡️ What Was Evaluated in Cortex XDR

- Process creation visibility
- Command-line monitoring
- Registry and file monitoring
- Network connection tracking
- Identity logon correlation
- Agent self-protection capability
- Alert severity accuracy
- Analyst investigation workflow

---

## 🗺️ MITRE ATT&CK Mapping

All activities were mapped to MITRE techniques and evaluated for detection.

See: **`attack-matrix.md`**

---

## 📊 Key Findings

| Area | Observation |
|-----|-------------|
| Identity correlation | Strong detection when logon tied to endpoint activity |
| Behavioral detection | More reliable than IOC-based alerts |
| Privilege escalation | High-confidence alerting with clear context |
| Defense evasion | Detected but required analyst interpretation |
| C2 behavior | Detectable before lateral movement occurred |

---

## 🧩 Skills & Knowledge Gained

- Practical MITRE ATT&CK planning and application
- Cortex XDR investigation workflow
- Endpoint telemetry analysis
- Identity + endpoint event correlation
- Detection engineering mindset
- SOC Tier-1 alert eveluation and perspective during live incidents
- Defensive security research documentation
- Secure lab design and execution discipline

---

## 🌍 Real-World Relevance

This project mirrors what SOC teams and detection engineers do when:

- Investigating suspicious activity alerts
- Tuning EDR rules
- Performing purple-team exercises
- Validating enterprise security controls
- Building detection logic from attacker behavior

The lab architecture and workflow can be directly adapted for:

- Internal security testing
- SOC analyst training
- Internal purple team exercises

---

## 📁 Repository Structure

```
Project-T1
│
├── README.md
├── attack-matrix.md
└── network-diag.png
```

---

## 🚀 Outcome

Project T1 established a baseline for:

- Understanding how modern EDR sees attacks
- Building detection-focused security thinking
- Designing future projects with stronger defensive alignment

This project directly influenced the architecture and goals of subsequent security research projects.

---

## 👤 Collaboration & Contributions

This project is designed, implemented, operated, and documented under the leadership of Dr. Victor Monga and conducted by Derick Dmello, focusing on security engineering, defensive analysis, and operational realism.

---

**Project T1 - Where adversary simulation meets defensive visibility**
