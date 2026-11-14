# API Design

## Status

API principles only. No API framework, endpoint, schema, or versioning strategy has been implemented or approved.

## Design goals

- Provide consistent, documented interfaces for the learner experience, administration, and approved integrations.
- Validate all external input and enforce authentication and authorization on every protected operation.
- Keep contracts aligned with domain boundaries and avoid exposing persistence internals.
- Return explicit outcomes; do not disguise failures as successful empty data.

## Contract principles

- Use resource-oriented operations and predictable naming once the API style is selected.
- Define request and response schemas, required fields, constraints, and error cases for each operation.
- Standardize error responses with a stable machine-readable code and a safe user-facing message.
- Document authentication requirements, authorization rules, pagination, filtering, and sorting.
- Use explicit versioning and compatibility policy before public clients depend on the API.
- Validate limits for request size and expensive operations; establish rate limits based on threat and usage modeling.
- Avoid returning personal or AI-context data beyond the caller's authorization.

## Candidate resource areas

Identity and profiles; preferences; discovery; goals; courses, modules, lessons and resources; pathways; practice; assessments and attempts; activity and progress; recommendations; administrative operations; and AI interactions if their data and privacy model are approved.

These are candidate areas, not endpoint commitments.

## Error, asynchronous work, and integrations

- Distinguish invalid input, unauthenticated access, forbidden access, missing resources, conflicts, rate limits, and service failures.
- For long-running work, expose a clearly defined job or status contract rather than a success-shaped placeholder.
- Define timeout, retry, idempotency, and webhook verification behavior for any external integration.
- Do not leak credentials, internal stack traces, or sensitive learner content in errors or logs.

## API readiness checklist

Before implementation of an endpoint, specify its owner, caller, authorization policy, input/output schema, validation, failure behavior, privacy implications, tests, and documentation. No API is currently available.
