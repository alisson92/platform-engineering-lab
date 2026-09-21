# Evidence records

Status: approved
Owner: platform engineering
Source: [EP00 — Governance and project foundations](../architecture/platform-engineering-lab-architecture-v0.1.md) (section 27), section 23.3, EP01 acceptance criteria

## Purpose

Every spike or run that produces a decision-relevant result is recorded as one evidence file under this directory. This template is created in EP00; it starts being filled from EP01 onward, when the feasibility spikes begin.

## File naming

`docs/evidence/<yyyy-mm-dd>-<slug>.md`, kebab-case, e.g. `docs/evidence/2026-09-22-eks-endpoint-connectivity.md`.

## Template

```markdown
# <title>

Date: <yyyy-mm-dd>
Related epic: EPnn
Related architecture section: §nn

## Hypothesis

What we expected to be true or to work, and why.

## Procedure

Exact steps, commands or configuration used to test the hypothesis.

## Result

What actually happened. Include effective versions locked (technical lock, §34), observed cost vs. estimate, tested endpoints without exposing tokens, alerts received, and residual-resource audit, where applicable (§23.3).

## Evidence

Links, command output excerpts, or references to artifacts that support the result. No secrets, tokens or credentials.

## Decision

Accepted / requires a change to the architecture document / blocked. If it requires a change, open a PR against the architecture document per section 32.
```
