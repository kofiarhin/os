# OS Product and Functional Specification

*Detailed behavioural definition for the OS product hypothesis*

| Field | Value |
|---|---|
| Version | Draft v0.1 |
| Date | 11 August 2026 |
| Owner / first-user hypothesis | Kofi |
| Lifecycle | Exploring |
| Product boundary | Standalone product; not part of Hibachi |
| Source | docs/PRD.md v0.1 |
| Decision state | Product hypothesis; not validated or approved for implementation |

> This specification defines product behaviour, workflows, states, permissions, failure handling, conceptual information, acceptance criteria, and validation scenarios. It deliberately does not select architecture, APIs, database schemas, technology stack, hosting, repository structure, or an implementation plan.

## 1. Purpose

This document turns the OS PRD into a testable product and functional specification. It is intended to:

- make the proposed user experience and system behaviour precise enough to review;
- preserve the distinction between confirmed direction, locked hypotheses, and open decisions;
- define observable requirements and acceptance scenarios;
- expose unresolved product questions before technical design begins.

This document does not authorize implementation. Requirements remain hypotheses until approved after discovery or prototype evidence.

## 2. Product definition

### 2.1 Locked primary problem hypothesis

OS helps Kofi turn loosely captured ideas into completed, verifiable outcomes by coordinating context, decisions, reusable workflows, AI agents, and execution tools within one governed process.

### 2.2 Intended outcome

A user can move one meaningful piece of work from an incomplete starting point to a verified end state without repeatedly reconstructing context, manually transferring decisions between tools, or confusing generated output with completed work.

### 2.3 Product boundary

OS is:

- a standalone product;
- an outcome-coordination layer spanning intent, knowledge, decisions, reusable processes, capabilities, execution state, and evidence;
- designed to keep consequential work inspectable and governed;
- intended to use the lightest workflow appropriate to the work.

OS is not currently defined as:

- part of, dependent on, or a replacement for Hibachi;
- a general-purpose autonomous agent;
- a foundation model;
- a marketplace;
- a team collaboration or enterprise administration product;
- a replacement for every chat, knowledge, project-management, or automation tool.

## 3. Status vocabulary

OS must use precise state language. The following terms are not interchangeable.

| Term | Meaning |
|---|---|
| Proposed | Suggested but not accepted or authorized. |
| Awaiting decision | Blocked until the user resolves a material question. |
| Planned | The intended actions and checks are described but not authorized. |
| Approved | The user has authorized the exact current outcome contract. |
| Executing | At least one authorized action is actively running. |
| Paused | Work is intentionally suspended with resumable state preserved. |
| Blocked | Progress cannot continue without resolving a dependency or decision. |
| Failed | An attempted action or required check did not succeed. |
| Verified | Required evidence supports the claimed result. |
| Completed | The outcome contract is satisfied and required evidence is present. |
| Cancelled | The user or system intentionally stopped the work. |
| Superseded | A newer decision, contract, or version replaced this item. |

A work item must never be marked completed solely because text, code, a document, or another artifact was generated.

## 4. Users and roles

### 4.1 MVP user hypothesis

The first-user hypothesis is Kofi operating across technical, creative, and operational projects.

### 4.2 Product roles

These roles describe product responsibilities, not an authentication or access-control implementation.

| Role | Responsibility |
|---|---|
| User | Supplies intent, corrects context, makes decisions, grants authority, and accepts or rejects outcomes. |
| OS | Frames work, selects relevant context, coordinates approved capabilities, tracks state, and presents evidence. |
| Agent capability | Performs reasoning, synthesis, generation, diagnosis, or other delegated cognitive work. |
| Tool capability | Performs an observable action against a defined target within granted authority. |
| Verifier | Produces or evaluates evidence against the outcome contract. It may be the user, OS, a tool, or an external source. |

The same underlying capability may play more than one role, but each action must retain its declared purpose and authority.

## 5. Core concepts

These concepts are product-level definitions only.

