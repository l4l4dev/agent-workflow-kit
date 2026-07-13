# Canonical Metadata Principles

## Purpose and Scope

Canonical metadata provides concise context for understanding, locating, relating, and reviewing Canonical Records. It helps humans and AI interpret a record consistently across sessions without relying on chat history, agent memory, a particular provider, or an external task-management system.

Metadata supports repository-first recovery and traceability, but it is not a substitute for record content, Evidence, or Human Decision. This document defines conceptual principles and categories only. It does not prescribe a representation or implementation.

## Role of Metadata

Metadata should make the responsibility and context of a Canonical Record easier to understand without duplicating the record's substantive content. It may help readers distinguish records, follow relevant relationships, identify the scope of an assessment, and understand the authority or limitations that apply.

Metadata must remain subordinate to the Canonical Record and the project's authoritative governance. When metadata summarizes or points to other information, it must not silently replace, reinterpret, or broaden the authoritative source.

Metadata should be sufficient for reliable navigation and interpretation while remaining minimal enough to review and maintain. Information belongs in metadata only when its contextual value justifies the risk of duplication, staleness, or ambiguity.

## Conceptual Metadata Categories

The categories below describe kinds of context metadata may serve. They are not fields, schemas, required sections, or a prescribed structure, and not every category applies to every Record Type.

### Identity Context

Identity context distinguishes a Canonical Record from other records and communicates what kind of responsibility it serves. It enables stable human understanding and unambiguous reference without determining a concrete identifier format.

Identity context must not imply approval, currentness, completeness, or authority merely because a record can be distinguished or classified.

### Work Item Context

Work Item context connects a record to the bounded work it concerns. It helps readers interpret the record within the relevant objective, Approved Scope, Acceptance Criteria, or broader Task, Phase, Milestone, governance, or review effort.

This context must not expand the Work Item's approved boundaries or make a record applicable to work outside its actual scope.

### Traceability Context

Traceability context helps reconstruct where a record came from, what project context it concerns, and how it fits into durable history. It supports review, recovery, and accountability across sessions and changes.

Traceability context must preserve historical meaning. It must not make later information appear to have existed earlier or turn a Historical Summary into a contemporaneous Canonical Record.

### Authority Context

Authority context helps a reader locate and understand the Human Decision governing a record or action when such authority is required. It makes the basis and boundary of human authorization traceable.

Metadata does not create, approve, broaden, or transfer authority. A reference, label, state description, or automated result cannot satisfy a Human Decision Gate or substitute for the authorized human choice preserved by a Human Decision.

### Relationship Context

Relationship context helps readers understand how a record provides context for, supports, assesses, responds to, or summarizes another record. It may reflect authority, informational, review, or other conceptual relationships already defined by the Canonical Record Model.

Relationship metadata must not change either Record Type's responsibility. A reference does not imply approval, correctness, completeness, existence of other expected records, or permission to proceed.

### Evidence Context

Evidence context helps connect Evidence with the claims it supports or challenges and preserves the limitations needed for responsible interpretation.

It must not turn assertions, recommendations, agent confidence, or conclusions into Evidence. Metadata about Evidence does not establish that the Evidence is sufficient, valid, or proof of correctness.

### Review Context

Review context helps bound an Independent Review or Independent Re-Review by clarifying the work, criteria, Evidence, and limitations relevant to the assessment. It may also help distinguish the breadth of a Task, Phase, or Milestone Review.

Review metadata must preserve review independence. It must not perform Implementation or Remediation, redefine Approved Scope or Acceptance Criteria, determine a Finding Disposition, or make a verdict equivalent to Human Decision or Finalization.

### Historical Context

Historical context helps distinguish records that preserve what was known, claimed, decided, reviewed, or handed off at different points in the work. It supports durable history while allowing later records to provide additional context.

Metadata must not erase, rewrite, or silently supersede historical meaning. Any later specification for changes or corrections must preserve the authority and traceability boundaries established by the higher-level documents.

### Recovery Context

Recovery context helps another human or AI locate the information necessary to resume a Work Item safely without chat history. It may support Session Handoff and repository navigation across recovery-relevant records.

Recovery metadata does not assign work, change status, approve an action, alter prior decisions, or authorize commit, push, release, or external mutation.

### Safety Context

Safety context may communicate handling limitations needed to protect privacy and sensitive information. Metadata must never contain credentials, secrets, private keys, or credentials embedded in URLs. Personal or other sensitive information must be minimized and included only when necessary, authorized, and appropriately protected.

Safe references, redaction, or non-sensitive placeholders should be used when context is needed without exposing protected values.

## Canonical and Derived Context

Metadata may restate authoritative context or be derived from existing repository information for navigation and assistance. The distinction must remain visible: derived or summarized context does not become authoritative merely because it is convenient, current-looking, or mechanically produced.

When metadata conflicts with authoritative record content or a Human Decision, the higher-authority source governs. Derived context must not overwrite a Canonical Record, Human Decision, Review conclusion, Finding Disposition, or Finalization.

## Quality Principles

Canonical metadata should be:

- **Purposeful:** included only when it improves interpretation, traceability, review, or recovery;
- **Minimal:** limited to context that belongs outside substantive record content;
- **Clear:** understandable without provider-specific knowledge or hidden conventions;
- **Consistent:** interpreted according to the same conceptual meaning across Record Types;
- **Traceable:** connected to the authoritative context it summarizes or references;
- **Reviewable:** concise enough for meaningful human inspection;
- **Durable:** stable across tools, sessions, and external-system changes; and
- **Safe:** free from credentials and unnecessary sensitive information.

These qualities guide later specifications but do not define validation rules or automated enforcement.

## Authority and Automation Boundaries

Metadata does not itself create authority, approval, correctness, completeness, Evidence, a review verdict, a Finding Disposition, Finalization, workflow progression, or permission to mutate any system. Its presence or absence does not automatically determine status or authorize the next action.

Automation may later assist with transparent, read-only mechanical handling of metadata. It must remain subordinate to Human Decisions and must not infer substantive validity, make governance choices, modify external systems, or act autonomously.

## Specification Boundary

Later approved tasks may define concrete metadata specifications while preserving the principles in this document and all higher-level governance. Those tasks must make their own scope and Human Decision boundaries explicit.

This document does not define schemas, field names, YAML, JSON, Markdown front matter, identifier syntax, directory layout, file naming, validation rules, templates, command-line behavior, workflow mechanics, or storage implementation.
