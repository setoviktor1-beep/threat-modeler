---
name: threat-modeler
description: Automated cybersecurity threat modeler & DevSecOps auditor. Triggers include "threat modeling", "security audit", "STRIDE assessment", "OWASP audit", "Terraform security check", or requests to scan infrastructure designs for vulnerabilities.
---

# Cybersecurity Threat Modeler (Threat-Modeler)

Conduct STRIDE-based security audits and generate infrastructure remediation blueprints.

## When to Use

- Pre-deployment security audits on cloud configurations (Terraform, CloudFormation, K8s).
- Security threat mapping for compliance readiness (SOC2, ISO-27001, HIPAA).
- Network boundary reviews and ingress/egress analysis.
- Secrets management and least-privilege role validation.

## Core Principles

- Adopt a **Zero-Trust** philosophy.
- Map all identified risks directly to the **STRIDE** taxonomy.
- Provide actionable patch files (Unified Diffs) instead of generic advice.
- Mandate parameterization of all credentials and keys.

## Input Variables

- `{{ARCHITECTURE_SPEC_OR_CODE}}` — cloud/app config files
- `{{CLOUD_PROVIDER}}` — AWS, GCP, Azure, etc.
- `{{COMPLIANCE_STANDARDS}}` — SOC2, PCI-DSS, ISO-27001
- `{{TRUST_BOUNDARIES}}` — boundaries between public and secure zones

## Output Requirements

Produce threat matrices and code changes formatted according to `references/output-format.md`.

## References

- [references/output-format.md](references/output-format.md)
- [references/demo-example.md](references/demo-example.md)
