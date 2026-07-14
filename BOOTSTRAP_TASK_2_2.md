# Temporary Bootstrap Governance — TASK-2.2

## Status and Limitation

This document is temporary bootstrap governance. It is not a canonical `DEF` record and is not a canonical `HD` record. It exists because the canonical Definition and Human Decision specifications and templates are not yet available; producing them is the objective of the Work Item this artifact governs.

This artifact preserves the approved Work Item definition and governing Human Decision as explicit, reviewable repository prose under the Bootstrap Ordering Rule. It must remain historically distinguishable from future Canonical Records and must not later be represented as a Canonical Record that existed at this time.

## Work Item

`TASK-2.2 — Canonical Metadata Specification and DEF/HD Templates`

## Objective

Define the concrete Canonical metadata specification and the Definition (`DEF`) and Human Decision (`HD`) record templates needed so that future Work Items can satisfy the Bootstrap Ordering Rule through Canonical Records instead of temporary bootstrap artifacts.

## Approved Scope

TASK-2.2 may define:

- the concrete Canonical metadata specification, realizing the conceptual categories of `CANONICAL_METADATA.md`;
- the concrete metadata representation within Canonical Record files;
- concrete metadata fields, their meanings, and their interpretation rules;
- which metadata applies generally across Record Types and which is specific to `DEF` and `HD` records;
- required and optional metadata for `DEF` and `HD` records;
- how metadata expresses identity, Work Item, traceability, authority, relationship, evidence, review, historical, recovery, and safety context without creating authority;
- the `DEF` record template;
- the `HD` record template;
- how the templates carry the objective, Approved Scope, explicit non-goals, and Acceptance Criteria that the Bootstrap Ordering Rule requires a Definition to make reviewable;
- how an `HD` record identifies the Definition it approves, its decision authority, and its limitations;
- the minimum `index.md` reference requirements needed to locate the currently governing Definition and the Human Decision approving that Definition;
- how metadata and templates reference Canonical Identifiers and canonical paths; and
- extension guidance for how later Record Type templates reuse the general metadata specification.

TASK-2.2 Implementation may create or modify only the following authorized deliverables:

```text
CANONICAL_METADATA_SPECIFICATION.md
templates/DEF.md
templates/HD.md
```

This authorized deliverable set is closed. No other template is authorized, and no actual Canonical Record under `records/` is authorized. Adding to or changing the authorized deliverable set requires a new explicit Human Decision. `BOOTSTRAP_TASK_2_2.md` is temporary bootstrap governance and is not itself a TASK-2.2 implementation deliverable; TASK-2.2 Implementation must not create or modify it.

The specification and templates must remain consistent with all committed governance and Canonical principles documents, including:

- the conceptual metadata categories, quality principles, and authority boundaries of `CANONICAL_METADATA.md`;
- the identifier syntax, Record Type prefixes, storage layout, and file naming rules of `CANONICAL_IDENTIFIER_AND_STORAGE_LAYOUT.md`, which TASK-2.2 uses but must not modify;
- the Record Type responsibilities of `CANONICAL_RECORD_TYPES.md` and the Canonical Record Model;
- the relationship and authority principles of the committed Canonical principles documents; and
- the Bootstrap Ordering Rule and Human Decision Gates of `AGENTS.md`.

## Explicit Exclusions

TASK-2.2 must not define or perform:

- creation or modification of any file outside the authorized deliverable set;
- templates for Record Types other than `DEF` and `HD` (`RV`, `FD`, and `FDP` templates belong to TASK-2.4; remaining templates belong to TASK-2.6);
- `index.md` requirements beyond the minimum reference requirements needed to locate the currently governing Definition and the Human Decision approving that Definition;
- general `index.md` content, summaries, status, priority, assignment, workflow state, record inventory, latest-review pointers, derived metadata, or `index.md`-based approval or transition behavior;
- creation of actual Canonical Records under `records/`;
- retrospective `DEF`/`HD` recording for earlier Work Items (this belongs to TASK-2.3);
- modification of any committed governance or Canonical principles document;
- modification of `CANONICAL_LIFECYCLE.md`;
- modification of `CANONICAL_IDENTIFIER_AND_STORAGE_LAYOUT.md`;
- new Record Types, Record Type prefixes, or Work Item prefixes;
- validation implementation;
- CLI behavior;
- automatic metadata generation, allocation, or renumbering;
- workflow transitions, approval procedures, or status automation;
- commit or push automation;
- external-system mutation; or
- provider-specific behavior.

## Acceptance Criteria

