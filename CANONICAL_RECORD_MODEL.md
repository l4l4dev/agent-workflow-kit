# Canonical Record Model

## Purpose

The Canonical Record Model is the conceptual architecture for preserving durable project knowledge in the repository. It enables humans and AI to recover approved project state without relying on chat history, agent memory, a particular provider, or an external task-management system.

The model supports repository-first development by keeping the information needed for investigation, human governance, implementation accountability, evidence-based verification, independent review, remediation, finalization, and session recovery available as reviewable repository artifacts. It establishes responsibilities and relationships among records without prescribing their implementation.

## Design Principles

### Work Item Centricity

Records are understood in the context of a bounded Work Item. This keeps purpose, Approved Scope, Acceptance Criteria, Evidence, decisions, and review outcomes traceable to the work they concern. Task, Phase, Milestone, and dedicated governance or review efforts may each serve as a Work Item when appropriate.

### Durable History

Authoritative historical records preserve what was known, claimed, decided, reviewed, or handed off at a particular point in the work. Later developments must not erase the historical meaning needed to reconstruct earlier decisions or review boundaries.

### Explicit Human Governance

Human Decisions remain explicit and attributable. Creating a record, producing an automated result, or completing implementation does not establish approval or satisfy a Human Decision Gate by itself.

### Evidence over Assertions

Claims must remain distinguishable from Evidence. Agent confidence, recommendations, and conclusions do not become Evidence merely because they are recorded.

### Review Independence

Implementation and Independent Review have separate responsibilities. Implementation self-assessment does not replace Independent Review, and adopted Remediation may require Independent Re-Review.

### Minimal Automation

Automation may assist with transparent, mechanical work, but it must not make Human Decisions, approvals, review verdicts, Finding Dispositions, or Finalization decisions. It must not infer authority from record presence or structure.

### Traceability and Reviewability

Material claims, decisions, Evidence, Findings, and outcomes should be connected clearly enough to explain what they concern and why later work relied on them. Records and changes should remain small enough for meaningful human review.

### Provider Neutrality

The model must remain usable without a particular AI provider, model, IDE, hosting service, task-management system, or proprietary interaction format.

## Conceptual Building Blocks

### Definition

Establishes a Work Item's objective, Approved Scope, explicit exclusions, and Acceptance Criteria. A Definition describes what has been proposed or approved; it does not approve itself.

### Human Decision

Records an explicit choice made by an authorized human, including the decision needed to cross a Human Decision Gate. It preserves human authority and accountability rather than transferring them to an agent or automated process.

### Investigation

Preserves verified facts, unknowns, alternatives, trade-offs, limitations, and recommendations produced through read-only analysis. It informs a Human Decision but does not implement or decide.

### Implementation

Describes the changes made within the Approved Scope and the claims associated with those changes. It provides an accountable implementation history without serving as Independent Review.

### Evidence

Preserves information that supports or challenges a specific claim, together with the limitations needed to interpret it. Evidence enables verification but does not guarantee correctness, security, compliance, or audit completeness.

### Review

Preserves an independent assessment of a bounded set of work against applicable criteria and Evidence. It communicates the review scope, conclusions, limitations, and any Findings without modifying the reviewed implementation.

### Finding

Identifies a defect, inconsistency, risk, unmet criterion, or other matter discovered through review. A Finding makes an issue visible but does not determine its own treatment.

### Finding Disposition

Preserves the human decision about how a Finding will be handled. It distinguishes Findings adopted for Remediation from those deferred or rejected.

### Remediation

Describes changes made to address only Findings explicitly adopted by a human. It connects corrective work to the Findings that authorized its scope.

### Finalization

Preserves the human-controlled conclusion reached after applicable scope, Evidence, reviews, Findings, dispositions, Remediation, and unresolved limitations have been considered. It does not by itself authorize commit, push, release, or external mutation.

### Session Handoff

Preserves the context required for another human or AI to resume a Work Item safely without chat history. It communicates the current recovery point and relevant limitations without changing approvals, decisions, assignments, or status.

## Record Relationships

Canonical Records gain meaning through explicit conceptual relationships. A Review concerns particular work and criteria; Evidence supports or challenges claims; a Finding originates from a Review; a Finding Disposition governs the response to that Finding; Remediation addresses adopted Findings; and Independent Re-Review evaluates the relevant Remediation.

Relationships must preserve traceability across later changes and must not allow a summary, pointer, or derived result to silently replace an authoritative record. The identifier system, relationship syntax, metadata, and storage layout are intentionally left to later specifications.

## Review Levels

### Task Review

Task Review evaluates one Task against its Approved Scope and Acceptance Criteria. It does not add, change, or reinterpret the approved requirements.

### Phase Review

Phase Review evaluates consistency across the related Work Items or governance artifacts within a bounded Phase. It may identify cross-cutting Findings but must not retroactively redefine lower-level Acceptance Criteria.

### Milestone Review

Milestone Review evaluates milestone-level completeness, integration, and readiness against approved milestone criteria. It does not redefine lower-level scope or make release or progression decisions reserved for humans.

Review Levels describe different breadths of assessment. A broader Review does not overwrite a narrower Review's result or expand the Approved Scope of a lower-level Task.

## Conceptual Lifecycle

A Work Item may involve the following responsibilities:

```text
Investigation
    ↓
Human Decision
    ↓
Implementation
    ↓
Independent Review
    ↓
Remediation, when findings are adopted
    ↓
Independent Re-Review, when required
    ↓
Finalization
```

This sequence illustrates responsibility and accountability, not an automatic workflow or a universal transition system. No stage authorizes the next stage, commit, push, release, or external mutation merely by existing.

## Bootstrap

Before the complete Canonical Record Model is available, the repository relies on committed governance documents and explicitly supplied task instructions. Missing future artifacts must be reported as unavailable rather than invented.

Bootstrap work must not be retroactively represented as having Canonical Records that did not exist at the time. If later context is needed, a clearly identified Historical Summary may distinguish verified facts from inference and acknowledge unavailable Evidence.

## Future Expansion

Later approved tasks may define Record Types, metadata, relationships, templates, and read-only mechanical validation. Those specifications may make this architecture concrete, but they must preserve its repository-first, human-governed, evidence-based, review-independent, and provider-neutral boundaries.

This overview does not define record schemas, metadata fields, identifier syntax, directory layout, file naming, validation rules, templates, prompt formats, command-line behavior, workflow transitions, or integrations with external systems.
