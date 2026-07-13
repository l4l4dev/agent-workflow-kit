# Canonical Identifier Principles

## Purpose and Scope

Canonical Identifiers provide stable, repository-controlled ways to distinguish and reference Work Items, Canonical Records, and other concepts that later approved specifications designate as identifiable. They support durable navigation, traceability, review, recovery, and relationships across sessions and changes.

Identifiers help humans and AI determine which project artifact or concept a reference concerns without relying on chat history, agent memory, a particular provider, or an external task-management system. This document defines conceptual principles only. It does not prescribe identifier syntax, generation, allocation, or storage.

## Architectural Role

The Canonical Record Model depends on references that remain understandable as project knowledge grows. Canonical Identifiers provide a stable point of reference while names, summaries, external systems, and derived views may change.

An identifier distinguishes what is being referenced; it does not describe the referenced content in full. It should support connections among records without replacing Record Type responsibilities, relationship meaning, substantive record content, Evidence, or Human Decisions.

Identifier use must remain subordinate to repository governance. Being identifiable or referenced does not make an artifact approved, correct, complete, current, or authoritative.

## Conceptual Characteristics

The characteristics below guide later identifier specifications. They are architectural qualities, not concrete formats or validation rules.

### Uniqueness

A Canonical Identifier should distinguish one intended subject from every other subject within the scope in which the identifier is authoritative. Ambiguous reuse would weaken traceability and make relationships unreliable.

The concrete uniqueness scope and allocation method belong to later specifications. Uniqueness does not imply importance, approval, ownership, or workflow state.

### Stability

A Canonical Identifier should remain stable for the lifetime of the subject it identifies. Changes to titles, descriptions, summaries, tools, or external-system references should not silently change canonical identity.

Stability preserves historical meaning, but it does not prohibit later records from correcting or superseding substantive content. An identifier must not be reused to make a different subject appear to be the original one.

### Traceability

A Canonical Identifier should make it possible to follow references across relevant Canonical Records and reconstruct which subject a claim, Evidence item, Review, Finding, Human Decision, or Session Handoff concerns.

Traceability does not establish the truth or sufficiency of the referenced information. It shows connection and identity, not substantive validity.

### Referential Integrity

References should continue to resolve conceptually to the intended subject and should not silently point to a different subject over time. Missing, ambiguous, or conflicting references must remain visible rather than being guessed or repaired through unsupported inference.

Referential integrity supports reliable recovery and review. It does not make every possible related record required, nor does it define validation behavior.

### Portability

Canonical Identifiers should remain meaningful when the repository is cloned, moved, mirrored, or used without a particular provider, hosting service, IDE, task manager, or proprietary interaction format.

Portability requires canonical identity to remain under repository governance rather than depend exclusively on an external system whose availability or naming may change.

### Human Readability

Canonical Identifiers should be practical for humans to recognize, communicate, review, and transcribe with reasonable accuracy. Human readability supports accountable review and session recovery.

Readability must be balanced with uniqueness, stability, and portability. This principle does not select a prefix, numbering scheme, character set, or identifier format.

### Immutability of Assignment

Once a Canonical Identifier has been assigned to a subject and used authoritatively, its association with that subject should not be silently changed. Historical references must continue to identify the subject they originally concerned.

This principle protects traceability without defining correction, migration, or replacement mechanics. Any future exception must preserve historical meaning and require the applicable Human Decision.

### Minimal Embedded Meaning

An identifier may aid recognition, but its continued validity should not depend on mutable descriptive facts. Encoding excessive meaning creates pressure to change identifiers when titles, classifications, responsibility, or project context evolve.

Substantive meaning belongs in authoritative records and metadata, not solely in the identifier.

## Canonical and External Identifiers

A Canonical Identifier is governed by the repository and is intended to remain stable independently of external systems. It provides the repository's durable identity for the subject it identifies.

An external identifier is assigned or controlled by another system, such as a task manager, hosting service, or other repository. It may support navigation or coexistence but remains external operational context.

An external identifier must not replace Canonical identity merely because it is convenient or widely visible. Its presence does not make the external system a Source of Truth, and its absence or change must not prevent recovery of approved project state from the repository.

Associating a Canonical Identifier with an external identifier is informational. The association does not transfer authority, imply synchronization, authorize external mutation, or establish that both systems contain equivalent or current information.

## Relationships and Metadata

Canonical Identifiers enable records and metadata to refer unambiguously to relevant subjects. They support conceptual authority, informational, review, and recovery relationships without defining or changing those relationships.

A reference through an identifier does not imply approval, endorsement, correctness, completeness, existence of other expected records, or permission to proceed. Identifiers do not make metadata authoritative or convert a relationship into a workflow transition.

Derived indexes, summaries, caches, or external mappings may repeat Canonical Identifiers for navigation. Those derived views remain subordinate to the Canonical Records and Human Decisions they reference.

## Authority and Ownership Boundaries

Canonical Identifiers do not themselves establish authority, approval, correctness, completeness, ownership, assignment, status, workflow progression, Review verdict, Finding Disposition, Finalization, or permission for the next action.

Human governance determines when an identifiable subject or reference has authority. A Human Decision Gate cannot be satisfied by assigning, displaying, or referencing an identifier.

The apparent creator, location, sequence, age, or external association of an identifier must not be used to infer ownership or decision authority.

## Automation Boundary

Automation may later assist with transparent, read-only, mechanical handling of Canonical Identifiers. Such assistance may support navigation and consistency without deciding substantive meaning.

Automation must not use identifiers to make Human Decisions, approve work, determine correctness, assign ownership, change status, decide verdicts or dispositions, finalize work, modify records, commit, push, or mutate external systems.

## Privacy and Safety

Canonical Identifiers must not contain credentials, secrets, private keys, credentials embedded in URLs, or unnecessary personal or sensitive information. Identity must not depend on exposing protected values.

Later specifications should prefer safe, durable identifiers whose routine use does not disclose confidential context. Safe references must be used when protected information must remain outside repository records.

## Specification Boundary

Later approved tasks may define concrete identifier specifications while preserving the principles in this document and all higher-level governance. Those tasks must make uniqueness scope, migration considerations, and Human Decision boundaries explicit without weakening historical traceability.

This document does not define identifier syntax, prefixes, numbering schemes, UUID formats, filename conventions, directory layout, schemas, metadata fields, YAML, JSON, validation rules, templates, command-line behavior, workflow mechanics, or storage implementation.