| Concept | Required meaning |
|---|---|
| Project | A bounded collection of intent, context, decisions, work, outcomes, and lessons. |
| Intake | The original user-supplied thought, request, goal, reference, or material. |
| Work item | One unit of work progressing through framing, planning, execution, verification, and closure. |
| Outcome contract | The inspectable agreement defining result, scope, authority, risks, actions, and completion evidence. |
| Context item | A fact, document, preference, decision, reference, or source-derived idea available to work. |
| Decision | A resolved choice with status, rationale, provenance, and scope. |
| Assumption | An unverified proposition used provisionally and kept visibly distinct from fact. |
| Skill | A named, inspectable, reusable process with inputs, constraints, expected outputs, and a version. |
| Capability | An agent or tool action OS may invoke within explicit boundaries. |
| Action | One observable attempted capability invocation with target, state, result, and evidence. |
| Evidence | A check, artifact, observation, or external status supporting or refuting an outcome claim. |
| Outcome record | The final state, result, evidence, unresolved items, decisions, and lessons for a work item. |
| Lesson | A correction or reusable insight retained after work. |

## 6. End-to-end workflow

### 6.1 Stage 1 — Capture

Goal: accept incomplete intent with minimal friction.

Required behaviour:

1. The user can create a work item from plain language.
2. The user can add references or supporting material.
3. OS preserves the original intake unchanged as provenance.
4. OS may suggest a concise title and project association.
5. OS must not require the user to complete a large structured form before capture.
6. If the project is uncertain, OS may leave it unassigned or ask only when the choice materially affects handling.

Exit condition: the original intent and available references are preserved in a work item.

### 6.2 Stage 2 — Frame

Goal: establish what outcome is sought and what remains uncertain.

Required behaviour:

1. OS identifies the desired result, known constraints, affected destinations, risks, dependencies, and proposed completion evidence.
2. OS separates confirmed information, retrieved evidence, assumptions, recommendations, source-derived ideas, and decisions.
3. OS resolves information from available evidence before asking the user.
4. When a material choice remains, OS asks one decision at a time and supplies a recommended answer with its consequence.
5. Non-material uncertainty may remain explicitly labelled.
6. The user can correct any framing item.

Exit condition: the work has a sufficiently clear intended outcome, or is explicitly blocked on a material decision.

### 6.3 Stage 3 — Assemble context

Goal: use only context relevant to the work.

Required behaviour:

1. OS selects context based on the work item, project boundary, and requested outcome.
2. Selected context is inspectable before consequential execution.
3. Each context item retains provenance, scope, and freshness information where available.
4. The user can remove, correct, or add context.
5. Conflicts between sources are surfaced when they materially affect the result.
6. OS must not silently convert an assumption or source-derived idea into a confirmed fact.
7. Irrelevant context must not be included merely because it is available.

Exit condition: the relevant context set is explicit enough to support planning.

### 6.4 Stage 4 — Plan and govern

Goal: make consequential execution understandable and authorized.

Required behaviour:

1. OS produces an outcome contract proportional to the task.
2. The contract identifies:
   - goal and intended result;
   - confirmed information and assumptions;
   - in-scope and out-of-scope work;
   - proposed actions and exact destinations;
   - permissions and approval gates;
   - dependencies and risks;
   - completion evidence and verification method;
   - failure, cancellation, and recovery behaviour.
3. Low-risk, reversible, read-only work may proceed without a heavyweight contract.
4. Consequential, destructive, costly, security-sensitive, externally visible, or multi-step work requires explicit approval.
5. Approval applies only to the presented contract version.
6. A material change invalidates approval and returns the work to framing or planning.
7. Silence, inactivity, or an unrelated affirmative response must not be treated as approval.

Exit condition: the work is approved, remains read-only and permitted to proceed, or is blocked.

### 6.5 Stage 5 — Coordinate execution

Goal: perform only authorized actions and expose progress.

Required behaviour:

1. OS chooses an eligible capability for each action without changing the agreed outcome.
2. Before invocation, OS validates the action, target, scope, and required authority.
3. Each action receives only the context and permission required for its purpose.
4. The user can see:
   - current workflow stage;
   - active capability;
   - current action and target;
   - latest result, warning, or blocker;
   - remaining planned actions.
5. OS records action transitions and results.
6. Failed state-changing actions must not be silently retried.
7. A capability request outside the approved contract is blocked and requires a revised contract.
8. The user can request cancellation or pause where the capability supports it.

Exit condition: all planned actions finish, a blocker or failure stops progress, or the work is cancelled.

