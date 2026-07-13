# Canonical Authority Principles

## Purpose and Scope

Authority within the Canonical Record Model is the legitimate human-governed basis for treating a decision, boundary, or conclusion as established project state within its approved scope. Authority makes accountability and permission traceable; it does not guarantee that the authorized choice is correct, complete, secure, or compliant.

The repository preserves authoritative project state, but authority ultimately remains with accountable humans. Canonical Records make that authority durable and reviewable without transferring it to AI, automation, record structure, or an external system. This document defines conceptual principles only and does not prescribe how authority is granted, represented, validated, or exercised.

## Foundational Principles

Authority must be:

- **Human-governed:** an authorized human retains final decision authority and accountability;
- **Explicit:** required authority must not be supplied through implication or unsupported inference;
- **Bounded:** authority applies only to the decision, scope, role, and action for which it was given;
- **Traceable:** repository records should make the authoritative basis and relevant limitations understandable;
- **Durable:** later activity must not silently rewrite the authority that governed earlier work;
- **Reviewable:** authority and its boundaries must remain open to meaningful human inspection; and
- **Provider-neutral:** authority must not depend on a particular AI provider, model, product, IDE, hosting service, or task manager.

Authority for one Work Item, role, phase, file, decision, or operation must not be treated as authority for another. Where a Human Decision Gate applies, work must not proceed on the assumption that authority will be granted later.

## Authority Perspectives

The perspectives below distinguish sources and uses of authority. They are not schemas, formal classifications, workflow states, or procedures.

### Human Authority

Human authority is the final decision authority and accountability retained by an authorized human. A Human Decision may establish an approved boundary, select among alternatives, determine a Finding Disposition, or authorize another matter reserved for human control.

AI may investigate, compare alternatives, explain trade-offs, and prepare recommendations. It must not make, approve, simulate, or imply the Human Decision. Human authority is limited to the actual decision and scope established; it is not a general delegation of unrelated authority.

### Record Authority

Record authority is the repository-recognized authority of a Canonical Record for the information it is responsible for preserving. It allows future readers to identify the durable source they should consult for that information.

A record's authority depends on its responsibility, governing context, and applicable Human Decision. The mere existence, location, age, apparent completeness, or Record Type of a record does not make its contents approved or authoritative. A record must not acquire another Record Type's responsibility through reference, repetition, or convenience.

### Evidence Authority

Evidence has authority as the recorded basis for supporting or challenging a specific claim within its stated context and limitations. Its value comes from what was actually observed or established, not from agent confidence or the prominence of its presentation.

Evidence does not make a Human Decision, approve work, establish its own sufficiency, or guarantee correctness. The presence of Evidence does not determine the conclusion that Investigation, Review, or Finalization may responsibly draw from it.

### Review Authority

Review has authority to preserve an independent assessment of bounded work against applicable criteria and Evidence. That authority is limited to the Review's actual scope, revision, criteria, Evidence, limitations, and conclusions.

Review authority does not permit the reviewer to implement, remediate, redefine Approved Scope or Acceptance Criteria, determine a Finding Disposition, make a Human Decision, or authorize commit, push, release, status change, or external mutation. A Review verdict is not interchangeable with Human Decision or Finalization.

### Derived Information

Derived information may summarize, index, calculate, cache, or present context from Canonical Records for navigation and mechanical assistance. It is useful only to the extent that its origin, limitations, and possible staleness remain visible.

Derived information is not an independent source of authority. Recency, convenience, aggregation, automated production, or apparent completeness must not allow it to override Canonical Records or Human Decisions. Conflicts must be resolved by consulting the applicable authoritative repository sources rather than treating the derived view as decisive.

### External System Authority

External systems may have operational authority over information they manage, such as assignment, scheduling, notifications, discussion, or board status. That operational role does not make them authoritative for the repository's approved project state.

External issues, project boards, wikis, task managers, repositories, and other remote systems do not replace Canonical Records or Human Decisions. Their identifiers, labels, states, approvals, or configuration must not be imported as repository authority through inference. Referencing an external system does not authorize synchronization, mutation, or reliance on that system for recovery.

## What Does Not Create Authority

Authority must not be inferred from:

- record existence, placement, formatting, or apparent completeness;
- relationships among records or references to an authoritative record;
- metadata, labels, summaries, pointers, or derived indexes;
- identifiers, naming, sequence, age, or external association;
- chronology, recency, or the order in which records appear;
- workflow progression, status, or the apparent completion of an activity;
- Implementation, Remediation, or other changes having been performed;
- Evidence, Review conclusions, or automated results outside their bounded responsibilities;
- automation, agent output, confidence, recommendation, or repeated assertion; or
- external-system state, approval, ownership, assignment, or configuration.

None of these establishes approval, correctness, completeness, ownership, assignment, Review verdict, Finding Disposition, Finalization, permission for the next action, commit or push approval, release authority, or authority to mutate an external system.

## Authority, Relationships, Metadata, and Identifiers

Relationships may trace how a Human Decision governs a record or action, but the Human Decision supplies the authority. The relationship does not create, broaden, transfer, or validate it.

Metadata may describe authority context, and Canonical Identifiers may identify the relevant records or subjects. Neither supplies substantive authority. A correct reference improves traceability; it does not prove that the referenced authority applies to a different scope or action.

Historical authority must remain understandable when later records add context, correct information, or supersede prior material. Later activity must not present changed authority as if it had governed earlier work.

## Automation Boundary

Automation may assist with transparent, read-only, mechanical handling of authority-related context. Such assistance remains subordinate to the authoritative records and Human Decisions it references.

Automation must not infer or grant authority, make Human Decisions, approve work, determine substantive correctness, decide Review verdicts or Finding Dispositions, finalize work, change status, assign ownership, modify records, commit, push, release, or mutate external systems. A mechanical result may identify information for human attention but cannot satisfy a Human Decision Gate.

## Privacy and Safety

Authority context must not expose credentials, secrets, private keys, credentials embedded in URLs, or unnecessary personal or sensitive information. Identifying an accountable authority does not justify recording protected values or more personal information than the approved purpose requires.

Safe references, redaction, and non-sensitive descriptions should preserve accountability without compromising privacy or security. These measures do not replace human security judgment or incident response.

## Specification Boundary

Later approved tasks may define concrete specifications that represent or use authority while preserving the principles in this document and all higher-level governance. Those specifications must not convert representation, validation, workflow state, or automation into authority.

This document does not define approval procedures, workflow rules, state transitions, schemas, metadata fields, identifier syntax, directory layout, filenames, YAML, JSON, validation rules or implementation, templates, command-line behavior, automation behavior, or storage implementation.
