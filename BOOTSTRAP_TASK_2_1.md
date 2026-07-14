# Temporary Bootstrap Governance — TASK-2.1

## Status and Limitation

This document is temporary bootstrap governance. It is not a canonical `DEF` record and is not a canonical `HD` record. It exists because the canonical Definition and Human Decision specifications and templates are not yet available.

This artifact preserves the approved Work Item definition and governing Human Decision as explicit, reviewable repository prose under the Bootstrap Ordering Rule. It must remain historically distinguishable from future Canonical Records and must not later be represented as a Canonical Record that existed at this time.

## Work Item

`TASK-2.1 — Canonical Identifier and Storage Layout Specification`

## Objective

Define the concrete identifier and repository layout specification needed to make Canonical Records durably identifiable, referenceable, discoverable, and portable.

## Approved Scope

TASK-2.1 may define:

- Canonical identifier syntax;
- Work Item identifier conventions;
- Record identifier conventions;
- Record Type prefixes for the currently approved Record Types;
- uniqueness scope;
- allocation and sequence rules;
- identifier stability and non-reuse rules;
- handling of branch allocation collisions;
- external identifiers as non-canonical references;
- extension rules for future Record Types;
- treatment of Historical Summary within the identifier system;
- repository storage layout;
- Work Item-centered directory structure;
- location and role of `index.md`;
- file naming conventions; and
- the relationship between identifiers, directories, and filenames.

The specification must remain compatible with the previously approved Human Decisions, including:

- `records/<work-item-id>/` as the basic structure;
- one `index.md` per Work Item;
- Record Type-specific subdirectories only when needed;
- no global directories grouped primarily by Record Type;
- Phase Review and Milestone Review represented as identifiable Work Items;
- file or directory presence never establishing approval, status, or workflow transition;
- Work-item-local Record sequences;
- fully qualified Record identifiers;
- three-digit local sequence numbers;
- identifier reuse prohibited;
- branch collisions resolved by renumbering before integration;
- internal Work Item identifiers are canonical;
- external Issue identifiers remain external references;
- the same identifier approach applies to Task, Phase, and Milestone Review Work Items; and
- the Work Item prefix system itself must be explicitly specified by TASK-2.1 rather than assumed.

## Explicit Exclusions

TASK-2.1 must not define:

- concrete metadata fields beyond what is strictly necessary to explain identifier and layout boundaries;
- YAML, JSON, or front matter;
- `DEF` or `HD` templates;
- other Record Type templates;
- validation implementation;
- CLI behavior;
- automatic allocation;
- automatic renumbering;
- workflow transitions;
- approval procedures;
- status automation;
- commit or push automation;
- external-system mutation; or
- provider-specific behavior.

## Acceptance Criteria

1. Only the approved TASK-2.1 specification artifact or artifacts are created or modified during TASK-2.1 Implementation.
2. The specification is consistent with all committed governance and Canonical principles documents.
3. A canonical Work Item identifier system is defined.
4. The Work Item identifier system supports Task, Phase Review, Milestone Review, and governance-oriented Work Items without making an external task manager authoritative.
5. Canonical Record identifiers use a Work-item-local sequence.
6. A fully qualified Record identifier format is defined.
7. Record Type prefixes are defined for all currently approved Canonical Record Types.
8. Record local sequences use three digits.
9. Identifier reuse is prohibited.
10. Identifier assignment remains stable after authoritative use.
11. Parallel-branch sequence collisions are resolved without preserving duplicate identifiers.
12. External Issue or task-manager identifiers remain external references rather than Canonical Identifiers.
13. An extension rule exists for future Record Types.
14. The identifier design explicitly addresses Historical Summary without silently treating an undefined concept as an existing Record Type.
15. The repository layout is Work Item-centered.
16. The basic Work Item path is based on `records/<work-item-id>/`.
17. Each Work Item has an `index.md` navigation entry point.
18. Record Type-specific subdirectories are optional and used only when justified.
19. A global Record Type-first directory layout is not adopted.
20. Phase Review and Milestone Review records are organized through their own identifiable Work Items and references to reviewed Work Items.
21. File and directory names remain portable across supported Git environments.
22. The relationship between Canonical Identifiers, directories, and filenames is clearly specified.
23. File or directory existence does not imply authority, approval, correctness, status, or transition.
24. The specification does not introduce Canonical metadata fields, front matter, templates, validation implementation, CLI behavior, or workflow automation.
25. No provider-specific or task-manager-specific authority is introduced.
26. `CANONICAL_LIFECYCLE.md` is not modified, staged, committed, or included in TASK-2.1 work.

## Human Decision

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

The human owner has also explicitly approved proceeding with TASK-2.1 after TASK-2.0.

- **Decision:** Approve this temporary bootstrap definition as the governing scope and Acceptance Criteria for TASK-2.1.
- **Decision authority:** Human owner.
- **Authorization:** TASK-2.1 Implementation may begin only after this temporary artifact has completed its required review and finalization process and entered the authoritative committed repository state.
- **Limitation:** This decision approves TASK-2.1's scope; it does not pre-approve the architecture choices produced by TASK-2.1. Consequential architecture choices found during Implementation must be surfaced for Human Decision rather than assumed.

No additional Human Decision is recorded by this artifact.

## Effective Condition

This temporary bootstrap governance does not authorize TASK-2.1 Implementation merely by existing in an uncommitted working tree. It becomes the repository-resident governing scope and Human Decision for TASK-2.1 only after it completes the required review and finalization process and enters the authoritative committed repository state.

Until that condition is satisfied, TASK-2.1 Implementation must not begin.

## Future Canonical Transition

When the canonical Definition and Human Decision specifications and templates become available, future Work Items must use those mechanisms as required by `AGENTS.md`.

This artifact must remain identifiable as temporary bootstrap governance. It must not be relabeled, migrated, or described as a canonical `DEF` or `HD` record that existed at this time. A future Canonical Record may reference this artifact as historical bootstrap context without rewriting its original status or meaning.