### 6.6 Stage 6 — Verify

Goal: determine whether the intended outcome was achieved.

Required behaviour:

1. OS evaluates the result against the completion evidence defined in the outcome contract.
2. Evidence is linked to the requirement or claim it supports.
3. Passing, failing, missing, stale, and inconclusive evidence remain distinguishable.
4. OS must not claim checks ran unless it has direct evidence that they ran.
5. Failed required evidence blocks verified and completed states.
6. Where verification requires user judgement, OS presents the artifact and a specific acceptance question.
7. An authorized exception must identify the failed or omitted check and the residual risk.

Exit condition: the work is verified, failed, blocked on evidence, or explicitly accepted with a documented exception.

### 6.7 Stage 7 — Close and learn

Goal: preserve the result and make the next state clear.

Required behaviour:

1. OS presents an outcome record containing:
   - intended outcome;
   - exact final state;
   - completed and incomplete actions;
   - verification evidence;
   - unresolved items;
   - material decisions;
   - changed destinations or artifacts;
   - recommended next action, if one exists.
2. Completed is available only when all mandatory contract conditions are satisfied.
3. The user may reject the outcome and reopen framing.
4. Useful lessons may be promoted to project context or a reusable skill.
5. Promotion must preserve provenance and must not overwrite confirmed knowledge silently.

Exit condition: the work is completed, cancelled, failed, or remains explicitly open.

## 7. Work-item state model

### 7.1 Permitted primary transitions

| From | To | Trigger |
|---|---|---|
| Proposed | Awaiting decision | A material ambiguity is identified. |
| Proposed | Planned | Framing is sufficient. |
| Proposed | Executing | Work is low-risk, permitted, and requires no governed approval. |
| Awaiting decision | Proposed | The user answers and framing resumes. |
| Planned | Approved | The user explicitly approves the exact contract. |
| Approved | Executing | Pre-execution validation passes. |
| Approved | Planned | A material contract change invalidates approval. |
| Executing | Paused | The user or system safely pauses. |
| Paused | Executing | State and authority are revalidated. |
| Executing | Blocked | A dependency, permission, or decision prevents progress. |
| Executing | Failed | An action fails and no safe continuation exists. |
| Executing | Verified | Required actions and evidence succeed. |
| Blocked | Proposed | The blocker changes scope or requires reframing. |
| Blocked | Executing | The blocker is resolved without material contract change. |
| Failed | Proposed | A revised approach requires reframing. |
| Verified | Completed | The outcome contract is satisfied and closure is recorded. |
| Any non-terminal state | Cancelled | The user cancels or a defined cancellation rule applies. |

### 7.2 State invariants

- Only one primary state is current for a work item.
- State transitions retain actor, time, reason, and supporting evidence.
- Approved requires a specific outcome-contract version.
- Executing requires valid authority for the next action.
- Verified requires all mandatory evidence to pass or a documented authorized exception.
- Completed requires verified status and a final outcome record.
- Cancelled, failed, and completed are terminal for that run; continuation creates a new run or explicitly reopens the work item.
- A child action failure does not automatically mean the whole work item failed; the outcome contract determines whether safe alternative work may continue.

## 8. Intake and provenance requirements

| ID | Requirement |
|---|---|
| INT-01 | Preserve the original intake and its creation time. |
| INT-02 | Allow later clarification without rewriting the original intake. |
| INT-03 | Identify the source of every material context item. |
| INT-04 | Label user statement, retrieved fact, assumption, recommendation, decision, and source-derived idea distinctly. |
| INT-05 | Record when an item is corrected or superseded and retain the relationship to the prior item. |
| INT-06 | Surface material conflicts instead of choosing silently. |
| INT-07 | Permit uncertain information to remain unresolved when it does not block safe progress. |

## 9. Project-context requirements

| ID | Requirement |
|---|---|
| CTX-01 | Keep project contexts separate by default. |
| CTX-02 | Show which project and work item are active. |
| CTX-03 | Scope retrieval to the active project unless cross-project use is explicit. |
| CTX-04 | Allow user-level preferences to be distinguished from project-specific decisions. |
| CTX-05 | Allow the user to inspect the context selected for a run. |
| CTX-06 | Allow correction, exclusion, and addition before consequential execution. |
| CTX-07 | Identify stale or conflicting context when known. |
| CTX-08 | Export core context, decisions, work history, and outcomes in a portable, inspectable form. |
| CTX-09 | Never treat conversational recall alone as authoritative when a designated durable source conflicts. |

