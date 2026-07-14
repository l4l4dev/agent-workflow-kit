# Temporary Bootstrap Human Decision — TASK-2.2 Architecture

## Status and Limitation

This document is temporary bootstrap governance. It records a Human Decision required by the committed `BOOTSTRAP_TASK_2_2.md` while the canonical DEF and HD mechanisms are not yet available.

This document is not a canonical `HD` record and is not a canonical `DEF` record. It must remain historically distinguishable from future Canonical Records and must not later be represented as a Canonical Record that existed at this time.

The existence of this document in the working tree does not authorize TASK-2.2 Implementation. This decision becomes authoritative only after Independent Review, any required remediation and Independent Re-Review, Finalization Assessment, explicit Human commit approval, and entry into the authoritative committed repository state.

## Governed Work Item

`TASK-2.2 — Canonical Metadata Specification and DEF/HD Templates`

## Decision

The human owner approves the architecture stated in this document for TASK-2.2 Implementation, subject to the Effective Condition below. No architecture choice beyond the Approved Architecture is approved.

## Approved Architecture

1. Canonical metadata shall use constrained YAML front matter followed by a Markdown body.

2. The YAML subset shall allow only:

   - double-quoted string scalar values;
   - sequences of double-quoted strings.

3. The YAML subset shall prohibit:

   - multiline scalar values;
   - nested objects;
   - booleans;
   - numbers;
   - native YAML dates or timestamps;
   - anchors;
   - aliases;
   - tags;
   - merge keys;
   - free-form substantive prose.

4. Shared metadata shall contain:

   Required:

   ```text
   record_id
   ```

   Optional:

   ```text
   created_on
   supersedes
   corrects
   withdraws
   ```

5. `created_on` is optional and, when present, uses a double-quoted `YYYY-MM-DD` string. It does not establish approval, chronology precedence, currentness, or authority.

6. The following are not included in the M1 shared metadata:

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

7. DEF shall introduce no DEF-specific metadata fields.

8. DEF approval shall be determined through:

   - an authoritative Human Decision whose body explicitly approves the fully qualified DEF identifier; and
   - the minimum navigation references in `index.md`.

   DEF metadata, path, filename, template use, or index pointer does not create approval.

9. The DEF template shall contain:

   Required body sections:

   ```text
   Objective
   Approved Scope
   Explicit Non-Goals
   Acceptance Criteria
   Constraints
   ```

   Optional predefined body section:

   ```text
   Assumptions
   ```

10. When no Constraints exist, the DEF shall state:

    ```text
    None.
    ```

11. The HD-specific metadata shall contain these required fields:

    ```text
    governed_subjects
    decision_authority
    ```

12. `governed_subjects` shall contain a sequence of Canonical Work Item Identifiers or fully qualified Canonical Record Identifiers.

13. `decision_authority` shall contain a safe human-readable role or repository-approved designation.

    It must not require or contain:

    - credentials;
    - secrets;
    - private keys;
    - credential-bearing URLs;
    - unnecessary personal information;
    - email addresses;
    - provider identities;
    - external account identifiers.

14. The HD template shall contain:

    Required body sections:

    ```text
    Decision
    Rationale
    Scope and Limitations
    Effective Condition
    ```

    Optional predefined body section:

    ```text
    Consequences
    ```

15. For a Definition approval, the HD body's `Decision` section must explicitly identify and approve the fully qualified DEF identifier. Metadata references alone do not establish approval.

16. The TASK-2.2 requirement for `index.md` is limited to these two navigation references:

    ```text
    Governing Definition: <fully-qualified-def-id>
    Approving Human Decision: <fully-qualified-hd-id>
    ```

17. TASK-2.2 must not define general `index.md` content, including:

    - summaries;
    - status;
    - priority;
    - assignment;
    - workflow state;
    - record inventory;
    - latest-review pointers;
    - derived metadata;
    - approval behavior;
    - transition behavior.

18. None of the following alone creates authority or approval:

    - YAML front matter;
    - metadata fields;
    - `record_id`;
    - `governed_subjects`;
    - `decision_authority`;
    - relationship fields;
    - template use;
    - file presence;
    - path;
    - filename;
    - index pointers.

    Authority derives from the explicit Decision made by an authorized human and preserved in the Human Decision record.

## Not Approved

No additional architecture choice is approved. In particular, this decision does not approve:

- additional metadata fields;
- DEF-specific metadata;
- templates for other Record Types;
- actual records under `records/`;
- retrospective DEF or HD records;
- Historical Summary as a Record Type;
- general index design;
- validation rules or implementation;
- CLI behavior;
- automatic allocation or generation;
- workflow transitions;
- status automation;
- commit or push automation;
- external-system mutation;
- provider-specific behavior;
- modification of `CANONICAL_LIFECYCLE.md`;
- modification of the committed identifier and storage specification.

Any change outside the approved architecture requires a separate explicit Human Decision.

## Decision Authority

`Human owner`

No personal name, email address, signature, timestamp, identifier, or external account is asserted by this artifact.

## Scope and Limitations

This decision authorizes only the architecture choices required for TASK-2.2 and does not amend previously approved governance. It does not authorize Implementation beyond the approved TASK-2.2 deliverables. It does not approve Implementation results, create authority through metadata or file placement, or waive any required review, remediation, finalization-assessment, commit-approval, or repository-entry condition.

## Effective Condition

This decision authorizes TASK-2.2 Implementation only after:

- this artifact completes Independent Review;
- any adopted Findings are remediated and independently re-reviewed;
- Finalization Assessment reports readiness;
- the human owner explicitly approves the commit; and
- this artifact enters the authoritative committed repository state.

Until every condition is satisfied, TASK-2.2 Implementation must not begin or resume under this decision.

## Future Canonical Transition

This temporary artifact remains historical bootstrap governance and must not be relabeled as a canonical `HD`. TASK-2.2 Implementation must use the approved architecture prospectively. Later Canonical Records must not claim that a canonical HD existed at this earlier point.
