# Repository structure

Status: approved
Owner: platform engineering
Source: [EP00 — Governance and project foundations](../architecture/platform-engineering-lab-architecture-v0.1.md) (section 27), section 16.1

## Purpose

This document registers the target directory structure for the two repositories described in section 16.1 of the architecture document. It records the decision ahead of time so each future epic knows where its output belongs. Directories are created by the epic that first populates them with real content, not in advance as empty placeholders.

## `platform-engineering-lab`

| Path | Purpose | Populated by |
|---|---|---|
| `docs/architecture/` | Approved architecture and backlog document | already exists |
| `docs/governance/` | Process conventions, repository structure, this document | EP00 |
| `docs/references/` | Official sources matrix | EP00 |
| `docs/evidence/` | Evidence records per spike/run | EP00 (template), EP01+ (content) |
| `.github/` | CODEOWNERS, PR/issue templates, workflows | EP00 (governance files), EP03+ (workflows) |
| `terraform/` | IaC modules and environments | EP03 |
| `gitops/` | Argo CD manifests, app-of-apps | EP04 |
| `helm/` | Chart values/overrides per component and tenant | EP05, EP08, EP09 |
| `policies/` | Policy as Code (Kyverno) | EP06 |
| `dashboards/` | Dashboards and alerts | EP07, EP10 |
| `tests/` | Automated tests across the test pyramid (section 23) | progressive, per epic |

## `camunda-sample-worker`

| Path | Purpose | Populated by |
|---|---|---|
| `bpmn/` | Sample BPMN process | EP11 |
| `worker/` | Instrumented worker code | EP11 |
| `tests/` | Unit and contract tests | EP11 |
| `.github/workflows/` | Build, SBOM and security pipeline (section 16.3) | EP11 |
| `docs/` | Worker-specific documentation | as needed |

## Notes

- This structure follows the naming conventions in [`CLAUDE.md`](../../CLAUDE.md) (English, kebab-case, documented exceptions).
- Changes to this structure follow the same governance as any other architectural decision: PR, reason, impact, approval (see section 32 of the architecture document).
