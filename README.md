# 🛡️ Identity & Access Management (IAM) Portfolio

Hands-on IAM engineering projects spanning **Microsoft Entra ID, Okta, Auth0, Keycloak, PowerShell, and the Microsoft Graph API**. Each lab simulates a real-world scenario an IAM engineer would own in production — identity governance, lifecycle automation, federation, and Zero Trust access control — with working scripts and documented outcomes.

> Built to demonstrate the design, automation, and security skills required to operate and scale modern identity systems.

-----

## 🏆 Certifications

- **Microsoft Certified: Identity and Access Administrator Associate (SC-300)** — `[FILL IN: status + date once passed, e.g. "Active — Earned June 2026 | Credential ID: XXXX"]`
- CompTIA Security+ · CompTIA A+ · AZ-900 · ITIL v4 Foundation

-----

## 🧰 Core Skills

|Domain                     |Technologies & Capabilities                                                                                     |
|---------------------------|----------------------------------------------------------------------------------------------------------------|
|**Identity Governance**    |PIM (JIT access), Access Reviews, Entitlement Management, lifecycle (JML) workflows, least-privilege enforcement|
|**Authentication & Access**|Conditional Access, MFA, SSO, Zero Trust policy design                                                          |
|**Federation**             |SAML 2.0, OIDC, SCIM provisioning, cross-IdP trust (Okta, Auth0, Entra, Keycloak)                               |
|**Automation**             |PowerShell, Microsoft Graph API/SDK, CSV audit reporting, scripted remediation                                  |
|**Hybrid Identity**        |Active Directory Domain Services, Azure AD Connect, on-prem → cloud sync                                        |
|**Platforms**              |Microsoft Entra ID, Okta, Auth0, Keycloak, Salesforce, ServiceNow, Docker                                       |

-----

## 👨‍💻 Projects

### 🔐 Okta ⇄ Salesforce Lifecycle Automation (SSO + SCIM Provisioning)

