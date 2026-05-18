# Agent IGA

Agent IGA is the identity governance and privileged access governance adapter layer between enterprise IGA/PAM tools and Agent Platform.

IGA means Identity Governance and Administration.

## Purpose

Agent IGA makes agents, humans, tools, secrets, groups, roles, and entitlements compatible with enterprise access governance and privileged access management processes.

## Responsibility

Agent IGA owns:

- access audit contracts
- access review / certification contracts
- role modeling contracts
- RBAC mapping
- group mapping
- entitlement mapping
- privileged access review
- segregation-of-duties checks
- least-privilege analysis
- toxic access combination detection
- recertification campaigns
- auditor evidence export
- IGA/PAM adapter contracts

## Example Upstream IGA Systems

- SailPoint
- Saviynt
- Microsoft Entra ID Governance
- Okta Identity Governance
- Omada
- One Identity

## Example Upstream PAM Systems

- CyberArk
- BeyondTrust
- Delinea
- HashiCorp Vault
- Teleport

## Relationship to Agent Platform

```text
Company IGA / PAM
  → Agent-IGA
  → Agent-Platform access model
  → Agent-Runtime enforcement
  → Agent-Traces audit evidence
  → Agent-Dashboard governance views
```

## Boundary with Agent-LCM

```text
Agent-LCM
  → lifecycle synchronization
  → joiner / mover / leaver
  → HRMS / IAM provisioning events

Agent-IGA
  → access governance
  → access reviews
  → role modeling
  → RBAC / groups
  → privileged access review
  → audit evidence
```

## Core Principle

```text
Every agent, human, tool, secret, role, group, and permission must be reviewable, explainable, and revocable.
```

## Final Rule

No access should exist without ownership, purpose, approval, reviewability, and revocation path.
