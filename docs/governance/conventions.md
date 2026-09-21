# Process conventions: labels, status and versioning

Status: approved
Owner: platform engineering
Source: [EP00 — Governance and project foundations](../architecture/platform-engineering-lab-architecture-v0.1.md) (section 27), section 32

This document covers project-process conventions: issue/PR labels, decision status and versioning of the architecture document and of execution milestones. File and commit conventions live in [`CLAUDE.md`](../../CLAUDE.md) and are not repeated here.

## Labels

| Label | Meaning | Applied to |
|---|---|---|
| `p0` | Priority P0 (must happen for the lab to work) | issues/PRs tied to a P0 epic |
| `p1` | Priority P1 | issues/PRs tied to a P1 epic |
| `p2` | Priority P2 (evolution, out of the initial critical path) | issues/PRs tied to a P2 epic |
| `status:proposed` | Decision proposed, not yet approved | PRs changing the architecture document before owner approval |
| `status:approved` | Decision approved | merged PRs that changed an approved decision |
| `status:superseded` | Decision replaced by a later change | historical reference only |
| `status:archived` | Decision no longer applicable | historical reference only |
| `spike` | Feasibility spike (EP01) | spike issues/PRs |
| `evidence` | Evidence record for a run or spike | PRs adding files under `docs/evidence/` |
| `governance` | Governance/process change | PRs under `docs/governance/`, `.github/` |
| `epic:epNN` | Ties an issue/PR to a specific epic | created on demand, when that epic is first opened as an issue |

Only `epic:ep00` exists today. The remaining `epic:ep01`…`epic:ep15` labels are created when each epic is actually opened, to avoid unused labels for epics that may never happen (e.g. EP15, a P2 evolution).

## Status states

Mirrors section 32 of the architecture document. Every architectural decision is in exactly one of: `proposed`, `approved`, `superseded`, `archived`. A decision moves between states only through a PR with reason, alternatives considered, and impact analysis.

## Versioning

Two independent schemes, intentionally decoupled:

1. **Architecture document** — informal SemVer already in use (`v0.1`). A scope or decision change increments minor (`v0.2`, `v0.3`, ...); an editorial-only correction increments patch (`v0.1.1`); `v1.0` is reserved for the architecture becoming stable after EP13 (destroy proven).
2. **Execution milestones** — one Git tag per completed epic, named `epNN-complete` (e.g. `ep00-complete`). These tags track delivery progress and are independent of the document's own version number.

## Required checks — current gap

No CI exists yet in either repository. Branch protection on `main` therefore has an empty required-status-checks list for now. Each check listed in section 16.3 of the architecture document is added to branch protection only when it is actually implemented and evaluated (EP03 for Terraform checks, EP04 for Helm/GitOps checks, EP11 for the worker's build/security pipeline). This matches the "Enforcement" section of `CLAUDE.md`: no tool is wired in before an explicit, evaluated decision to adopt it.
