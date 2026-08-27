# Online Banking Threat Model

## Overview

This threat model analyzes an online banking workflow using Microsoft's Threat Modeling Tool concepts. The model represents authentication, transaction processing, intrusion detection, customer data, and transaction logging.

## Modeled Components

- Human User
- Attacker
- Security Admin
- Authentication Service
- Transaction Processing Service
- Intrusion Detection System (IDS)
- Customer Database
- Transaction Logs

## Key Data Flows

- Login Request
- Credential Verification
- Login Result
- Transaction Request
- Update Balance
- Store Transaction History
- Malicious Login Attempts
- Suspicious Activity
- Security Alert

## Representative Threats

| Threat category | Example | Priority |
|---|---|---|
| Spoofing | Impersonation of a legitimate banking user | Medium |
| Elevation of Privilege | Gaining higher transaction privileges through impersonation | High |
| Denial of Service | Excessive authentication or transaction requests | High |
| Spoofing / Log Integrity | Manipulating transaction-log records | High |

## Security Focus

The model demonstrates security analysis across the authentication, transaction, and audit paths, with particular attention to:

- Strong authentication and identity assurance
- Authorization boundaries around financial transactions
- Availability controls for authentication and transaction services
- Integrity and trustworthiness of audit logs
- Intrusion detection and security alerting

> The original Threat Modeling Tool project file was reviewed but is not included in this public portfolio package because it contains local/user metadata and tool-generated template content.
