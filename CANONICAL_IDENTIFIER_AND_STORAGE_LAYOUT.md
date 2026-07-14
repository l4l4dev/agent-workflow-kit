# Canonical Identifier and Storage Layout Specification

## Purpose and Scope

This specification defines how Work Items and Canonical Records are identified and where their files are stored in the repository. Its purpose is to make durable project records identifiable, referenceable, discoverable, and portable without depending on chat history, agent memory, an external task manager, or a particular provider or tool.

Identifiers establish stable identity, and paths make the identified artifacts discoverable. Neither an identifier nor a path establishes authority, approval, correctness, completeness, ownership, status, workflow progression, or permission to act.

## Canonical Identifier Syntax

Canonical Identifiers use printable ASCII and are case-sensitive. Canonical forms use uppercase prefixes and the separators defined below. Two identifiers that differ in any character identify different subjects; identifiers that differ only by letter case must not both be allocated.

### Work Item Identifiers

A Work Item Identifier has this form:

```text
<work-item-prefix>-<work-item-key>
```

The Work Item prefix identifies the broad kind of bounded work:

| Prefix | Work Item kind |
|---|---|
| `TASK` | A bounded Task, including implementation or documentation work |
| `PHASE` | A Phase or a Phase Review treated as its own Work Item |
| `MILESTONE` | A Milestone or a Milestone Review treated as its own Work Item |
| `GOV` | A governance-oriented Work Item that is not better represented by another approved kind |

The Work Item key consists of one or more decimal segments separated by periods. Each segment contains one or more digits. Leading zeroes are permitted and remain significant. Examples include:

```text
TASK-2.1
TASK-012
PHASE-001
MILESTONE-001
GOV-1
```

The complete Work Item Identifier is canonical. Numeric appearance does not imply priority, chronology, hierarchy, dependency, status, or approval. Because leading zeroes are significant, `TASK-1` and `TASK-001` are distinct identifiers and must not be treated as aliases.

Work Item Identifiers are unique across the repository. An identifier allocated to one Work Item must not be reused for another Work Item, including after the original work is completed, withdrawn, renamed, or otherwise no longer current.

### Local Record Identifiers

A local Record Identifier has this form:

```text
<record-type-prefix>-<sequence>
```

The sequence is exactly three decimal digits from `001` through `999`. Sequence `000` is not valid.

Examples:

```text
DEF-001
HD-001
RV-002
```

A local Record Identifier is unique within the combination of one Work Item and one Record Type prefix. Different Record Types in the same Work Item have independent sequences.

### Fully Qualified Record Identifiers

A fully qualified Record Identifier has this form:

```text
<work-item-id>/<local-record-id>
```

Examples:

```text
TASK-2.1/DEF-001
TASK-2.1/HD-001
PHASE-001/RV-001
MILESTONE-001/RV-001
```

The fully qualified form is the Canonical Identifier of a Canonical Record. References within record content and references across Work Items must use the fully qualified form. A local Record Identifier may be used as a filename and may be used as an unambiguous shorthand within its own Work Item's immediate navigation context, but it is not globally unique by itself.

## Record Type Prefixes

The currently approved Record Types use these prefixes:

| Prefix | Record Type |
|---|---|
| `DEF` | Definition |
| `HD` | Human Decision |
| `INV` | Investigation |
| `IMP` | Implementation |
| `EV` | Evidence |
| `RV` | Review, including Independent Review and Independent Re-Review |
| `FD` | Finding |
| `FDP` | Finding Disposition |
| `RM` | Remediation |
| `FIN` | Finalization |
| `HO` | Session Handoff |

Prefixes belong to the Record Type namespace. A prefix identifies responsibility; it does not indicate approval, authority, lifecycle position, or workflow state.

## Identifier Allocation

### Work Item Allocation

Before a Work Item Identifier is used authoritatively, its complete identifier must be checked against existing repository Work Item Identifiers. Allocation is manual in this specification. A task manager, issue tracker, branch name, directory name, or automation output must not allocate or approve a Canonical Identifier implicitly.

The selected Work Item prefix must match the approved kind of work. The Work Item key is allocated within that prefix's repository-wide namespace. Existing project numbering may be continued, but a new identifier must not be treated as a child, dependency, priority, or status solely because of its numeric form.

Once a Work Item Identifier has entered authoritative repository use, changes to the Work Item's title, location, external references, or operational status must not change its identifier. Reassignment to a different subject and reuse are prohibited.

### Record Allocation

Record sequences are allocated separately for each Work Item and Record Type prefix. A new record uses an unused three-digit sequence in that local namespace. Allocation should normally use the lowest number greater than every previously allocated sequence for that Work Item and Record Type.

Gaps are permitted. A skipped, withdrawn, superseded, corrected, or otherwise historical identifier must not be reused. Sequence order may assist navigation but does not prove chronology, authority, approval, supersession, or currentness.

This specification does not provide automatic allocation. A human or agent preparing a record must inspect the relevant repository context and preserve the chosen identifier consistently, subject to the applicable Human Decision boundaries.

### Parallel-Branch Collisions

Parallel branches may independently allocate the same Work Item Identifier or the same local Record Identifier. Duplicate Canonical Identifiers must not enter the authoritative integrated repository state.

When a collision is discovered before integration:

- an identifier already present in the authoritative target branch retains its assignment;
- otherwise, one colliding allocation is selected for renumbering before integration;
- the renumbered record receives an unused identifier in the applicable namespace; and
- its filename and all references introduced with that allocation are updated consistently.

