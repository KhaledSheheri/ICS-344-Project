# ICS344 Project - Phase 2
**Student Name**: Khalid Alshehri  
**University**: KFUPM  
**Course**: ICS 344 - Computer and Network Security

---

# Phase 2: Visual Analysis with a SIEM Dashboard

---

## Introduction

In this phase, a Security Information and Event Management (SIEM) system was implemented using Splunk Enterprise to collect, upload, analyze, and visualize SSH attack logs.  
The objective was to monitor activities from both the attacker (Kali Linux) and the victim (Metasploitable3) environments, and detect cyberattack patterns using log analysis and visualization.

---

## Step 1: Environment Setup

| Machine | Role | Description |
|:--------|:-----|:------------|
| Kali Linux (VMware) | Attacker | Performed SSH brute-force and scripted attacks |
| Metasploitable3 (UTM) | Victim | Hosted a vulnerable SSH service |
| MacBook Pro (Host) | SIEM/Monitoring | Installed and operated Splunk Enterprise |

- Splunk Version: **9.4.1**
- Network Mode: **Bridge Network** to allow direct connection.

---

## Step 2: Splunk Installation

- Downloaded Splunk Enterprise `.dmg` package for Mac.
- Installed Splunk using the graphical installer.
- Accepted license agreements.
- Set the Splunk administrator username and password.

✅ **Screenshot:** *(Insert Splunk installation screenshot)*

---

## Step 3: Attack Simulation

SSH attacks were performed to generate log activity:

- **Task 1.1**: Using Metasploit Framework:
  - Launched an SSH login attempt exploit.
  - Targeted IP address: 172.20.10.5 (Metasploitable3).
  - Username and password: vagrant/vagrant.
  
- **Task 1.2**: Using a custom Python script:
  - Scripted SSH login automation using `paramiko` library.
  - Connected from Kali to Metasploitable3 IP address.

✅ **Proof:** *(Insert screenshot of successful Metasploit login and Python script execution)*

---

## Step 4: Extracting Log Files

### 4.1 On the Victim Machine (Metasploitable3)

```bash
sudo cp /var/log/auth.log /home/vagrant/
sudo chmod 644 /home/vagrant/auth.log

