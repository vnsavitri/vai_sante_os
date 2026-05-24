# Threat model

This is a lightweight starting threat model for high-stakes evidence workflows.

## Assets

- source evidence and metadata
- provenance chains and audit logs
- access-control policies
- model prompts, outputs, and tool traces

## Threat classes

- **Data poisoning**: manipulated source artefacts enter ingestion.
- **Provenance tampering**: chain-of-custody metadata is altered or stripped.
- **Prompt injection**: malicious content biases retrieval or orchestration.
- **Privacy leakage**: sensitive data appears in logs, outputs, or embeddings.
- **Review bypass**: risky tasks skip required human checkpoints.

## Baseline mitigations

- immutable artefact IDs and append-only trace logs
- content signing and checksum verification where possible
- policy-gated tool execution for high-impact actions
- explicit review gates with escalation criteria
- periodic red-team style replay tests

## Open risks

- cross-modal hallucination under weak or noisy evidence
- false confidence when provenance exists but evidence is low quality
- performance trade-offs between strict policy checks and latency
