# Cloud agent IGA boundary

Agent-IGA owns identity governance and access lifecycle for AGenNext agents, users, services, and infrastructure access.

## Decision

Agent-IGA is distinct from Agent-Identity and Agent-Auth.

- Agent-Auth authenticates sessions.
- Agent-Identity verifies DID/VC trust claims.
- Agent-IGA governs access lifecycle, entitlement reviews, and access policy compliance.

## Boundary

| Component | Responsibility |
|---|---|
| Agent-IGA | Access governance, entitlement lifecycle, access reviews |
| Agent-Auth | Authentication and sessions |
| Agent-Identity | DID/VC verification and trust decisions |
| Agent-Registry | DID/service registry and discovery |
| Agent-Secrets | Secret access boundaries and vaulting |
| Agent-Compliance | Compliance control mapping and evidence |
| Agent-Runtime | Consumes access decisions |

## Agent-IGA owns

- access request workflows
- access approval lifecycle
- entitlement catalog
- role and permission reviews
- privileged access governance
- time-bound access policies
- access recertification
- separation-of-duties checks
- access evidence for compliance
- deprovisioning policy

## Cloud agent IGA examples

For k8smicro and OVH/Kimsufi operations, Agent-IGA should govern:

- who can approve server reinstall actions
- who can access SSH credentials
- who can read SurrealDB memory
- who can mutate Kubernetes clusters
- who can deploy runtime workers
- who can bypass security gates
- time-limited break-glass access

## Flow

```txt
User requests privileged infrastructure action
  ↓
Agent-Auth authenticates user
  ↓
Agent-Identity verifies trusted identity/claims
  ↓
Agent-IGA checks entitlement and access policy
  ↓
Agent-Runtime executes only if access is permitted
  ↓
Agent-Traces records evidence
  ↓
Agent-Compliance maps evidence to controls
```

## Rule

Agent-IGA answers: should this authenticated and trusted actor have this access now?
