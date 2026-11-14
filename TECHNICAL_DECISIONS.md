# Technical Decisions

## Decision record policy

Record significant technical choices with context, alternatives, trade-offs, status, and consequences. Do not treat a proposal or evaluation as an approved decision. Revisit accepted decisions when requirements or evidence materially change.

## Decisions

### TD-001: Defer selection of the technology stack

- **Status:** Open; no technology selected.
- **Context:** The repository currently has no application code or concrete workload constraints. The product vision spans web experience, APIs, persistence, AI, and operations.
- **Decision:** Do not introduce a language, framework, database, cloud provider, or deployment platform until MVP requirements and evaluation criteria are established.
- **Reasoning:** Premature selection would be speculative and could constrain the product without evidence.
- **Next step:** During product and technical discovery, compare candidates for requirements fit, compatibility, maintainability, scalability, security, complexity, performance, cost, and documentation; record an approved decision before implementation.

### TD-002: Treat architecture areas as logical boundaries, not separate services

- **Status:** Provisional guiding principle.
- **Context:** The product has distinct identity, learning, assessment, progress, AI, and administrative capabilities, but no scale or deployment requirements are known.
- **Decision:** Design for clear modular boundaries without committing to microservices or other deployment decomposition.
- **Reasoning:** This preserves separation of concerns while avoiding operational complexity without a demonstrated need.
- **Revisit when:** Workload, team ownership, reliability, or scaling evidence supports a different deployment boundary.

### TD-003: Defer AI provider and retrieval technology

- **Status:** Open; no provider, model, embeddings, vector search, or RAG technology selected.
- **Context:** AI is part of the vision, but intended use cases, source content, privacy terms, evaluation criteria, and cost targets are unresolved.
- **Decision:** Approve specific AI use cases and data safeguards before selecting or integrating providers or retrieval infrastructure.
- **Next step:** Define an evaluation plan and compare options against quality, safety, privacy, cost, latency, and operational needs.