**Objective:** Make Okta the single source of truth for Salesforce identities, automating the full Joiner–Mover–Leaver lifecycle.
**Impact:** Eliminated manual onboarding/offboarding by configuring SAML SSO plus SCIM (OAuth) provisioning — users were created, updated, and deactivated in Salesforce in real time from Okta profile changes, closing the offboarding gap that leaves orphaned SaaS access. `[FILL IN: # of lifecycle scenarios tested, or time saved per user event]`
**Skills:** Okta · Salesforce · SAML · SCIM · OAuth · Lifecycle Automation
📁 [Week 12 – Okta ⇄ Salesforce Lifecycle Automation](https://github.com/Ingrambtp3/IAM--PROJECTS/tree/main/Week-12-OktaxSalesforce-JML)

-----

### 🧩 Keycloak IAM Lifecycle (Joiner–Mover–Leaver)

**Objective:** Stand up a full enterprise identity-governance lifecycle in a self-hosted IdP.
**Impact:** Built a complete JML simulation in Keycloak + Docker with RBAC, MFA, OIDC SSO, and audit logging — and troubleshot real-world failure modes (misconfigured redirect URIs, disabled accounts) the way an operator would in production.
**Skills:** Keycloak · Docker · OIDC · RBAC · MFA · Audit Governance
📁 [Week 11 – Keycloak IAM Lifecycle (JML)](https://github.com/Ingrambtp3/IAM--PROJECTS/blob/main/Week%2011/readme.md)

-----

### 🔐 Hybrid Identity Access Governance (Group-Based App Provisioning)

**Objective:** Automate cloud application access using on-prem group membership.
**Impact:** Linked on-prem AD security groups to a ServiceNow enterprise app through Azure AD Connect sync, so adding a user to an on-prem group automatically provisioned their cloud access — a real-world RBAC onboarding flow that enforces least privilege and removes manual access grants.
**Skills:** Active Directory · Azure AD Connect · Entra ID · RBAC · Group-Based Provisioning
📁 [Week 10 – Hybrid Identity Access Governance](https://github.com/Ingrambtp3/IAM--PROJECTS/tree/main/Week%2010)

-----

### 🔐 Hybrid Identity Lab (On-Prem AD → Entra ID)

**Objective:** Bridge legacy on-prem directory infrastructure with a cloud identity platform.
**Impact:** Deployed a Windows Server 2019 domain controller in Azure and synced on-prem AD identities to Entra ID via Azure AD Connect, replicating how enterprises run hybrid identity during cloud migration. Resolved PowerShell module/sync issues to achieve reliable directory synchronization.
**Skills:** AD DS · Azure AD Connect · Entra ID · PowerShell · Hybrid Architecture
📁 [Week 9 – Hybrid Identity Lab](https://github.com/Ingrambtp3/IAM--PROJECTS/tree/main/week09-hybrid-identity-ad-sync)

-----

### 🔐 SAML SSO Federation (Auth0 IdP → Entra ID SP)

**Objective:** Establish a federated SSO trust between a third-party IdP and Entra ID.
**Impact:** Manually configured a SAML 2.0 trust — exporting Auth0 metadata, importing the X.509 signing cert into Entra, and defining ACS/Entity ID settings — then validated an IdP-initiated login end-to-end. Demonstrates assertion handling and cross-platform trust without relying on pre-built gallery connectors.
**Skills:** SAML 2.0 · Identity Federation · X.509 Certificates · Auth0 · Entra ID
📁 [Week 8 – SAML SSO Lab](https://github.com/Ingrambtp3/IAM--PROJECTS/tree/main/week%208)

-----

### ✅ Inactive Guest User Cleanup (Graph PowerShell)

**Objective:** Automate identity hygiene by detecting stale guest accounts.
**Impact:** Scripted the Microsoft Graph PowerShell SDK to pull all guest users, check last sign-in timestamps, and export accounts inactive 30+ days (or never signed in) to a CSV — turning a manual audit into a repeatable report that reduces standing external attack surface.
**Skills:** Microsoft Graph SDK · PowerShell · Identity Lifecycle · Reporting
📁 [Week 7 – Inactive Guest User Cleanup](https://github.com/Ingrambtp3/IAM--PROJECTS/tree/main/week%207)

-----

### 🔎 PIM Role Audit & Auto-Cleanup (Graph PowerShell)

**Objective:** Enforce time-bound privileged access by catching roles active beyond policy.
**Impact:** Built a PowerShell + Graph script that retrieves active role assignments, flags any still active past the allowed window, exports violations to CSV, and optionally auto-removes them — plus a mock-data test harness to validate the logic. Operationalizes least privilege instead of trusting it to manual review.
**Skills:** PIM · Microsoft Graph API · PowerShell · Audit Logging · Least Privilege
📁 [Week 6 – PIM Role Audit & Auto-Cleanup](https://github.com/Ingrambtp3/IAM--PROJECTS/tree/main/Week%206#readme)

-----

### 🔐 PIM Role Activation Automation (Graph PowerShell)

**Objective:** Streamline Just-In-Time privileged access activation.
**Impact:** Wrote a parameterized PowerShell script (user email, role, duration) that activates eligible PIM roles via Graph and logs each activation to CSV — modeling the controlled, audited access elevation enterprises require for admin work.
**Skills:** PIM · JIT Access · Microsoft Graph API · PowerShell · Governance
📁 [Week 5 – PIM Role Activation Automation](https://github.com/Ingrambtp3/IAM--PROJECTS/tree/main/Week%205)

-----

### 🛡️ Access Review Automation (Graph PowerShell)

**Objective:** Automate the collection of Access Review decision data for auditing.
**Impact:** Authenticated through a custom app registration, queried Access Review instances and decisions via Graph, and exported results to CSV — replacing manual governance reporting with a repeatable, least-privilege automated pull.
**Skills:** Microsoft Graph API · PowerShell · Identity Governance · App Registrations
📁 [Week 4 – PowerShell Access Review Automation](https://github.com/Ingrambtp3/IAM--PROJECTS/tree/main/WEEK%204%20Automation)

-----

### ✅ Access Reviews in Entra ID

**Objective:** Ensure users retain only the access they still need.
**Impact:** Configured and tested Entra ID Access Reviews, assigned reviewers, and applied decisions to remove unnecessary access — practicing the recurring certification cycle that keeps entitlements clean and audit-ready.
**Skills:** Entra ID · Access Reviews · Identity Governance · Least Privilege
📁 [Week 3 – Access Reviews](https://github.com/Ingrambtp3/IAM--PROJECTS/tree/main/Week%203%20Access%20Reviews)

-----

### 🛡️ Scenario-Based Privilege Remediation

**Objective:** Identify and remediate excessive privilege on a compromised-style test account.
**Impact:** Removed excessive permissions, stood up Access Reviews to monitor privileged assignments, and applied PIM for controlled administrative access — a remediation workflow mirroring real incident cleanup.
**Skills:** Privilege Remediation · PIM · Access Reviews · Least Privilege
📁 [Week 2 – Scenario-Based Remediation](https://github.com/Ingrambtp3/IAM--PROJECTS/tree/main/Week%202#readme)

-----

### 🔑 Conditional Access & MFA Baseline

**Objective:** Establish a Zero Trust access baseline in Entra ID.
**Impact:** Configured Conditional Access policies and MFA with RBAC, building context-aware access controls keyed to user, risk, device, and location — the foundational guardrails every Entra tenant needs.
**Skills:** Conditional Access · MFA · RBAC · Zero Trust · Entra ID
📁 [Week 1 – Azure Conditional Access & MFA](https://github.com/Ingrambtp3/IAM--PROJECTS/blob/main/week-1-iam)

-----

## 📫 Connect

- **LinkedIn:** [allon-ingram](https://www.linkedin.com/in/allon-ingram-0a0803226)
- `[FILL IN: portfolio site or email if you want it here]`


