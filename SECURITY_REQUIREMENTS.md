# Security Requirements

## Status

Security requirements for future development. No application security controls have been implemented or verified in this documentation-only repository.

## Core requirements

- Protect authentication secrets and never commit credentials or expose them to client code.
- Authenticate protected operations and enforce authorization at trusted service boundaries.
- Apply least privilege to users, administrators, services, and operational tooling.
- Validate and constrain all external input; encode output appropriately for its destination.
- Protect personal learner data in transit and at rest using controls appropriate to the selected infrastructure.
- Minimize collection and retention of learner profile, activity, assessment, and AI interaction data.
- Use secure, reviewed dependency and configuration management.
- Record security-relevant administrative actions without placing secrets or unnecessary personal content in logs.
- Apply abuse protections, request limits, and rate limits appropriate to exposed operations.
- Define secure error behavior that does not disclose credentials, internal details, or unauthorized records.

## AI and third-party data

- Treat AI models, external services, imported content, and generated outputs as trust boundaries.
- Review data processing, retention, training use, residency, and access terms before selecting a provider.
- Do not send sensitive or identifying learner context to a provider without an approved purpose and safeguards.
- Verify external callbacks and integration credentials; constrain permissions and rotate credentials through an approved process.

## Administration

Administrative functions must use explicit roles and permissions, least-privilege defaults, and auditability for sensitive changes. Separate user-facing access from platform configuration and privileged operations.

## Required lifecycle controls

Before production, establish threat modeling, dependency and secret scanning, security-focused tests, vulnerability triage, incident response, backup access control, data deletion/export procedures, and a process for reviewing changes that affect personal data or authorization.

## Verification

Security acceptance criteria must be included in feature work. Do not claim compliance or security certification without a defined standard, evidence, and review. This document is a baseline, not a completed security audit.
