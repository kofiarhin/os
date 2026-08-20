# Routines

Routines define recurring work before it is scheduled or activated. Every routine is inactive by default.

## Requirements

A routine must state:

- Trigger and cadence.
- Inputs and source-of-truth files.
- Output path and format.
- Permission level.
- Actions it may and may not perform.
- Verification and human-review requirements.
- Failure, retry, and duplicate-run behaviour.
- Owner and activation status.

## Safety Defaults

- Start with read-only analysis or documentation output.
- Do not publish, deploy, merge, message people, change customer data, or modify production systems.
- Do not activate a schedule without explicit approval.
- Never automatically retry a state-changing failure.
- If required context is missing, stop and report the blocker.
- If a material assumption or permission is unresolved, create a decision request rather than proceeding.
- Keep outputs reviewable and preserve source provenance.

Use `TEMPLATE.md` to propose a routine. Proposal does not equal activation.
