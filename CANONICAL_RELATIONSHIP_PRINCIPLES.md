# Canonical Relationship Principles

## Purpose and Scope

Canonical relationships make durable project knowledge understandable as a connected body of records rather than isolated documents. They help humans and AI determine how one Canonical Record provides context for, is governed by, supports, assesses, responds to, or summarizes another.

Relationships support repository-first traceability, review, and recovery without relying on chat history, agent memory, a particular provider, or an external task-management system. This document defines the conceptual qualities and boundaries of those relationships. It does not prescribe representation or implementation.

## Architectural Role

The Canonical Record Model separates responsibilities across Record Types. Relationships preserve the context needed to understand how those distinct responsibilities contribute to a Work Item while preventing one record from silently assuming another's role.

A relationship helps explain why records are relevant to one another. It does not replace substantive record content, Evidence, Human Decisions, Record Type responsibilities, or the reader's obligation to consider limitations.

Relationships must remain subordinate to repository governance. Their presence, absence, direction, or apparent completeness does not establish authority, approval, correctness, ownership, status, or permission to proceed.

## Conceptual Qualities

The qualities below guide later relationship specifications. They are architectural principles, not formal relationship categories, required structures, or validation rules.

### Traceability

A relationship should make the basis and context of project work easier to reconstruct. Readers should be able to understand which approved boundaries, Human Decisions, claims, Evidence, Reviews, Findings, dispositions, Remediation, or recovery context are relevant to a record.

Traceability shows connection, not truth. A relationship does not prove that either record is correct, sufficient, approved, or complete.

### Directionality

A relationship may have a meaningful direction: one record may provide context, authority, support, assessment, response, or summary for another. Direction helps communicate responsibility without merging the related records.

Directionality does not imply chronology, execution order, workflow progression, dependency completion, or permission for downstream work. A downstream record does not retroactively authorize or rewrite an upstream record.

### Referential Integrity

A relationship should continue to concern the intended Canonical Records and should not silently resolve to different subjects over time. Missing, ambiguous, or conflicting references must remain visible rather than being guessed or repaired through unsupported inference.

Referential integrity depends on stable Canonical identity but does not define identifier syntax, validation behavior, or a requirement that every conceivable related record exist.

### Authority Boundaries

An authority relationship may trace how an authorized Human Decision governs another record or action within its approved scope. The Human Decision supplies the governance authority; the relationship only makes that authority traceable.

A relationship cannot create, broaden, transfer, or substitute for authority. Informational, review, recovery, or derived relationships must not be treated as Human Decision approval.

### Responsibility Preservation

A relationship must preserve the responsibilities of both related Record Types. Linking Investigation to a Definition does not turn analysis into approval; linking Evidence to Implementation does not prove correctness; linking Review to Implementation does not permit the reviewer to implement; and linking a Finding to Remediation does not bypass its human-controlled disposition.

No record acquires another Record Type's responsibility merely by being related to it.

### Evidence Context

Relationships may connect Evidence to the claims it supports or challenges and may make the Evidence considered by Investigation, Review, Remediation, Independent Re-Review, or Finalization visible.

An Evidence relationship does not establish sufficiency, validity, correctness, or a verdict. Assertions, recommendations, and agent confidence do not become Evidence through association.

### Review Independence

Review relationships must preserve the separation between assessed work and the independent reviewer. They may connect Review to bounded Implementation, criteria, Evidence, Findings, or Remediation without making Review part of the work it assesses.

A Review relationship does not authorize implementation changes, redefine Approved Scope or Acceptance Criteria, decide a Finding Disposition, or make a Review verdict equivalent to a Human Decision.

### Historical Continuity

Relationships should preserve what records concerned and how they were understood at relevant points in project history. Later context must not silently rewrite earlier review boundaries, decisions, Findings, Evidence, or Session Handoffs.

Historical continuity permits later records to add context without presenting revised meaning as if it had always existed. A Historical Summary remains retrospective and must not be treated as a contemporaneous Canonical Record.

### Reviewability

Relationships should be understandable enough for a human reviewer to determine why the connection matters and whether the related records retain distinct responsibilities. Unnecessary or ambiguous connections reduce rather than improve traceability.

Reviewability favors purposeful, minimal, and clear relationships. It does not prescribe how a relationship is displayed or encoded.

### Recoverability

Relationships should help another human or AI locate the authoritative records needed to recover a Work Item safely without chat history. Recovery may require following context across Definitions, Human Decisions, Implementation, Evidence, Reviews, Findings, dispositions, Remediation, Finalization, and Session Handoffs when relevant.

Recovery relationships communicate context only. They do not assign work, approve an action, change status, alter prior decisions, or authorize the next step.

### Portability

Canonical relationships should remain meaningful when the repository is cloned, moved, mirrored, or used without a particular provider, hosting service, IDE, task manager, or proprietary interaction format.

An external reference may provide informational context, but it must not make the relationship or approved project state dependent exclusively on an external system.

## Relationship and Workflow Boundary

Conceptual relationships describe relevance, context, authority provenance, support, assessment, response, or summary. Workflow describes rules, gates, responsibilities, and allowed actions. These concerns must remain distinct.

A relationship is not a workflow transition, state change, execution order, prerequisite completion signal, or automatic progression rule. The existence of related records does not prove that a required activity occurred or that the next activity is authorized.

Not every Work Item requires every Record Type or every possible relationship. Missing relationships must be reported when relevant; they must not be invented to make a record set appear complete.

## Relationships, Metadata, and Identifiers

Canonical Identifiers may distinguish the subjects of relationships, and metadata may provide concise relationship context. Neither identifiers nor metadata create the semantic meaning or authority of a relationship by themselves.

Derived indexes, summaries, caches, or external mappings may assist navigation. They remain subordinate to the Canonical Records and Human Decisions they reference and must not silently replace canonical relationship context.

When derived context conflicts with authoritative records or Human Decisions, the higher-authority repository source governs. Convenience, recency, or mechanical generation does not grant authority.

## Authority and Automation Boundaries

Relationships do not themselves establish authority, approval, correctness, completeness, ownership, assignment, status, workflow progression, Review verdict, Finding Disposition, Finalization, or permission for the next action.

Automation may later assist with transparent, read-only, mechanical handling of relationships. It must not use relationships to make Human Decisions, approve work, infer substantive validity, determine verdicts or dispositions, finalize work, change status, modify records, commit, push, release, or mutate external systems.

## Privacy and Safety

Relationship context must not expose credentials, secrets, private keys, credentials embedded in URLs, or unnecessary personal or sensitive information. A useful connection does not justify disclosing protected values.

Safe references, redaction, or non-sensitive placeholders must be used when relationship context is needed without exposing confidential information.

## Specification Boundary

Later approved tasks may define concrete relationship specifications while preserving the principles in this document and all higher-level governance. Those tasks must keep Human Decision authority, review independence, historical continuity, and provider neutrality explicit.

This document does not define relationship syntax, edge notation, graph representation, serialization, schemas, metadata fields, identifier syntax, directory layout, filename conventions, YAML, JSON, validation rules, templates, command-line behavior, workflow mechanics, or storage implementation.