## 10. Decision requirements

| ID | Requirement |
|---|---|
| DEC-01 | Ask the user only when evidence cannot resolve a material choice. |
| DEC-02 | Ask one material decision per interaction when governed clarification is required. |
| DEC-03 | Present the decision, recommendation, rationale, and one clear question. |
| DEC-04 | Record the selected answer, scope, rationale, and provenance. |
| DEC-05 | Distinguish a locked product hypothesis from a validated fact. |
| DEC-06 | Permit a decision to be superseded without erasing history. |
| DEC-07 | Reopen approval when a changed decision materially changes scope, risk, cost, destination, or acceptance criteria. |

## 11. Skills requirements

A skill is a reusable process, not an autonomous identity.

| ID | Requirement |
|---|---|
| SKL-01 | A skill has a stable name, purpose, version, inputs, constraints, expected outputs, and completion conditions. |
| SKL-02 | The user can inspect the skill definition used for a run. |
| SKL-03 | Each run records the exact skill version. |
| SKL-04 | Changes create a new version or an explicit superseding record. |
| SKL-05 | A skill may compose other skills while preserving the full execution trace. |
| SKL-06 | A skill may declare required capabilities and permissions but cannot grant those permissions itself. |
| SKL-07 | A skill must fail clearly when required inputs or capabilities are unavailable. |
| SKL-08 | A lesson may be proposed as a skill change but does not become active silently. |
| SKL-09 | Ownership, sharing, testing, synchronization, and retirement policies remain open product decisions. |

## 12. Capability and action requirements

| ID | Requirement |
|---|---|
| CAP-01 | A capability declares the actions and target types it can perform. |
| CAP-02 | OS checks eligibility and authority before each invocation. |
| CAP-03 | A capability receives the minimum context and permission required. |
| CAP-04 | Each action records capability, purpose, target, start state, result, and final state. |
| CAP-05 | Read-only and state-changing actions are distinguishable. |
| CAP-06 | A denied action fails closed and explains the violated boundary. |
| CAP-07 | Capabilities must not silently broaden scope or select a new destination. |
| CAP-08 | Provider-specific details remain behind the product concept of a replaceable capability. |
| CAP-09 | Capability unavailability produces a blocker and possible alternatives, not a false success. |
| CAP-10 | Raw activity may be shown, but OS acts only on results that satisfy the expected product contract. |

## 13. Authority and approval model

### 13.1 Risk classes

These classes define product behaviour and do not prescribe an implementation.

| Class | Examples | Default handling |
|---|---|---|
| Informational | Questions, summaries, explanations | Proceed directly. |
| Read-only operational | Inspecting project state or public evidence | Proceed when access is authorized; expose sources. |
| Reversible low impact | Drafting or temporary local work | Proceed or request lightweight confirmation based on context. |
| Consequential | Repository writes, external messages, purchases, publishing, persistent changes | Require an explicit outcome contract and approval. |
| High risk | Destructive, security-sensitive, credential-sensitive, production, migration, or material-cost actions | Require explicit approval plus action-specific safeguards; some actions may remain unsupported. |

### 13.2 Approval rules

- Approval must identify the contract version and actor.
- Approval scope includes only listed actions, targets, boundaries, and exceptions.
- Approval expires when a material fact, plan, destination, dependency, risk, cost, or acceptance criterion changes.
- Approval does not imply permission to merge, deploy, publish, delete, purchase, or message externally unless explicitly included.
- OS must validate authority immediately before each consequential action.
- A skill, agent, or tool cannot approve its own expanded scope.

## 14. Failure, interruption, and recovery

### 14.1 Failure categories

