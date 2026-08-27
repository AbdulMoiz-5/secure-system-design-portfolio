# Ransomware Threat Modeling — EHR System

## Overview

This case study models a simulated ransomware incident against a healthcare Electronic Health Record (EHR) environment. The analysis combines legitimate system interactions with attacker misuse cases and defensive mitigations.

## Legitimate System Model

The baseline use-case model identifies four primary actors:

- **IT Administrator:** configures backup schedules.
- **Doctor:** views patient records and updates medical history.
- **Patient:** accesses the patient portal.
- **External Lab System:** retrieves laboratory results.

The model uses authentication as a supporting control for privileged clinical actions.

## Attack Scenario

The simulated attack follows a double-extortion ransomware pattern:

1. **Initial access:** targeted phishing delivers a malicious document.
2. **Execution and lateral movement:** the attacker establishes command-and-control and moves through vulnerable SMB infrastructure.
3. **Impact:** patient data and backups are encrypted.
4. **Exfiltration:** sensitive records are stolen to increase extortion pressure.

## Misuse Cases and Mitigations

| Misuse case | Defensive control |
|---|---|
| Phishing / malicious attachment | EDR and endpoint protection |
| SMB-based lateral movement | Disable SMBv1 and segment the network |
| Encryption of patient data and backups | Immutable, offline backups |
| Sensitive-data exfiltration | Data Loss Prevention (DLP) |

## Threat Intelligence Mapping

- **T1566.001 — Spearphishing Attachment**
- **T1486 — Data Encrypted for Impact**
- **T1048 — Exfiltration Over Alternative Protocol**
- **CVE-2017-0144 — EternalBlue / SMBv1**

## Defensive Architecture

The analysis recommends a defense-in-depth approach built around:

- Zero Trust principles
- Network segmentation
- Endpoint Detection and Response
- Immutable/offline backup architecture
- Least privilege and strong authentication
- Egress monitoring and DLP
- Removal of legacy protocols

## Related Artifacts

- [`ehr-use-case-diagram.svg`](../diagrams/ehr-use-case-diagram.svg)
- [`ehr-misuse-case-diagram.svg`](../diagrams/ehr-misuse-case-diagram.svg)