Renumbering is a deliberate integration correction, not an automatic operation. It must not silently change an identifier that has already entered authoritative use, and it must not erase evidence of an actual historical conflict when that context is material.

## External Identifiers

Identifiers assigned by issue trackers, task managers, hosting services, or other repositories are external references. They do not replace the canonical Work Item or Record Identifier, even when the external identifier is more visible operationally.

An external identifier may be associated with a Canonical Identifier for navigation. That association does not make the external system authoritative, prove that the two systems are synchronized, or authorize external-system mutation. A change to an external identifier must not silently change canonical identity.

## Future Record Type Extensions

A new Record Type and its prefix require an explicit Human Decision before authoritative use. A proposed prefix must:

- contain two through four uppercase ASCII letters;
- remain distinct from every active Record Type prefix;
- remain distinct from every retired Record Type prefix;
- remain distinct from every active Work Item prefix;
- remain distinct from every retired Work Item prefix;
- identify a responsibility not already covered by an approved Record Type; and
- remain stable after authoritative use.

The active Work Item prefixes `TASK`, `PHASE`, `MILESTONE`, and `GOV` are therefore unavailable as Record Type prefixes. A retired prefix must not be reassigned to a different Record Type or identifier kind. Adding a prefix must never reinterpret an existing identifier; it applies only to future allocations. Adding a prefix does not by itself define the new Record Type's responsibility, authorize its use, or amend existing records.

## Historical Summary

Historical Summary is a canonical glossary concept but is not currently an approved Record Type. This specification therefore assigns it no Record Type prefix, local Record Identifier, Canonical Record filename, or Record Type-specific directory.

A Historical Summary must not be given an invented Canonical Record identity or be presented as a contemporaneous record. If a future Human Decision establishes Historical Summary as a Record Type, that decision must approve its responsibility and prefix under the extension rules before the new type is used authoritatively.

## Repository Storage Layout

Canonical Records use a Work Item-centered layout:

```text
records/
└── <work-item-id>/
    ├── index.md
    └── <record-type-directory>/
        └── <local-record-id>.md
```

The Work Item directory name is the exact canonical Work Item Identifier. For example:

```text
records/TASK-2.1/
records/PHASE-001/
records/MILESTONE-001/
```

The repository must not use a global layout organized primarily by Record Type, such as `records/reviews/<work-item-id>.md`. Records belonging to a Phase Review or Milestone Review are stored under that review effort's own identifiable Work Item and reference the reviewed Work Items as needed.

## Work Item Index

Every Work Item directory contains one file named exactly:

```text
index.md
```

The index is the stable navigation entry point for its Work Item. It helps readers locate the Work Item's authoritative records without duplicating their substantive content.

The index filename has no Record Type prefix and does not receive a Canonical Record Identifier under this specification. Its existence, content, or pointers do not approve a Definition, satisfy a Human Decision Gate, establish status, or authorize a workflow transition. Concrete index metadata and content requirements belong to later approved specifications.

## Record Type Directories

Record Type-specific directories are created only when the Work Item contains a record of that type. Empty directories must not be pre-created merely to suggest completeness.

The directory names for currently approved Record Types are:

| Record Type prefix | Directory |
|---|---|
| `DEF` | `definitions/` |
| `HD` | `decisions/` |
| `INV` | `investigations/` |
| `IMP` | `implementations/` |
| `EV` | `evidence/` |
| `RV` | `reviews/` |
| `FD` | `findings/` |
| `FDP` | `dispositions/` |
| `RM` | `remediations/` |
| `FIN` | `finalizations/` |
| `HO` | `handoffs/` |

Future Record Types require an approved, unique directory name as part of their extension decision. A directory name must not be reused for a different Record Type.

## File Naming Conventions

A Canonical Record filename is its local Record Identifier followed by the lowercase Markdown extension:

```text
<local-record-id>.md
```

Examples:

```text
DEF-001.md
HD-001.md
RV-002.md
```

The canonical path of a Record is therefore:

```text
records/<work-item-id>/<record-type-directory>/<local-record-id>.md
```

Example:

```text
records/TASK-2.1/decisions/HD-001.md
```

Directory and filenames use only the ASCII characters already present in their canonical components, plus `/`, `-`, `.`, and the lowercase `.md` extension. Paths must not contain spaces, platform-specific separators, control characters, credentials, secrets, private keys, credential-bearing URLs, or unnecessary personal or sensitive information.

Canonical paths must not rely on case-only distinctions. File and directory names must be usable in common Git environments with case-sensitive or case-insensitive filesystems.

## Identifiers and Paths

The Canonical Identifier is the durable identity; the path is its repository location. A record filename carries the local Record Identifier, while its parent Work Item directory and Record Type directory provide discoverable storage context.

Moving or renaming a file must not silently reassign canonical identity. A path that conflicts with the record's Canonical Identifier is an inconsistency to be surfaced, not evidence that identity changed. Derived indexes, links, and external mappings remain subordinate to the authoritative record identity and repository governance.

Files and directories are containers and navigation aids. Their presence, absence, ordering, or apparent completeness does not establish authority, approval, correctness, status, Review verdict, Finding Disposition, Finalization, or workflow transition.

## Specification Boundaries

This specification defines identifiers and storage layout only. It does not define Canonical metadata fields, YAML, JSON, front matter, record templates, validation implementation, command-line behavior, automatic allocation, automatic renumbering, workflow mechanics, approval procedures, status automation, commit or push automation, external-system mutation, or provider-specific behavior.
