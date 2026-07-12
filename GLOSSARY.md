# Canonical Glossary

## Purpose

This glossary defines the shared terminology used by `agent-workflow-kit`. The definitions are provider-neutral and implementation-independent. They describe governance concepts, not record schemas, file layouts, metadata, templates, validation rules, command-line behavior, or workflow transitions.

## Terms

### Acceptance Criteria

The explicit, reviewable conditions used to determine whether a Work Item satisfies its approved objective and scope. Acceptance Criteria define what must be demonstrated; they do not establish their own completion or approval.

**Related terms:** Approved Scope, Evidence, Task Review

### Approved Scope

The boundaries of work that a human has explicitly authorized, including the intended outcome and any stated exclusions. Approval for one scope does not authorize work outside it or work belonging to another Work Item.

**Related terms:** Acceptance Criteria, Human Decision, Work Item

### Bootstrap

The initial period in which the project establishes the governance and foundations needed for later self-use. During bootstrap, some future artifacts or mechanisms may not yet exist and must not be invented or represented as completed.

**Related terms:** Historical Summary, Repository as Source of Truth

### Canonical Record

A durable repository artifact designated as authoritative for the project information it contains. A Canonical Record preserves information needed for review, recovery, or accountability without depending on chat history or agent memory.

**Notes:** This term does not prescribe a file format, location, or schema.

**Related terms:** Record Type, Repository as Source of Truth

### Evidence

Recorded information that supports or challenges a specific claim. Evidence must be distinguishable from assertions, recommendations, confidence, and conclusions, and its limitations must remain visible.

**Related terms:** Acceptance Criteria, Finding, Independent Review

### Finalization

The human-controlled conclusion that a Work Item has satisfied its approved completion conditions after relevant Evidence, reviews, findings, dispositions, and unresolved limitations have been considered. Finalization does not by itself authorize a commit, push, release, or external mutation.

**Related terms:** Finalization Assessment, Human Decision, Independent Review

### Finalization Assessment

A read-only evaluation of whether a Work Item is ready for the human action required to conclude it. The assessment reports readiness but does not itself finalize, commit, push, release, or mutate external state.

**Related terms:** Finalization, Independent Review

### Finding

A review observation that identifies a defect, inconsistency, risk, unmet criterion, or other matter requiring visibility. A Finding does not determine its own response.

**Related terms:** Finding Disposition, Independent Review, Remediation

### Finding Disposition

The recorded human decision about how a Finding will be handled, such as adopting it for remediation, deferring it, or rejecting it. A disposition must not be inferred from implementation activity or agent preference.

**Related terms:** Finding, Human Decision, Remediation

### Historical Summary

A later-created account of earlier work based on available authoritative sources. It must be identified as retrospective, distinguish verified facts from inference, and must not imply that records, reviews, decisions, or Evidence existed when they did not.

**Related terms:** Bootstrap, Evidence, Repository as Source of Truth

### Human Decision

An explicit choice made by an authorized human who retains final authority and accountability. AI may inform the choice through investigation and recommendations but must not make, approve, or imply the decision.

**Related terms:** Human Decision Gate, Finding Disposition

### Human Decision Gate

A boundary beyond which work must not proceed until an authorized human has made and recorded the required Human Decision. The presence of a file, field, status, or automated result does not satisfy the gate.

**Related terms:** Human Decision, Approved Scope

### Implementation

The task-scoped creation or modification of approved project artifacts or behavior. Implementation must follow the Approved Scope and must remain separate from Independent Review.

**Related terms:** Approved Scope, Independent Review, Remediation

### Independent Re-Review

A read-only review performed after adopted Remediation to determine whether the relevant Findings were addressed without unacceptable regression. It remains separate from the remediation work and does not perform further changes.

**Related terms:** Independent Review, Finding, Remediation

### Independent Review

A read-only assessment of work by a reviewer separate from the implementation role. It evaluates the defined review scope against applicable criteria and Evidence; implementation self-assessment is not Independent Review.

**Related terms:** Evidence, Finding, Review Level

### Investigation

A read-only examination that establishes facts, identifies unknowns, compares alternatives, explains trade-offs, and may recommend a course of action. An Investigation does not implement its recommendation or make a Human Decision.

**Related terms:** Human Decision, Implementation

### Milestone

A bounded collection of related Phases, Work Items, or outcomes used to evaluate broader completeness, integration, and readiness toward a project objective.

**Related terms:** Milestone Review, Phase, Work Item

### Milestone Review

A review whose scope evaluates milestone-level completeness, integration, and readiness against approved milestone criteria. It does not redefine lower-level scope or authorize release or progression that requires a Human Decision.

**Related terms:** Milestone, Phase Review, Review Level

### Phase

A bounded grouping of related Work Items or governance artifacts organized around a shared intermediate objective. A Phase does not alter the Approved Scope or Acceptance Criteria of its constituent Work Items.

**Related terms:** Milestone, Phase Review, Work Item

### Phase Review

A review whose scope evaluates consistency across the related Work Items or artifacts included in a Phase. It may identify cross-cutting Findings but does not retroactively redefine lower-level Acceptance Criteria.

**Related terms:** Phase, Task Review, Review Level

### Provider Neutrality

The principle that project rules and durable records must not require a particular AI provider, model, product, IDE, hosting service, or proprietary interaction format.

**Related terms:** Repository as Source of Truth

### Record Type

A semantic category that identifies the purpose of a Canonical Record, such as Investigation, Human Decision, Evidence, or Review. A Record Type describes responsibility and meaning without prescribing storage or syntax.

**Related terms:** Canonical Record

### Remediation

Task-scoped work performed to address only Findings explicitly adopted by a human. Remediation must not silently address deferred, rejected, or unrelated Findings and remains subject to Independent Re-Review when required.

**Related terms:** Finding, Finding Disposition, Independent Re-Review

### Repository as Source of Truth

The principle that the main Git repository contains the authoritative approved project state needed for recovery, review, and accountability. Chat history, transient tool output, external operational systems, and agent or human memory are not authoritative substitutes.

**Related terms:** Canonical Record, Provider Neutrality, Session Handoff

### Review Level

The declared breadth at which a Review is bounded, such as Task, Phase, or Milestone. Review Level identifies scope without making one level's criteria or verdict override another's.

**Related terms:** Task Review, Phase Review, Milestone Review

### Session Handoff

A durable account that enables another human or AI to resume a Work Item safely without relying on chat history. It communicates the relevant current context, limitations, and safe continuation point without changing approvals, decisions, or status.

**Related terms:** Repository as Source of Truth, Work Item

### Task

A Work Item with a specific, bounded objective, Approved Scope, and Acceptance Criteria. A Task is intended to produce a small, reviewable, and traceable outcome.

**Related terms:** Task Review, Work Item

### Task Review

A review whose scope evaluates one Task against its Approved Scope and Acceptance Criteria. It does not add, change, or reinterpret the approved requirements.

**Related terms:** Acceptance Criteria, Approved Scope, Task

### Work Item

A provider-neutral unit of approved or proposed project work that can be identified, bounded, reviewed, and traced. Tasks, Phases, Milestones, and dedicated governance or review efforts may be treated as Work Items when appropriate.

**Related terms:** Task, Phase, Milestone