| Category | Required response |
|---|---|
| Invalid input | Explain the missing or invalid field and preserve the work item. |
| Missing context | Request or retrieve only what is necessary; do not invent it. |
| Permission denied | Stop the affected action, identify the boundary, and preserve prior results. |
| Capability unavailable | Mark blocked, show impact, and offer eligible alternatives if known. |
| Transient read-only failure | A bounded retry may be proposed or attempted if it has no consequential effect. |
| State-changing action failure | Do not silently retry; revalidate current state before another attempt. |
| Verification failure | Mark evidence failed and block completion. |
| Partial completion | Show completed and incomplete actions separately; do not claim full completion. |
| Lost connection or interruption | Preserve known state and require revalidation before resuming consequential work. |
| Invalid capability result | Reject the result for action purposes and surface the error or retry policy. |
| Scope violation | Block the action, invalidate approval when material, and return to planning. |

### 14.2 Recovery requirements

- Recovery must begin from the last confirmed state, not an assumed state.
- OS must detect when external state may have changed during interruption.
- Resumption of consequential work requires the outcome contract, project, target, authority, and prior action state to remain valid.
- If validity cannot be established, the work returns to planned or awaiting-decision state.
- Cancellation must stop future actions and attempt safe cancellation of active actions without claiming rollback unless rollback is verified.
- Existing completed external actions remain part of the outcome record even if later steps fail.

## 15. Verification specification

### 15.1 Evidence properties

Every required evidence item should identify:

- the outcome condition or claim it supports;
- the producing actor or capability;
- collection time;
- status: pending, passed, failed, missing, stale, or inconclusive;
- artifact or source reference when available;
- any limitation or authorized exception.

### 15.2 Verification rules

| ID | Requirement |
|---|---|
| VER-01 | Completion evidence is defined before consequential execution. |
| VER-02 | Verification is proportional to outcome risk and type. |
| VER-03 | OS reports only checks supported by direct evidence. |
| VER-04 | Required failed or missing evidence blocks completion. |
| VER-05 | Human acceptance is explicit where subjective judgement is required. |
| VER-06 | Evidence from the same capability that produced the output is identified as such; independent verification may be required by the contract. |
| VER-07 | Stale evidence cannot prove a later changed state. |
| VER-08 | An exception records who authorized it, why, and the remaining risk. |
| VER-09 | The final outcome record links claims to supporting evidence. |

## 16. Outcome-record requirements

An outcome record must include:

1. original intent;
2. agreed outcome and completion conditions;
3. exact final work-item state;
4. contract version and approval state;
5. actions attempted, completed, failed, skipped, or cancelled;
6. changed artifacts and destinations;
7. verification evidence and limitations;
8. unresolved decisions, blockers, or residual risks;
9. lessons proposed or retained;
10. a recommended next action only when useful.

OS must not use success language that exceeds the evidence. For example, committed, verified, merged, deployed, published, delivered, and completed remain separate facts.

## 17. User-control requirements

| ID | Requirement |
|---|---|
| UCR-01 | The user can inspect and correct framing before approval. |
| UCR-02 | The user can inspect selected context and provenance. |
| UCR-03 | The user can approve, reject, revise, pause, resume, or cancel applicable work. |
| UCR-04 | The user can see current state and the next blocked decision. |
| UCR-05 | The user can inspect actions, targets, results, and evidence. |
| UCR-06 | The user can export core project and outcome records. |
| UCR-07 | The user can distinguish recommendations from decisions. |
| UCR-08 | The user is warned when a requested action is unsupported or exceeds current authority. |

## 18. Product quality requirements

### 18.1 Transparency

- Consequential work exposes basis, context, plan, actions, and evidence.
- Material state changes are attributable.
- The user can reconstruct why OS reached the current state.

### 18.2 Safety

- Unapproved or out-of-scope actions fail closed.
- Least authority and minimum necessary context are the default.
- State-changing retries require revalidation.
- Product language never implies unsupported completion.

### 18.3 Recoverability

- Interrupted work retains useful state.
- Resumption validates external state and authority.
- Failure preserves evidence and partial results.

### 18.4 Responsiveness

- Capture and informational work should feel immediate.
- Governance overhead is proportional to consequence and uncertainty.
- Simple read-only tasks must not be forced through the full seven-stage workflow.

Exact performance thresholds remain open pending prototype evidence.

### 18.5 Accessibility

The critical workflow must be keyboard-operable, use visible text in addition to colour for states, provide understandable labels, and expose errors next to the affected decision or action. Formal accessibility conformance targets remain an open decision.

