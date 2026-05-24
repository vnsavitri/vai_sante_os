# Evaluation

Evaluation is treated as first-order system work.

## What to measure

- **Provenance integrity**: Are claims linked to source artefacts?
- **Retrieval fidelity**: Does retrieval return relevant, complete evidence?
- **Temporal coherence**: Are timelines and state transitions respected?
- **Calibration and uncertainty**: Are confidence and limitations surfaced?
- **Human factors**: Can reviewers quickly verify and correct outputs?

## Suggested evaluation tracks

1. **Offline replay**: deterministic runs over known cases.
2. **Perturbation tests**: missing docs, contradictory records, OCR noise.
3. **Adversarial tests**: prompt injection and provenance spoofing attempts.
4. **Workflow tests**: escalation frequency, review latency, override outcomes.

## Minimal scorecard

Use [`templates/eval-scorecard.md`](../templates/eval-scorecard.md) to record:

- task context
- data slice
- expected behaviour
- observed failure modes
- severity and mitigation notes
