# AI Architecture

## Status

AI product capabilities are part of the vision; no model, provider, prompt, retrieval system, or AI-backed behavior has been implemented or selected.

## Intended capabilities

- AI learning assistant and personalized explanations.
- Context-aware learning conversations.
- AI-assisted exercise and assessment support.
- Recommendation intelligence.
- Retrieval-augmented generation and embeddings only where a validated content and retrieval use case requires them.
- Evaluation of output quality, safety, cost, and latency.

## Design principles

- Clearly distinguish generated suggestions from verified course content and learner-recorded evidence.
- Never fabricate sources, assessment results, completed activities, or learner progress.
- Ground educational answers in approved materials when the experience promises source-grounded answers; expose provenance where appropriate.
- Treat model output as untrusted and validate it before using it in product workflows.
- Keep human and learner judgment in control of consequential evaluations and recommendations.
- Minimize context sent to a model and do not send personal data unless purpose, consent, provider terms, and safeguards are approved.
- Provide useful failure behavior when a model is unavailable, without presenting fabricated responses as AI output.

## Logical flow

1. Identify the user-requested learning task and applicable privacy and safety constraints.
2. Assemble only authorized, relevant context from approved sources.
3. Apply a task-specific prompt and output contract.
4. Call an approved model service through a controlled integration boundary.
5. Validate output, cite supporting material where required, and reject unsafe or malformed results.
6. Return the result with suitable limitations and capture privacy-conscious quality and operational metrics.

This is a target flow, not an implemented pipeline.

## Evaluation and operations

Before launch, define task-specific quality criteria, representative evaluation data, safety testing, regression checks, latency and cost budgets, usage limits, and escalation behavior. Monitor aggregate usage and failures while avoiding unnecessary retention of prompts and learner content.

## Decisions required

Choose supported AI use cases and boundaries; provider and model; data-processing and retention terms; source-content permissions; evaluation ownership; user disclosure and consent; and whether embeddings or vector search are justified. Record approved decisions in [TECHNICAL_DECISIONS.md](./TECHNICAL_DECISIONS.md).