### 18.6 Privacy

- Only relevant context is supplied to a run.
- Context and authority are inspectable.
- Sensitive values are not exposed in ordinary transcripts or outcome records.
- Retention, deletion, encryption, regional storage, and compliance policies remain open decisions.

## 19. Acceptance scenarios

The following scenarios are product-level tests. They do not define a testing framework.

### AS-01: Capture an incomplete idea

Given the user provides a short, incomplete thought  
When OS captures it  
Then the original wording is preserved  
And a work item is created without requiring a complete structured brief  
And any suggested title or project is labelled as a recommendation.

### AS-02: Separate facts and assumptions

Given intake and reference material contain confirmed and uncertain claims  
When OS frames the work  
Then each material claim is labelled by provenance and certainty  
And no assumption is presented as fact.

### AS-03: Ask one material question

Given available evidence cannot resolve a choice that materially changes scope  
When OS requires clarification  
Then it presents one decision, a recommended answer, the consequence, and one question  
And execution remains blocked until resolved.

### AS-04: Bypass heavyweight governance

Given the user asks a simple read-only question  
When OS can answer from authorized context  
Then it proceeds without requiring an outcome contract or execution approval  
And cites or identifies the basis when operational facts matter.

### AS-05: Approve consequential work

Given a consequential action is planned  
When OS seeks approval  
Then the user can inspect outcome, scope, targets, actions, risks, and verification  
And approval is bound to that exact contract version.

### AS-06: Reject scope expansion

Given a contract is approved  
When a capability proposes an unlisted target or material action  
Then OS blocks the action  
And invalidates approval when the change is material  
And returns the work to planning.

### AS-07: Preserve exact operational state

Given an action produces an artifact but verification has not run  
When OS reports progress  
Then it reports the artifact as produced  
And does not label the work verified or completed.

### AS-08: Block false completion

Given a mandatory verification check fails  
When OS evaluates the outcome  
Then the evidence is marked failed  
And the work cannot enter verified or completed state  
And the outcome record identifies the failure.

### AS-09: Handle partial failure

Given two authorized actions succeed and a third fails  
When execution stops  
Then successful actions remain recorded  
And the failed action and remaining actions are distinguished  
And OS does not claim rollback or full completion without evidence.

### AS-10: Resume safely

Given consequential work is interrupted  
When the user requests resume  
Then OS revalidates the active project, contract, target state, and authority  
And resumes only if no material mismatch exists  
Otherwise it returns to planning or awaits a decision.

### AS-11: Reuse a skill

Given a named skill has a recorded version and required inputs  
When OS runs it on two eligible work items  
Then both runs record the exact version, inputs, actions, and results  
And failures remain attributable to the relevant run.

### AS-12: Correct project context

Given the user identifies stale or incorrect context  
When they correct it  
Then the correction is used for future work  
And the prior item is retained as corrected or superseded  
And dependent approved work is revalidated.

### AS-13: Close with evidence

Given all mandatory actions and checks pass  
When OS closes the work  
Then the outcome record contains the result, evidence, changed artifacts, decisions, unresolved items, and exact completed state.

### AS-14: Preserve standalone boundary

Given OS work references Hibachi or another project as evidence or an example  
When context is assembled  
Then the source project remains a reference  
And no dependency, product boundary, or requirement is inferred without an explicit decision.

## 20. MVP product-completeness hypothesis

A future MVP is product-complete only when representative testing demonstrates:

- incomplete intent can become a clear outcome contract without excessive form filling;
- context is relevant, inspectable, correctable, and provenance-aware;
- one reusable skill succeeds across at least two eligible work items;
- consequential execution respects explicit scope and authority;
- a material change invalidates prior approval;
- actions and states remain visible and precise;
- required evidence blocks unsupported completion claims;
- one end-to-end work item reaches verified completion;
- an interrupted or failed run preserves truthful, recoverable state;
- simple informational work avoids unnecessary governance;
- the user can export and inspect the core project and outcome record;
- OS remains standalone from Hibachi.

Exact quantitative thresholds remain open until baseline discovery produces credible measures.

## 21. Validation scenarios before technical design

Before architecture or stack selection, validate the specification through three real concierge workflows:

1. one technical outcome;
2. one creative outcome;
3. one operational outcome.

For each workflow, capture:

- initial thought and desired outcome;
- existing tools and sources;
- clarification questions required;
- context selected and corrected;
- manual handoffs avoided or added;
- decisions and approval points;
- actions attempted;
- verification evidence;
- time to an acceptable plan;
- time to verified completion;
- trust failures, surprises, and unnecessary friction;
- lessons worth retaining or converting into a skill.

The workflow and requirements should be revised before technical design if the evidence shows that coordination overhead outweighs value or that a smaller product boundary delivers the outcome.

## 22. Traceability to PRD requirements

| PRD requirement | Specification coverage |
|---|---|
| FR-01 Capture intent | Sections 6.1, 8, AS-01 |
| FR-02 Preserve provenance | Sections 6.2–6.3, 8, AS-02 |
| FR-03 Define outcome | Sections 6.2, 6.4 |
| FR-04 Ask selectively | Sections 6.2, 10, AS-03 |
| FR-05 Scope context | Sections 6.3, 9, AS-12 |
| FR-06 Apply reusable process | Section 11, AS-11 |
| FR-07 Plan consequential work | Sections 6.4, 13, AS-05 |
| FR-08 Control authority | Sections 12–13, AS-06 |
| FR-09 Track exact state | Sections 3 and 7, AS-07 |
| FR-10 Expose activity | Sections 6.5 and 17 |
| FR-11 Handle plan changes | Sections 6.4, 7, 10, 13 |
| FR-12 Verify outcomes | Sections 6.6 and 15, AS-08 |
| FR-13 Resume safely | Sections 7 and 14, AS-10 |
| FR-14 Close with evidence | Sections 6.7 and 16, AS-13 |
| FR-15 Retain learning | Sections 6.7 and 11 |
| FR-16 Export project record | Sections 9, 16, and 17 |

## 23. Open product decisions

The following remain unresolved and must not be inferred from this specification:

- the first end-to-end work category;
- the smallest valuable workflow and exact MVP boundary;
- which steps OS performs directly versus coordinates externally;
- the detailed approval policy for each action category;
- credible evidence standards for different outcome types;
- the interface form and interaction model;
- the separation and precedence of user, project, work-item, and source context;
- skill ownership, authoring, testing, sharing, synchronization, and retirement;
- collaboration, identity, access, and multi-user requirements;
- privacy, retention, deletion, audit, and compliance policies;
- pricing, business model, distribution, and commercialization;
- quantitative success thresholds;
- differentiation from current agent, knowledge, workflow, and automation products;
- architecture, APIs, database schemas, technology stack, hosting, repository structure, deployment, and implementation plan.

## 24. Decision and assumption register

| Item | State | Basis |
|---|---|---|
| Working name is OS | Confirmed | Ideas Hub |
| OS is standalone and not part of Hibachi | Confirmed | Ideas Hub and current conversation |
| Broad direction coordinates agents, project knowledge, skills, and tools | Confirmed direction | Ideas Hub |
| Intended direction is idea-to-outcome completion | Confirmed direction | Ideas Hub |
| First user is Kofi | Locked hypothesis | Current conversation |
| Primary problem statement | Locked hypothesis | Current conversation |
| Seven-stage workflow | Proposed hypothesis | PRD and this specification |
| Product states and behavioural rules | Proposed hypothesis | This specification |
| MVP acceptance scenarios | Proposed hypothesis | This specification |
| Architecture and technology decisions | Open | Requires validated product evidence |

## 25. Change control

- Changes to confirmed boundaries require an explicit product decision.
- Changes to locked hypotheses must record the new hypothesis and why it supersedes the prior one.
- New requirements must identify supporting evidence or remain labelled as proposed.
- Architecture or implementation decisions belong in separate documents after product validation.
- Approval of this specification means approval of its product-definition scope; it does not authorize implementation.

## 26. References

- docs/PRD.md, Draft v0.1.
- Canonical Ideas Hub project record: kofiarhin/ideahub, projects/os.md on main.
- Reference transcript described in the PRD: inspiration only, not an authoritative requirements source.
- Current conversation decisions: Kofi as first-user hypothesis; locked primary problem hypothesis; OS remains standalone.