1. Only the authorized deliverables — `CANONICAL_METADATA_SPECIFICATION.md`, `templates/DEF.md`, and `templates/HD.md` — are created or modified during TASK-2.2 Implementation.
2. No file outside the authorized deliverable set is created or modified; no other template exists; no file exists under `records/`; and `BOOTSTRAP_TASK_2_2.md` is not created, modified, or treated as a TASK-2.2 implementation deliverable.
3. The authorized deliverable set has not been expanded or changed without a new explicit Human Decision.
4. The specification and templates are consistent with all committed governance and Canonical principles documents.
5. A concrete Canonical metadata specification is defined that realizes the conceptual categories of `CANONICAL_METADATA.md` without redefining them.
6. A concrete metadata representation is defined that is portable, provider-neutral, and reviewable as plain text.
7. Purposeful: every metadata field has a stated purpose tied to identification, interpretation, traceability, authority context, review, history, recovery, or safety.
8. Minimal: no metadata field is included unless its stated purpose cannot be satisfied by existing record content, identifiers, paths, or another approved field without harmful duplication.
9. Clear: every metadata field has an unambiguous name, meaning, value expectations, and applicability.
10. Consistent: shared metadata fields retain the same meaning across `DEF` and `HD` records, and type-specific fields do not redefine shared semantics.
11. Traceable: metadata references use the committed Canonical Identifier rules and identify the referenced subject unambiguously.
12. Reviewable: a reviewer can determine required versus optional fields and evaluate a record without relying on chat history or agent memory.
13. Durable: metadata does not depend on provider-specific, session-specific, transient, or external-system-only state.
14. Safe: metadata requirements prohibit credentials, secrets, private keys, credential-bearing URLs, and unnecessary sensitive or personal information.
15. The specification distinguishes metadata that applies generally across Record Types from metadata specific to `DEF` and `HD` records.
16. No metadata field creates, implies, or automates authority, approval, correctness, completeness, Evidence, a review verdict, a Finding Disposition, Finalization, status, or workflow progression.
17. A `DEF` template is defined that makes the Work Item's objective, Approved Scope, explicit non-goals, and Acceptance Criteria reviewable, as the Bootstrap Ordering Rule requires.
18. An `HD` template is defined that records an explicit human decision, identifies the Definition or subject it governs, identifies the decision authority, and preserves the decision's limitations.
19. The `HD` template does not allow a decision to be inferred from authorship, file presence, Implementation activity, or automation.
20. Metadata and templates reference Work Items and Canonical Records using the identifier syntax and fully qualified forms of `CANONICAL_IDENTIFIER_AND_STORAGE_LAYOUT.md`.
21. Templates are compatible with the canonical storage layout and file naming conventions without modifying them.
22. Any `index.md` requirements are limited to the minimum reference requirements needed to locate the currently governing Definition and the Human Decision approving that Definition.
23. No general `index.md` content, summaries, status, priority, assignment, workflow state, record inventory, latest-review pointers, derived metadata, or `index.md`-based approval or transition behavior is defined.
24. Templates for Record Types other than `DEF` and `HD` are not defined.
25. No retrospective `DEF` or `HD` records are produced for earlier Work Items.
26. External identifiers remain external references, and no external system or task manager is made authoritative.
27. Historical Summary is not silently treated as an approved Record Type and receives no template or metadata identity.
28. Temporary bootstrap governance artifacts remain distinguishable from Canonical Records and are not relabeled by the specification or templates.
29. The specification does not introduce validation implementation, CLI behavior, automatic generation or allocation, workflow transitions, approval procedures, status automation, or commit or push automation.
30. No provider-specific or task-manager-specific authority is introduced.
31. No committed governance or Canonical principles document is modified.
32. `CANONICAL_LIFECYCLE.md` is not modified, staged, committed, or included in TASK-2.2 work.
33. `CANONICAL_IDENTIFIER_AND_STORAGE_LAYOUT.md` is not modified during TASK-2.2 work.

## Governing Human Decision

The human owner has explicitly adopted the following Phase 2 structure:

- TASK-2.0: Bootstrap ordering rule and temporary HD recording convention
- TASK-2.1: Identifier and storage layout specification
- TASK-2.2: Metadata specification and DEF/HD templates
- TASK-2.3: TASK-1.8 DEF/HD persistence and bootstrap-period HD retrospective recording
- TASK-2.4: RV/FD/FDP templates
- TASK-2.5: TASK-1.8 Independent Review
- TASK-2.6: Remaining Record Templates
- TASK-2.7: Phase 2 Historical Summary
- TASK-2.8: Phase 2 Phase Review

The human owner has also explicitly approved beginning TASK-2.2 after TASK-2.1, instructing that only this temporary bootstrap governance artifact be created first.

- **Decision:** Approve this temporary bootstrap definition as the governing scope and Acceptance Criteria for TASK-2.2.
- **Decision authority:** Human owner.
- **Authorization:** TASK-2.2 Implementation may begin only after this temporary artifact has completed its required review and finalization process and entered the authoritative committed repository state.
- **Limitation:** This decision approves TASK-2.2's scope; it does not pre-approve the metadata representation, field set, or template designs produced by TASK-2.2. Consequential architecture choices found during Implementation, including the choice of metadata representation, must be surfaced for Human Decision rather than assumed.

No additional Human Decision is recorded by this artifact.

## Effective Condition

This temporary bootstrap governance does not authorize TASK-2.2 Implementation merely by existing in an uncommitted working tree. It becomes the repository-resident governing scope and Human Decision for TASK-2.2 only after it completes the required review and finalization process and enters the authoritative committed repository state.

Until that condition is satisfied, TASK-2.2 Implementation must not begin.

## Future Canonical Transition

TASK-2.2 itself produces the canonical Definition and Human Decision specifications and templates. Once those are approved and available, future Work Items must use them as required by `AGENTS.md`, and the temporary bootstrap mechanism must no longer be used for new Work Items.

This artifact must remain identifiable as temporary bootstrap governance. It must not be relabeled, migrated, or described as a canonical `DEF` or `HD` record that existed at this time. A future Canonical Record may reference this artifact as historical bootstrap context without rewriting its original status or meaning.
