# Canonical Metadata Specification

## Purpose and Scope

This specification defines the concrete metadata representation shared by Canonical Records and the metadata that applies to Definition (`DEF`) and Human Decision (`HD`) records. It makes identity, traceability, historical context, and bounded decision authority reviewable in plain text while preserving the responsibilities and authority boundaries of the Canonical Record Model.

This specification applies prospectively. It does not relabel temporary bootstrap governance as Canonical Records or imply that a Canonical Record existed before it was created. It does not define metadata for other Record Types, validation implementation, command-line behavior, automation, workflow transitions, status behavior, or external-system mutation.

## Record Representation

A Canonical Record uses constrained YAML front matter followed by a Markdown body. The front matter begins and ends with a line containing exactly three hyphens:

```yaml
---
record_id: "TASK-2.2/DEF-001"
---
```

The YAML front matter contains concise metadata only. Substantive record content belongs in the Markdown body.

### Permitted YAML Subset

Metadata values use only:

- double-quoted string scalars; and
- sequences of double-quoted strings.

The YAML front matter does not use:

- multiline scalars;
- nested objects;
- booleans;
- numbers;
- native YAML dates or timestamps;
- anchors;
- aliases;
- tags;
- merge keys; or
- free-form substantive prose.

Dates are strings rather than native YAML dates. Identifiers are strings even when they contain numeric segments.

## Shared Metadata

Shared fields retain the same meaning wherever they are used. `record_id` is required. Every other shared field is optional and is omitted when it does not apply.

| Field | Requirement | Value | Purpose and interpretation |
|---|---|---|---|
| `record_id` | Required | Double-quoted string containing the record's fully qualified Canonical Record Identifier | Establishes the stable repository identity of the record. It must agree with the Work Item directory, Record Type directory, and local Record Identifier filename defined by `CANONICAL_IDENTIFIER_AND_STORAGE_LAYOUT.md`. Identity does not establish approval, authority, correctness, completeness, or currentness. |
| `created_on` | Optional | Double-quoted `YYYY-MM-DD` string | Records the calendar date on which the record was created for historical interpretation. It does not establish approval, chronological precedence, currentness, or authority. |
| `supersedes` | Optional | Sequence of double-quoted fully qualified Canonical Record Identifiers | Identifies earlier records whose responsibility is prospectively replaced by this record within the meaning stated in the Markdown body. The relationship does not erase or rewrite either record's historical meaning and does not create authority. |
| `corrects` | Optional | Sequence of double-quoted fully qualified Canonical Record Identifiers | Identifies earlier records for which this record supplies a correction described in the Markdown body. The earlier record remains historically distinguishable, and the relationship does not create authority. |
| `withdraws` | Optional | Sequence of double-quoted fully qualified Canonical Record Identifiers | Identifies records whose content is withdrawn within the meaning and limits stated in the Markdown body. The relationship does not delete historical context or create authority. |

Relationship fields contain Canonical Record references, not external identifiers. Their presence communicates traceability only. The Markdown body remains responsible for explaining the substantive meaning and limits of a supersession, correction, or withdrawal.

The M1 shared metadata does not include:

```text
record_type
work_item_id
title
authorship
recorder
status
revision
generic relationships
external references
```

Record Type and Work Item context are recoverable from `record_id` and the canonical storage path. Titles and substantive explanations belong in the Markdown body. Authorship, recorder, status, revision, generic relationships, and external references are not part of M1 metadata.

## Definition Metadata

A Definition introduces no DEF-specific metadata fields. Its front matter uses only the shared metadata defined above.

The `DEF` template requires these Markdown body sections:

```text
Objective
Approved Scope
Explicit Non-Goals
Acceptance Criteria
Constraints
```

It also provides this optional predefined section:

```text
Assumptions
```

When no Constraints apply, the `Constraints` section contains exactly:

```text
None.
```

A Definition does not approve itself. Approval requires an authoritative Human Decision whose `Decision` section explicitly identifies and approves the fully qualified DEF identifier, together with the minimum navigation references in the Work Item's `index.md`. DEF metadata, path, filename, template use, or an index pointer does not create approval.

