---
id: TICKET-001
title: Establish the OS operating backbone
status: implemented
owner: Kofi
created: 2026-08-20
---

# Goal

Give agents a consistent, repository-backed process for planning, executing, verifying, reviewing, and reporting OS work.

# User

Kofi needs OS work to move from an incomplete request to a reviewable outcome without losing context, exceeding authority, or confusing generated output with verified completion.

# Scope

- Expand `AGENTS.md`.
- Add `roadmap.md` and `review.md`.
- Add ticket guidance and a reusable ticket template.
- Add customer-note guidance and a reusable note template.
- Add demo guidance.
- Add inactive routine guidance and a reusable routine template.
- Update the project summary.

# Exclusions

- Application code or architecture.
- Changes to existing product documents, context, skills, or outputs.
- Dependencies, connectors, hooks, schedules, publishing, deployment, pull requests, or merge.

# Experience

An agent entering the repository can identify the current priority, load only relevant context, frame one ticket, respect approval boundaries, verify the result, review it consistently, and report the exact final state.

# Constraints

- Preserve the exploring product state defined in `docs/PRD.md` and `docs/SPEC.md`.
- Keep OS standalone from Hibachi.
- Do not present assumptions as customer evidence.
- Do not activate routines.
- Work on `feat/operating-backbone`, not `main`.

# Acceptance Criteria

- [x] The operating guide defines context, workflow, states, permissions, and completion reporting.
- [x] The roadmap defines the current goal, ordered priorities, exclusions, and advancement evidence.
- [x] The review guide defines layered checks and severity classifications.
- [x] Reusable ticket and customer-note templates exist.
- [x] Demo and routine areas define their purpose and boundaries.
- [x] Existing product docs, context, skills, and outputs are unchanged.

# Verification

- Re-fetch every changed file from GitHub.
- Compare `feat/operating-backbone` with `main`.
- Confirm the diff contains only approved files.
- Inspect terminology and links against the current PRD and specification.
- Automated tests and browser verification are not applicable to documentation-only work.

# Risks And Assumptions

- This backbone has not yet been validated through a complete OS workflow.
- The first recommended validation target is the existing TikTok content workflow.

# Human Review

- Decide whether to open or merge a pull request.
- Approve any future routine activation, connector, hook, dependency, or application implementation.

# Completion Evidence

The feature-branch commit and GitHub comparison are the authoritative implementation evidence. Verification results must be reported after the commit is created and inspected.
