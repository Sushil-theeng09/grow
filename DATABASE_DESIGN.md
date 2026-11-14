# Database Design

## Status

Conceptual design only. No database engine, schema, migration, index, or backup implementation is present or selected in this repository.

## Design principles

- Model durable product concepts and relationships explicitly.
- Preserve referential integrity and use constraints for invariants that belong in storage.
- Separate user identity from learner-specific goals and progress where useful.
- Store only data needed for product behavior; define retention and deletion rules for personal and AI-related data.
- Use migrations as the auditable path for schema changes.
- Add indexes from demonstrated query patterns and measured performance needs.
- Define backup, restore, and recovery objectives before production use.

## Candidate domain entities

These are modeling candidates, not an approved schema:

- **User and identity:** account identifiers, authentication references, status, and access roles.
- **Learner profile and preferences:** learner context, interests, and experience preferences.
- **Goal:** learner-defined development outcome, timeframe, and lifecycle.
- **Skill or capability:** a versioned taxonomy and the evidence or proficiency model associated with it.
- **Course, module, lesson, and resource:** structured learning content, ownership, publication state, and provenance.
- **Learning pathway:** ordered or conditional learning activities associated with goals and capabilities.
- **Enrollment and activity:** learner participation and completion evidence.
- **Assessment and response:** assessment definitions, attempts, results, and evaluation provenance.
- **Practice activity or project:** task definition and learner work or completion evidence.
- **Progress record:** time-stamped evidence of learner activity and capability development.
- **Recommendation:** proposed next step, rationale, source evidence, and lifecycle.
- **AI conversation or interaction:** only if approved; purpose, access controls, retention, and sensitive-data handling must be specified first.
- **Administrative audit event:** security- and operations-relevant changes with restricted access.

## Relationships to validate during detailed design

- A user may have a learner profile, preferences, goals, and learning activity.
- Courses contain modules; modules contain lessons and associated resources.
- A pathway can reference learning activities, courses, practice, and assessments.
- Assessment attempts and activity records provide evidence for progress and recommendations.
- Skill definitions may be referenced by goals, content, assessments, and progress evidence.

Cardinality, tenancy, content ownership, taxonomy governance, and historical versioning remain open decisions.

## Data integrity and lifecycle

- Define required fields, uniqueness, allowed state transitions, and deletion behavior for each entity.
- Decide whether learner data is deleted, anonymized, or retained under defined exceptions when an account is removed.
- Version published course content and assessment definitions when prior learner results depend on their original form.
- Avoid storing secrets in application tables; use an approved secrets-management mechanism once infrastructure is selected.
- Define export, correction, and deletion workflows for personal data before production launch.

## Query and index planning

Likely access patterns include loading a learner dashboard, retrieving pathway content, recording activity, and querying progress over time. Do not create indexes solely from this list; validate access patterns against the chosen engine and representative data, then measure query plans.

## Operational requirements

Before production, select a database and migration approach, define backup frequency and restore testing, set recovery objectives, establish access controls, and document schema-change and incident procedures.