## Human Decision Metadata

An HD uses the shared metadata and adds both of the following required fields:

| Field | Requirement | Value | Purpose and interpretation |
|---|---|---|---|
| `governed_subjects` | Required | Sequence of double-quoted Canonical Work Item Identifiers or fully qualified Canonical Record Identifiers | Identifies the bounded subjects governed by the decision. A reference does not by itself approve the subject, broaden the decision, or transfer authority. |
| `decision_authority` | Required | Double-quoted safe human-readable role or repository-approved designation | Identifies the accountable human authority in a durable, reviewable form. The field records authority context but does not create or prove authority by itself. |

`decision_authority` does not require or contain credentials, secrets, private keys, credential-bearing URLs, unnecessary personal information, email addresses, provider identities, or external account identifiers.

The `HD` template requires these Markdown body sections:

```text
Decision
Rationale
Scope and Limitations
Effective Condition
```

It also provides this optional predefined section:

```text
Consequences
```

When an HD approves a Definition, its `Decision` section explicitly identifies and approves the fully qualified DEF identifier. Listing that identifier in `governed_subjects`, another metadata field, or an index pointer is not approval.

A Human Decision cannot be inferred from authorship, file presence, Implementation activity, metadata, template use, or automation. Authority derives from the explicit decision made by an authorized human and preserved in the HD body within its stated scope and limitations.

## Minimum Work Item Index References

For a Work Item governed by a Definition approved by a Human Decision, `index.md` contains these two navigation references:

```text
Governing Definition: <fully-qualified-def-id>
Approving Human Decision: <fully-qualified-hd-id>
```

These references use fully qualified Canonical Record Identifiers. They help a reader locate the governing records but do not duplicate their substantive content or create approval, authority, status, or a workflow transition.

This specification defines no other `index.md` content. In particular, it does not define summaries, status, priority, assignment, workflow state, record inventory, latest-review pointers, derived metadata, approval behavior, or transition behavior.

## Identifiers, Paths, and Templates

Canonical Work Item and Record references use the syntax defined by `CANONICAL_IDENTIFIER_AND_STORAGE_LAYOUT.md`. References to Canonical Records use fully qualified Canonical Record Identifiers.

The templates are instantiated at the canonical paths defined by that specification:

```text
records/<work-item-id>/definitions/<local-def-id>.md
records/<work-item-id>/decisions/<local-hd-id>.md
```

The template files are reusable source material and are not themselves Canonical Records. Copying or completing a template, placing a file at a canonical path, assigning an identifier, or adding an index pointer does not establish authority or approval.

## Authority, History, and Safety Boundaries

Metadata, identifiers, paths, filenames, relationships, template use, file presence, and index pointers do not establish or imply authority, approval, correctness, completeness, Evidence, a Review verdict, a Finding Disposition, Finalization, status, workflow progression, or permission for another action.

Metadata preserves historical context without rewriting it. A superseding, correcting, or withdrawing record remains distinct from the records it references. Temporary bootstrap governance remains historical bootstrap governance and must not be relabeled or represented as a canonical `DEF` or `HD` that existed earlier.

Metadata must not contain credentials, secrets, private keys, credential-bearing URLs, or unnecessary sensitive or personal information. External identifiers remain external operational references and do not replace Canonical identity or make an external system authoritative.

## Extension Boundary

Later approved Record Type templates may reuse the shared metadata fields with exactly the meanings defined here. A later template may add Record Type-specific metadata only through its own approved scope and Human Decision. It must not redefine shared fields or infer authority from metadata.

Historical Summary is not an approved Record Type and receives no template or Canonical metadata identity under this specification.

This specification does not define templates for Record Types other than `DEF` and `HD`, actual records under `records/`, retrospective records, validation rules or implementation, a CLI, automatic generation or allocation, workflow transitions, approval procedures, status automation, commit or push automation, external-system mutation, or provider-specific behavior.
