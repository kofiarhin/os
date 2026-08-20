# OS Review Standard

## Purpose

Use this file to judge work before it is described as complete. Review the active ticket first, then the current roadmap, product documents, relevant context, and resulting diff or output.

## Review Outcome

Classify every material finding as:

- **Must fix** — blocks the ticket, violates scope or permissions, creates material risk, or lacks required verification.
- **Should fix** — important quality issue that does not block the stated outcome.
- **Okay to ship** — verified, within scope, and acceptable for the current product state.

Do not use `Okay to ship` to imply merged, deployed, published, or released.

## Layer 1: Ticket And Scope

- Does the result achieve the ticket's single outcome?
- Are all acceptance criteria evaluated?
- Does the diff contain only approved files and behaviour?
- Were exclusions and unrelated user changes preserved?
- Did a material change reopen planning and approval?

## Layer 2: Product Direction

- Does the work match `roadmap.md`, `docs/PRD.md`, and `docs/SPEC.md`?
- Are hypotheses, recommendations, confirmed facts, and customer evidence distinguishable?
- Is the solution the smallest complete vertical slice?
- Does it avoid premature architecture, abstraction, dependencies, or services?

## Layer 3: User Experience

For user-facing work:

- Can the intended user understand the value and next action?
- Are loading, empty, error, success, and recovery states handled?
- Is the primary flow keyboard-operable and understandable without colour alone?
- Was the actual flow inspected at desktop and mobile widths?
- Were browser console and network errors checked?
- Does copy use sourced customer language when such evidence exists?

If no user-facing application exists, mark browser checks `Not run` with the reason.

## Layer 4: Engineering Quality

When code is involved:

- Follow the existing stack and repository conventions.
- Keep API logic out of React components.
- Use TanStack Query for server state and Redux Toolkit only for necessary global client state.
- Use Vitest for frontend tests and Jest for backend tests unless the project already establishes another standard.
- Keep secrets in `.env` and provide a safe `.env.example` when needed.
- Check tests, lint, type checks, production build, and relevant browser flows.
- Never report a check as passed unless it was run and inspected.

## Layer 5: Safety And Evidence

- Did work remain inside the approved permissions and destinations?
- Are secrets, private data, and customer information protected?
- Are proposed, approved, implemented, verified, committed, pushed, merged, and deployed states reported precisely?
- Is completion supported by observable evidence?
- Are limitations and human-review items explicit?
- Were state-changing failures prevented from silently retrying?

## Content Workflow Checks

For TikTok or Instagram work:

- Was the correct brand context loaded?
- Are claims supported by supplied facts or visible evidence?
- Is the hook specific and platform-appropriate?
- Is the output complete according to the selected skill?
- Is the saved path correct and non-overwriting?
- Is UK English used unless the audience requires otherwise?
- Are invented results, clients, statistics, testimonials, and experiences absent?
- Does the final report distinguish generated content from published content?

## Final Review Format

```markdown
## Must fix
- Finding or "None".

## Should fix
- Finding or "None".

## Okay to ship
- Verified strengths and scope notes.

## Verification
- Passed — check and result.
- Failed — check and result.
- Not run — check and reason.

## Human review
- Remaining judgement or "None".
```
