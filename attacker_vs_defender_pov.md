# Attacker vs Defender Perspective Analysis  
*(MITRE ATT&CK–Driven Case Study)*

---

## Introduction
Security incidents can be better understood when analyzed from both the attacker’s and defender’s viewpoints. This case study examines a simulated brute-force authentication attempt by evaluating attacker intent and techniques alongside SOC detection and response processes.

---

## Scenario Overview
A brute-force login attempt targets a valid user account by repeatedly submitting incorrect passwords. The goal is to obtain unauthorized access or identify weak authentication controls.

---

## Attacker Point of View (POV)
From the attacker’s perspective, the objective is to compromise credentials while avoiding detection.

### Attacker Goals
- Gain unauthorized access to a valid user account
- Exploit weak authentication controls
- Avoid triggering security alerts

### Key Attacker Assumptions
- The username is valid
- Account lockout policies may be weak or absent
- Failed authentication attempts may not be actively monitored
- Detection thresholds may be poorly configured

The attacker relies on automated or repeated manual attempts, expecting minimal resistance if monitoring controls are insufficient.

---

## Defender Point of View (SOC POV)
From a SOC analyst’s perspective, repeated authentication failures within a short time window raise suspicion of malicious activity.

### SOC Analysis Focus
- Number of failed login attempts
- Time interval between attempts
- Login attempts outside business hours
- Sensitivity and role of the targeted user account
- Patterns indicating automation or brute-force behavior

Windows Security Event Logs are reviewed to assess frequency, timing, and context of authentication failures.

---

## Detection & Monitoring
Brute-force detection relies on:
- Monitoring failed authentication events
- Applying alert thresholds based on frequency and timing
- Centralized log collection and correlation

### Detection Gaps
Detection effectiveness depends on:
- Proper logging configuration
- Strong account lockout policies
- Centralized SIEM monitoring
- Well-defined alert thresholds

In environments with weak logging or misconfigured thresholds, brute-force attacks may go undetected or detected late.

---

## MITRE ATT&CK Mapping
- **Tactic:** Credential Access  
- **Technique:** Brute Force (T1110)

### Technique Explanation
The attacker repeatedly submits incorrect passwords for a known user account in an attempt to obtain valid credentials, directly aligning with the Brute Force technique under the Credential Access tactic.

---

## SOC Decision & Response
**Classification:** True Positive  

### Immediate Response Actions
- Temporarily lock the affected user account
- Block the suspicious source IP address
- Notify the affected user
- Escalate the incident to Tier-2 SOC analysts
- Review authentication and monitoring policies

---

## Lessons Learned
Analyzing attacks from both attacker and defender perspectives improves detection accuracy and response effectiveness. Understanding attacker techniques enables SOC teams to anticipate threats, close defensive gaps, and strengthen authentication and monitoring controls.

---

## Purpose of This Project
This case study demonstrates practical SOC thinking by combining adversary behavior analysis with defensive detection and response strategies.