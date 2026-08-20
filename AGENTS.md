# OS Operating Guide

## Purpose

OS turns loosely captured ideas into completed, verifiable outcomes through a governed workflow. Treat this repository as the shared operating workspace for product definition, project context, reusable skills, tickets, evidence, and durable learning.

The product remains an exploring hypothesis. `docs/PRD.md` and `docs/SPEC.md` define the current product boundary; neither authorises application implementation.

## Source Of Truth

Read only the context required for the task:

1. `roadmap.md` for the current priority and exclusions.
2. The active file under `tickets/` for the approved outcome and finish line.
3. `review.md` for the quality standard.
4. `docs/PRD.md` and `docs/SPEC.md` when product behaviour or scope is involved.
5. `CONTEXT/PERSONAL_PROFILE.md` for stable personal and technical preferences.
6. The relevant profile under `CONTEXT/BRANDS/` for brand work.
7. `CONTEXT/MEMORY.md` only for confirmed durable decisions and proven patterns.
8. Relevant notes under `customers/` when customer evidence is required.
9. The named skill under `.agents/skills/` when the request matches it.

Do not load every file by default. Do not treat assumptions, generated copy, transcripts, or temporary task progress as confirmed memory or customer evidence.

## Instruction Precedence

When instructions conflict, follow this order:

1. Safety, security, privacy, and permission boundaries.
2. The explicitly approved execution plan.
3. The user's latest explicit instruction.
4. This operating guide.
5. The active ticket and `roadmap.md`.
6. `review.md`.
7. Product documents and retrieved context.
8. Skill defaults and agent recommendations.

A material conflict or scope change invalidates the prior approval and requires a revised plan.

## Operating Loop

1. **Inspect** — read the request, active ticket, roadmap, review standard, relevant context, and current repository state.
2. **Frame** — state the user, desired outcome, scope, exclusions, constraints, risks, and completion evidence.
3. **Ticket** — keep one task, one finish line, and one reviewable change.
4. **Plan** — explain the smallest complete approach before consequential work.
5. **Approve** — obtain explicit approval for state-changing, risky, costly, credential-sensitive, or externally consequential work.
6. **Execute** — make only the approved changes and preserve unrelated work.
7. **Verify** — run applicable tests, lint, type checks, builds, and user-facing flows. Never claim success without inspected evidence.
8. **Review** — assess the result against the ticket, roadmap, and `review.md`.
9. **Close** — report the outcome, evidence, limitations, human-review items, exact state, and affected files.
10. **Learn** — update durable context only when the learning is confirmed and the update is approved.

## Work States

Use precise states:

- `proposed`
- `awaiting-decision`
- `approved`
- `executing`
- `blocked`
- `failed`
- `implemented`
- `verified`
- `completed`

Generated output is not automatically verified or completed.

## Permission Boundaries

### Safe And Read-Only

May proceed when clearly requested:

- Inspect repository files and history.
- Analyse context and sources.
- Explain findings and propose plans.
- Recommend tests, tickets, routines, skills, connectors, and hooks.

### Approval Required

Obtain explicit approval before:

- Creating or editing files.
- Changing dependencies, lockfiles, migrations, authentication, payments, or permissions.
- Running state-changing commands.
- Changing Git state or publishing a branch or pull request.
- Activating schedules, routines, connectors, hooks, or external services.

Approval covers only the presented files, actions, risks, and acceptance criteria.

### Human-Owned

Do not perform without separate explicit authorisation and an environment that permits it:

- Production deployment or merge.
- Destructive data operations.
- Live billing or customer-data decisions.
- Credential sharing.
- Security-policy changes.

## Ticket Rules

Every consequential implementation starts from a ticket based on `tickets/TEMPLATE.md`. Split work when it has more than one independently valuable outcome, an unclear finish line, or a diff too large to review confidently.

## Customer Evidence

Store real interviews, support notes, objections, observed behaviour, or supplied analytics under `customers/`. Record provenance and distinguish direct statements from summaries and interpretations. Never invent customer evidence.

## Skills, Routines, Connectors, And Hooks

- Turn a repeated, stable workflow into a skill only after the process has been used successfully.
- Define routines under `routines/` before activation. Start with read-only or documentation output.
- Add connectors only when they provide necessary context or capability.
- Use hooks for deterministic safeguards such as formatting after edits or checks before a pull-request summary.
- Do not install, enable, schedule, or publish any of these without approval.
- Use parallel agents or worktrees only when requested, tasks are independent, and file ownership does not overlap.

## Repository Areas

- `CONTEXT/` — stable personal, brand, and confirmed memory.
- `customers/` — sourced customer evidence.
- `docs/` — product requirements and specifications.
- `tickets/` — scoped work and completion contracts.
- `demos/` — demo flows, scripts, screenshots, and evidence.
- `routines/` — inactive routine definitions and runbooks.
- `.agents/skills/` — reusable agent workflows.
- `_output/` — generated deliverables.
- `summary/` — concise project handoff state.

## Completion Report

Report checks as `Passed`, `Failed`, or `Not run`, including the command or inspection and relevant result. Classify review findings as `Must fix`, `Should fix`, or `Okay to ship`. Clearly separate implemented, verified, committed, pushed, merged, and deployed states.
