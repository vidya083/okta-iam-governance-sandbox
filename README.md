# Enterprise IAM Architecture & Lifecycle Governance Sandbox

## 📋 Project Overview
This repository documents the technical design, backend configuration, and continuous compliance mapping of an enterprise Identity and Access Management (IAM) environment engineered within a sandboxed Okta ecosystem. 

Designed for a simulated corporate entity, **"Apex Global Analytics,"** this framework maps live administrative identity parameters directly to standard IT General Controls (ITGC), SOX compliance mandates, and ISO 27001/NIST frameworks. It provides clear, actionable evidence of operational effectiveness for information security risk mitigation.

---

## 🛡️ Control Architecture & Backend Implementation

### 1. Automated Lifecycle Management (Joiner/Mover Logic)
* **Objective:** Enforce strict least-privilege standards, minimize manual input, and dynamically mitigate internal horizontal access creep during departmental transfers.
* **Technical Implementation:** * Provisioned three core architectural structural role containers: `Dept-All-Employees`, `Dept-Engineering-All`, and `Dept-Finance-All`.
  * Deployed automated, attribute-driven system policies (`Auto-Assign-Finance` and `Auto-Assign-Engineering`) leveraging conditional user profile metadata parsing (`IF profile.department == 'Finance'`).
  * Executed live testing of delta transfer events by updating target account strings to dynamically trigger real-time, zero-touch provisioning updates and immediate target application revocation pipelines.

### 2. Federated Single Sign-On (SAML 2.0 Integration)
* **Objective:** Consolidate external authentication boundaries, secure trust channels via modern identity protocols, and remove siloed, high-risk application databases.
* **Technical Implementation:**
  * Integrated a simulated enterprise SaaS instance (`Apex-Corporate-ServiceNow`) into the Okta Identity Provider (IdP) ecosystem.
  * Formulated the cryptographic handshake parameters, configuring unique Assertion Consumer Service (ACS) redirect target URLs and Service Provider (SP) Entity ID strings.
  * Evaluated and extracted public X.509 verification token keys to illustrate the backend mechanism used by downstream software configurations to validate authentic, non-tampered assertion payloads.

### 3. Adaptive Authentication & Zero Trust Session Controls
* **Objective:** Harden perimeter controls across highly regulated or privileged business segments, meeting rigorous multi-factor authentication (MFA) parameters under audit scrutiny.
* **Technical Implementation:**
  * Created a dedicated, high-priority fallback security perimeter targeting high-risk employee populations: `Finance-High-Assurance-Perimeter`.
  * Configured contextual contextual logic forcing step-up Multi-Factor Authentication (MFA) challenges at every discrete sign-in point.
  * Applied systemic token constraints, lowering the maximum permissible global idle timeframe threshold to a hard cap of 2 hours to limit risk surface exposure for exposed terminals.

### 4. Continuous Control Auditing & Evidence Verification
* **Objective:** Ensure all identity platform operations remain entirely transparent, tamper-proof, and fully indexable for internal corporate controllers and external compliance reviewers.
* **Technical Implementation:**
  * Leveraged the core immutable Okta System Logs telemetry dashboard to pull backend validation artifacts.
  * Designed targeted system tracking queries filtering discrete schema events (`eventType eq "group.user_membership.add"`).
  * Monitored generated log outputs to verify proper actor attribution, validating that group updates were safely recorded under the authority of the **Okta System Rules Engine** with precise UTC metadata timestamps.

---

## 📊 GRC Framework Mapping Matrix

| Technical Control Deployed | ITGC Control Objective | ISO 27001 Reference | NIST CSF 2.0 Function |
| :--- | :--- | :--- | :--- |
| **Attribute-Driven Rules** | User Access Management / Joiner-Mover Lifecycles | A.8.2 (User Access Provisioning) | PR.AA-1 (Identity Management) |
| **SAML 2.0 / X.509 Exchange**| Secure Data Transmission & Trust Boundaries | A.8.20 (Network Security Controls) | PR.DS-2 (Data-in-Transit Protection) |
| **Step-Up MFA Prompts** | Identification & Strong Authentication Strength | A.5.15 (Access Control Policy) | PR.AA-2 (Authentication) |
| **2-Hour Token Idle Timeout**| Active Session Management & Expiration | A.8.11 (Binding of Assets) | PR.AA-5 (Session Revocation) |
| **System Rules Engine Logs** | Audit Logging & Change Tracking Integrity | A.8.15 (Logging) | PR.PS-1 (Audit Generation) |

---

## 🛠️ Technology Stack
* **Identity Platform:** Okta Developer Directory Instance
* **Protocols Deployed:** SAML 2.0 Identity Federation, Cryptographic X.509 Certificate Authentication
* **Security Architecture:** Zero Trust Adaptive Access Control, Step-Up MFA
* **Compliance Framework Alignment:** Sarbanes-Oxley (SOX Section 404), ISO/IEC 27001:2022 Annex A, NIST CSF 2.0
