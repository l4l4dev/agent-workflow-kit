# Canonical Record Types

## Purpose and Scope

This document defines the responsibilities and boundaries of the Canonical Record Types used by `agent-workflow-kit`. A Record Type identifies the semantic purpose of a Canonical Record. It does not prescribe how that record is stored or represented.

No record gains authority merely by existing. Authority comes from the applicable governance and an explicit Human Decision where one is required. The conceptual relationships described below support traceability but do not define identifiers, metadata, syntax, storage, validation, or workflow mechanics.

## `DEF` — Definition

**Purpose:** Establish the bounded objective against which a Work Item is authorized, implemented, and reviewed.

**Represents:** A proposed or approved objective, Approved Scope, explicit exclusions, Acceptance Criteria, and relevant constraints for a Work Item.

**Must not represent:** Its own approval, a Human Decision, implementation progress, review outcome, or Finalization. A Definition does not become authoritative merely because it exists.

**Typical relationships:** A Human Decision may approve a Definition. Investigation may inform it; Implementation follows its approved boundaries; Review evaluates work against it; Finalization considers whether its approved completion conditions were satisfied.

## `HD` — Human Decision

**Purpose:** Preserve an explicit governance choice made by an authorized human.

**Represents:** The human decision that approves, rejects, defers, selects, or changes a course of action within the decision's stated scope.

**Must not represent:** An AI recommendation, inferred approval, automated result, implementation claim, review verdict, or decision created solely by record presence. Only the authorized human makes the decision that the record preserves.

**Typical relationships:** May be informed by Investigation, approve a Definition, establish a Finding Disposition, authorize adopted Remediation, or record another Human Decision Gate outcome. Other records may rely on it as their governance authority.

## `INV` — Investigation

**Purpose:** Preserve read-only analysis needed to understand a question before a Human Decision or scoped action.

**Represents:** Verified facts, unknowns, assumptions, alternatives, trade-offs, limitations, and recommendations discovered through investigation.

**Must not represent:** A Human Decision, approval, implementation, remediation, review verdict, or Finalization. A recommendation does not become authoritative merely because it is recorded.

**Typical relationships:** May inform a Definition or Human Decision and reference Evidence supporting its analysis. Later records may cite it for context without treating its recommendations as approval.

## `IMP` — Implementation

**Purpose:** Preserve an accountable account of changes made within an Approved Scope.

**Represents:** What was changed, the implementation claims being made, and the limitations or unresolved aspects of that work.

**Must not represent:** Approval, Independent Review, Evidence of correctness by itself, a Finding Disposition, or Finalization. Completion of Implementation does not authorize commit, push, release, or external mutation.

**Typical relationships:** Follows an approved Definition and applicable Human Decisions, may reference supporting Evidence, and is evaluated by Review. Remediation may produce separate implementation work in response to adopted Findings.

## `EV` — Evidence

**Purpose:** Preserve information that supports or challenges a specific claim.

**Represents:** Observations, results, or other recorded information together with the context and limitations needed to interpret them.

**Must not represent:** Unsupported assertion, agent confidence, recommendation, approval, guaranteed correctness, or a review verdict. Evidence does not decide the conclusion drawn from it.

**Typical relationships:** May support or challenge claims in Investigation, Implementation, Review, Remediation, Independent Re-Review, or Finalization. Findings may cite the Evidence on which they rely.

## `RV` — Review

**Purpose:** Preserve a read-only, independent assessment of bounded work against applicable criteria and Evidence.

**Represents:** The reviewed scope, assessment, conclusions, limitations, and Findings produced by an Independent Review or Independent Re-Review.

**Must not represent:** Implementation, Remediation, Human Decision, automatic approval, automatic Finalization, or self-assessment by the implementation role. A Review must not modify the work it assesses or redefine its Approved Scope and Acceptance Criteria.

**Typical relationships:** Evaluates Implementation or Remediation against an approved Definition and Evidence. It may produce Findings; an Independent Re-Review also relates to the earlier Review, adopted Findings, their dispositions, and the relevant Remediation.

## `FD` — Finding

**Purpose:** Preserve a review observation that requires explicit visibility and consideration.

**Represents:** A defect, inconsistency, risk, unmet criterion, or other concern identified within a bounded Review.

**Must not represent:** Its own Finding Disposition, approval to remediate, Remediation, or a change to Approved Scope or Acceptance Criteria. A Finding does not decide what action will be taken.

**Typical relationships:** Originates from a Review, concerns reviewed work or criteria, and may rely on Evidence. A Finding Disposition determines its human-approved treatment; adopted Findings may be addressed by Remediation and assessed by Independent Re-Review.

## `FDP` — Finding Disposition

**Purpose:** Preserve the human-controlled determination of how a Finding will be handled.

**Represents:** A human decision to adopt a Finding for Remediation, defer it, reject it, or otherwise determine its treatment within the approved governance boundary.

**Must not represent:** A Finding, review verdict, Remediation, automatic decision, or inferred response based on implementation activity. A Finding Disposition does not arise merely because work was changed.

**Typical relationships:** Applies to a Finding and derives its authority from an explicit Human Decision. An adopted disposition may bound Remediation; deferred or rejected dispositions remain visible to later Review and Finalization.

## `RM` — Remediation

**Purpose:** Preserve changes made specifically to address Findings adopted by a human.

**Represents:** The corrective work performed within the scope authorized by one or more adopted Finding Dispositions, including the claims and limitations of that work.

**Must not represent:** A new Finding Disposition, unrelated cleanup, silent treatment of deferred or rejected Findings, Independent Re-Review, or Finalization. Remediation does not determine whether it succeeded.

**Typical relationships:** Addresses adopted Findings under their dispositions, may rely on Evidence, and is evaluated by an Independent Re-Review. It may also relate to the approved Definition when confirming that remediation remains within scope.

## `FIN` — Finalization

**Purpose:** Preserve the human-controlled conclusion about a Work Item after its approved completion conditions and relevant project records have been considered.

**Represents:** The finalization conclusion and its basis, including the relevant scope, Evidence, Reviews, Findings, Finding Dispositions, Remediation, and unresolved limitations.

**Must not represent:** Automatic approval, an unperformed check, a replacement for Independent Review, or authorization to commit, push, release, change status, or mutate an external system. Readiness assessment alone is not Finalization.

**Typical relationships:** Considers the approved Definition, applicable Human Decisions, Implementation, Evidence, Reviews, Findings, dispositions, Remediation, and Independent Re-Review. It may inform a later human-controlled action without authorizing that action itself.

## `HO` — Session Handoff

**Purpose:** Preserve the context needed for another human or AI to resume a Work Item safely without relying on chat history.

**Represents:** The relevant recovery point, known state, limitations, unresolved matters, and safe continuation context at the time of handoff.

**Must not represent:** Approval, assignment, Human Decision, Review verdict, Finding Disposition, Finalization, status transition, or authorization to commit, push, release, or mutate external state. A Session Handoff communicates state but does not change it.

**Typical relationships:** May reference the applicable Definition, Human Decisions, Investigation, Implementation, Evidence, Reviews, Findings, dispositions, Remediation, Finalization, and earlier Session Handoffs needed for safe recovery.

## Specification Boundary

Later approved tasks may define metadata, identifiers, relationship syntax, storage layout, templates, and read-only mechanical validation for these Record Types. Those specifications must preserve the responsibilities and authority boundaries defined here.

This document does not define metadata fields, schemas, identifier syntax, filenames, directories, storage structure, validation rules, templates, prompt formats, command-line behavior, or workflow transitions.
