# 📋 Botium Toys: Controls & Compliance Checklist

This document details the comprehensive evaluation of controls and compliance practices conducted during the internal security audit of Botium Toys.

---

## 1. Controls Assessment Matrix

| Category | Specific Control | Currently in Place? | Observed Risk & Evaluation Notes |
| :--- | :--- | :---: | :--- |
| **Identity & Access** | Principle of Least Privilege | ❌ **NO** | All internal employees have unrestricted read/write access to internal data, including payment card records and customer PII/SPII. |
| **Identity & Access** | Separation of Duties | ❌ **NO** | Administrative, financial, and operational roles lack separation; high-risk operations lack independent review or dual authorization. |
| **Identity & Access** | Password Complexity Policy | ❌ **NO** | Password requirements are nominal and fail to meet industry complexity standards (length, character sets, expiration). |
| **Identity & Access** | Centralized Password Manager / IAM | ❌ **NO** | No centralized directory (IAM/SSO). Manual password reset requests cause significant IT support friction and downtime. |
| **Identity & Access** | Multi-Factor Authentication (MFA) | ❌ **NO** | Authentication relies solely on single-factor passwords, leaving accounts vulnerable to phishing and brute force. |
| **Data Protection** | Data Encryption at Rest | ❌ **NO** | Credit card details and customer PII are stored in plain text inside local database servers. |
| **Data Protection** | Data Encryption in Transit | ❌ **NO** | Internal network transactions and payment data flows lack mandatory TLS 1.3 encryption. |
| **Data Protection** | Data Integrity Controls | ✅ **YES** | Basic integrity checks and controls have been integrated by the IT department for database transactions. |
| **Network & Threat** | Stateful Firewall | ✅ **YES** | Perimeter firewall deployed and actively filtering network traffic according to predefined security rule sets. |
| **Network & Threat** | Antivirus / Anti-Malware Software | ✅ **YES** | Antivirus installed across endpoints and workstations, regularly updated and monitored by IT. |
| **Network & Threat** | Intrusion Detection System (IDS) | ❌ **NO** | No NIDS or HIDS deployed. The security team cannot detect real-time intrusions, anomalous traffic, or lateral movement. |
| **Operations** | Disaster Recovery Plan (DRP) & BCP | ❌ **NO** | No formal disaster recovery or business continuity plans exist to handle catastrophic system outages or cyber incidents. |
| **Operations** | Data Backups | ❌ **NO** | Zero automated or offline backups exist for critical customer databases and system configurations. |
| **Operations** | Legacy System Maintenance | ❌ **NO** | End-of-life legacy systems require manual monitoring; no patch schedule or documented intervention procedures exist. |
| **Physical Security** | Physical Door Locks & Deadbolts | ✅ **YES** | Sufficient physical locks and deadbolts installed across storefront, corporate offices, and warehouse. |
| **Physical Security** | Closed-Circuit TV (CCTV) | ✅ **YES** | Modern CCTV cameras monitoring facility perimeter, store entrance, and warehouse storage. |
| **Physical Security** | Fire Detection & Prevention | ✅ **YES** | Functioning smoke alarms and fire suppression systems installed and compliant with local safety codes. |

---

## 2. Regulatory Compliance Evaluation Matrix

| Framework / Standard | Jurisdiction / Scope | Compliance Status | Key Gaps & Regulatory Exposure |
| :--- | :--- | :---: | :--- |
| **PCI DSS v4.0** *(Payment Card Industry Data Security Standard)* | Global — Cardholder Data Environment | ❌ **NON-COMPLIANT** | **Critical Violations:** Storing unencrypted primary account numbers (PAN), lack of end-to-end transport encryption, and failure to restrict access via least privilege. Risks monthly fines ($5,000–$100,000) and card processor termination. |
| **GDPR** *(General Data Protection Regulation)* | European Union — EU Customer PII | ❌ **NON-COMPLIANT** | **Deficiencies:** Lacks technical privacy by design safeguards (encryption, access controls), missing Data Protection Impact Assessments (DPIA), and lacks a tested 72-hour incident notification workflow. Risks fines up to €20M or 4% of global turnover. |
| **SOC 1 & SOC 2 Type II** *(AICPA Trust Services Criteria)* | Corporate Governance & B2B Trust | ❌ **DEFICIENT** | **Gaps:** Absence of formal change management, lack of audit logging/accounting, unsegregated financial duties, and lack of independent control verification. Impairs enterprise retail partnerships and investor valuation. |

---

## 3. Audit Scoring Summary

$$\text{Initial Inherent Risk Score: } \mathbf{8\ /\ 10\ (High\ Risk)}$$
$$\text{Projected Residual Risk Score Post-Remediation: } \mathbf{2\ /\ 10\ (Low\ Risk)}$$
