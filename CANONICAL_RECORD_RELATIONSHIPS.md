# Canonical Record Relationships

## Purpose and Scope

This document explains the conceptual relationships among Canonical Record Types. These relationships make project knowledge traceable by showing how one record provides context for, governs, supports, assesses, or summarizes work represented by another.

Canonical relationships are implementation-independent. They are not workflow transitions, do not require that every related Record Type exist for every Work Item, and do not create approval or authority through reference alone. The existence of a record or a reference does not establish that its claims are correct, approved, or complete.

## Relationship Perspectives

### Upstream and Downstream Context

An upstream record provides context that later work may rely on, such as a Definition that bounds Implementation or Evidence considered by Review. A downstream record describes work, assessment, or conclusions informed by that context.

Upstream and downstream describe the direction of contextual dependency, not chronology, status, or permission to proceed. A downstream reference does not modify its upstream record, and an upstream record does not guarantee that any downstream record exists.

### Authority Relationships

An authority relationship exists only when an authorized Human Decision governs another record or action within its stated scope. For example, a Human Decision may approve a Definition or determine how a Finding will be handled.

A reference to a Human Decision helps trace authority but does not create, broaden, or transfer that authority. Other Record Types may preserve recommendations, claims, Evidence, assessments, or summaries, but they must not substitute for the required Human Decision.

### Informational Relationships

An informational relationship provides context without granting authority. Investigation may inform a Definition or Human Decision; Evidence may support or challenge a claim; and a Session Handoff may direct a future reader to recovery-relevant records.

Informational relationships do not imply endorsement, approval, correctness, or completeness. The receiving record remains responsible for interpreting the referenced information and its limitations.

### Review Relationships

A review relationship connects a read-only Review to the bounded work, approved criteria, and Evidence it assesses. Findings preserve concerns identified through that Review, while Independent Re-Review evaluates adopted Remediation without becoming part of the remediation work.

Review relationships must preserve independence. They do not authorize a reviewer to implement changes, allow a Review to redefine Approved Scope or Acceptance Criteria, or make a verdict equivalent to a Human Decision.

## Major Conceptual Relationships

### Definition and Human Decision

A Definition proposes or preserves the bounded objective, Approved Scope, exclusions, Acceptance Criteria, and constraints of a Work Item. A Human Decision may approve that Definition or govern a later change to it.

The Definition does not approve itself. Merely referring to a Human Decision does not prove approval; the authorized human choice preserved by that decision is the source of governance authority.

### Definition and Investigation

Investigation may provide facts, unknowns, alternatives, trade-offs, and recommendations that inform a Definition. The Definition may rely on that context when expressing a bounded objective or constraints.

Investigation remains informational. It does not approve the Definition, and the Definition does not convert recommendations into Human Decisions.

### Definition and Implementation

An approved Definition provides the governing boundary against which Implementation is performed and later assessed. Implementation describes changes and claims made within that boundary.

Implementation does not alter the Definition through reference or activity. If the approved boundary is insufficient, a separate Human Decision is required rather than treating implementation as implicit scope expansion.

### Implementation and Evidence

Evidence may support or challenge claims made by Implementation. This relationship makes clear which observations or results are relevant to an implementation claim and which limitations affect their interpretation.

Implementation is not Evidence of correctness by itself, and Evidence does not automatically validate the Implementation or authorize another action.

### Review and Implementation

Review assesses bounded Implementation against the applicable approved Definition, Acceptance Criteria, and Evidence. The relationship preserves what was reviewed without merging the implementation and reviewer responsibilities.

Review remains read-only. It does not modify Implementation, perform Remediation, redefine the reviewed scope, or grant approval merely by reaching a conclusion.

### Review and Finding

A Finding originates from a bounded Review and preserves a defect, inconsistency, risk, unmet criterion, or other concern identified by that Review. The relationship provides the review context needed to understand the Finding.

A Finding is not automatically created for every observation, and its existence does not determine its treatment. The Review does not silently remediate the Finding it identifies.

### Finding and Finding Disposition

A Finding Disposition preserves the human-controlled determination of how a Finding will be handled. It keeps the observed concern separate from the decision to adopt, defer, reject, or otherwise treat it.

The Finding cannot decide its own disposition. A disposition requires Human Decision authority and does not arise from a reference, implementation change, or automated result.

### Finding Disposition and Remediation

An adopted Finding Disposition bounds the Remediation authorized to address the relevant Finding. Remediation describes corrective work within that adopted scope.

This relationship does not authorize unrelated cleanup or work on deferred or rejected Findings. Remediation does not revise the disposition or determine that the Finding has been resolved.

### Remediation and Independent Re-Review

Independent Re-Review assesses the relevant Remediation against the adopted Findings, their dispositions, applicable criteria, and Evidence. It determines what the review can conclude about the remediation work while remaining independent from it.

Independent Re-Review does not perform further Remediation, rewrite the original Review or Finding, or automatically establish Finalization.

### Finalization and Prior Records

Finalization considers the approved Definition, applicable Human Decisions, Implementation, Evidence, Reviews, Findings, Finding Dispositions, Remediation, Independent Re-Review, and unresolved limitations that are relevant to the Work Item.

This relationship preserves the basis for the human-controlled conclusion without making every Record Type universally required. Finalization does not replace prior records and does not authorize commit, push, release, status change, or external mutation.

### Session Handoff and Recovery-Relevant Records

A Session Handoff may direct a future human or AI to the records needed to recover a Work Item safely, including its Definition, Human Decisions, Investigation, Implementation, Evidence, Reviews, Findings, dispositions, Remediation, Finalization, and earlier handoffs when relevant.

These informational relationships do not change project state. A Session Handoff does not grant assignment, approval, authority, or permission to perform the next action, and it must not replace the authoritative records it summarizes.

## Relationship Boundaries

Conceptual relationships support repository-first recovery, Evidence-based assessment, independent review, Human governance, and traceability across small reviewable changes. They remain provider-neutral and must not depend on a particular tool, task manager, hosting service, or external system.

Automation may later assist with transparent, read-only checks of concrete relationships, but automation must not infer approval, validity, verdict, disposition, Finalization, or authority from a relationship.

This document does not define metadata, schemas, identifiers, filenames, directories, relationship or graph syntax, storage implementation, validation rules, workflow transitions, templates, or command-line behavior.
