# Architecture

This document describes the target architecture for `vai_sante_os` as a modular, privacy-first evidence workflow framework.

## Design principles

1. Provenance is mandatory metadata, not an optional feature.
2. Retrieval quality depends on evidence quality and policy constraints.
3. Temporal context is core to reasoning in high-stakes workflows.
4. Human review is a system component, not an afterthought.
5. Every key step should be inspectable and replayable.

## Logical components

- **Ingestion adapters**: Parse and standardise text, image, audio, and structured data.
- **Privacy controls**: Redaction, minimisation, and access policy enforcement.
- **Memory layer**: Durable evidence store + metadata + temporal snapshots.
- **Retrieval layer**: Hybrid search (semantic + symbolic + temporal filters).
- **Orchestration layer**: Tool-using agents with policy-aware routing.
- **Review layer**: Human checkpoints with approval/rework pathways.
- **Evaluation layer**: Trace replay, benchmark runs, and governance metrics.

## Architecture diagram

```mermaid
flowchart LR
    subgraph DataPlane[Data Plane]
      I[Ingestion]
      P[Privacy Controls]
      M[Memory + Provenance]
      X[Indexes\nVector | Graph | Time]
    end

    subgraph ControlPlane[Control Plane]
      O[Orchestration]
      R[Retrieval Policy]
      H[Human Review]
      E[Eval + Audit]
    end

    I --> P --> M --> X
    O --> R --> X
    O --> H
    O --> E
    H --> E
    M --> E
```

## Non-goals

- End-to-end autonomous decision-making.
- Production safety claims without validation.
- Domain-specific compliance guarantees in the current scaffold.
