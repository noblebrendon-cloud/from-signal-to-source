# From Signal to Source

**A repeatable agent workflow for turning live conversations into research-grounded articles.**

From Signal to Source is an open, versioned methodology/specification for moving an emergent idea from a live conversation or observation through research, adversarial review, theory refinement, publication, and distribution without collapsing uncertainty or giving downstream agents more authority than the workflow grants them.

## Pipeline

`Capture → Thesis → Deep Research → Challenge → Refine → Draft → Publish → Distribute`

The workflow is organized into eight bounded agent roles:

1. Signal Miner
2. Thesis Architect
3. Research Director
4. Evidence Auditor
5. Theory Refiner
6. Article Builder
7. Publication Architect
8. Distribution Agent

Each stage proposes a next state rather than silently assuming authority to perform every downstream action.

## What is included

- Human-readable workflow specification in PDF and DOCX
- Master orchestration prompt
- Stage-specific executable prompts
- Machine-readable stage-envelope JSON Schema
- Worked example showing the method applied to an article-development process
- Citation metadata for GitHub and Zenodo
- Version history and release notes

## Core operating rules

- Do not jump from raw signal to a final article when factual substantiation is required.
- Preserve uncertainty and disagreement across stages.
- Separate observation, inference, established evidence, contested interpretation, synthesis, and proposed framework terms.
- Include disconfirmation paths, strong counterarguments, and legitimate exceptions during research.
- Audit source quality and claim fit before theory refinement.
- Let evidence change the theory and record what changed.
- Use cross-domain examples to show structural recurrence without implying false equivalence.
- Inspect the existing publication environment before deciding placement.
- Distribution copy must never make a stronger claim than the canonical article.
- Every stage ends with `STATUS`, `ARTIFACT`, `UNCERTAINTIES`, `GATE CHECK`, and `NEXT AUTHORIZED STAGE`.
- If a gate fails, repair the current stage instead of advancing.

## Stage contract

A stage output should conform conceptually to:

```json
{
  "stage": "01-signal-miner",
  "status": "pass | repair | blocked",
  "artifact": {},
  "uncertainties": [],
  "gate_check": {
    "passed": true,
    "notes": []
  },
  "next_authorized_stage": "02-thesis-architect"
}
```

A formal JSON Schema is provided in `schemas/stage-envelope.schema.json`.

## Validation boundary

This repository publishes a reusable methodology and prompt specification. It is **not** a claim of peer review, universal applicability, or independent validation. Each release should distinguish:

- established source-backed claims,
- contested claims,
- author synthesis,
- proposed framework terms,
- and implementation choices.

The methodology is designed to make those boundaries inspectable rather than erase them.

## Reuse

The documentation, prompts, schemas, and examples in this repository are released under **CC BY 4.0**. You may use, adapt, and redistribute them with attribution. If future versions add standalone software code, that code may be licensed separately.

## Citation

GitHub can render citation information from `CITATION.cff`. Zenodo-specific release metadata is supplied in `.zenodo.json`.

Suggested citation before DOI assignment:

> Coleman, Brendon R. (2026). *From Signal to Source: A Repeatable Agent Workflow for Turning Live Conversations into Research-Grounded Articles* (Version 1.0.0).

Once a Zenodo DOI is minted, cite the DOI-backed release instead.

## Version

Current prepared release: **v1.0.0**

See `CHANGELOG.md` for release history.
