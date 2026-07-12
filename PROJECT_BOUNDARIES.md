# Project Boundaries

## Purpose of This Document

This document defines the initial product scope of `agent-workflow-kit`. It applies the principles established by `PROJECT_CONSTITUTION.md` without replacing or restating its governance role. The project is a provider-neutral, repository-first workflow kit for accountable, human-led, AI-assisted software development.

## Initial Product Scope

The initial product may provide:

- provider-neutral workflow documentation;
- reusable record specifications and templates;
- reusable AI prompt templates;
- session handoff guidance and templates;
- canonical vocabulary and adoption guidance;
- examples for different project types;
- lightweight, read-only mechanical validation; and
- optional guidance for coexistence with task-management systems.

These materials should help teams preserve durable, reviewable project state in their repositories without requiring a particular provider, development environment, hosting service, or task-management system.

## Explicit Non-Goals

The initial product must not include:

- autonomous software-development agents;
- AI provider API integrations;
- automatic Human Decisions or approvals;
- automatic completion of Acceptance Criteria;
- automatic review verdicts or finding dispositions;
- automatic finalization or status transitions;
- automatic commits, pushes, releases, or external-system mutations;
- a replacement task-management system;
- a large workflow engine or large CLI;
- mandatory integration with any task-management system; or
- a required dependency on `fj` or any other project.

The project does not guarantee correctness, security, compliance, or audit completeness.

## Human-Controlled Boundaries

Humans must retain explicit control over decisions, approvals, review verdicts, finding dispositions, finalization, releases, and changes to external systems. Automation must not infer that a decision or approval is valid from the presence of a file, field, status, or validation result.

Initial automation must be limited to transparent, mechanical assistance, such as checking required files or sections, identifier format and duplication, broken internal references, unresolved placeholders, structural completeness, and possible credential or secret patterns. Such checks may identify issues for human attention but must not judge the substantive validity of a Human Decision, approval, review verdict, disposition, or finalization.

## Task-Management Integration Boundary

The project may coexist with Backlog.md, GitHub Issues, GitHub Projects, Jira, Linear, plain Markdown task lists, or other task-management approaches. These systems may manage operational information such as priority, assignment, scheduling, notifications, discussion, and board status.

No external task-management system is mandatory. The main Git repository must retain the durable approved project state needed for recovery and audit, even when an external system is unavailable. Integration guidance must preserve this authority boundary and must not redefine the project as a task-management replacement.

## External-System Mutation Boundary

Automatic external-system mutation is outside the initial scope. This includes changing issues, boards, repositories, releases, deployment systems, or other remote state. Guidance may describe human-controlled interaction with external systems, but the initial product must not perform such mutations automatically.

GitHub Wiki is not a Source of Truth. It may be considered later as an optional publication surface or generated mirror only if the main Git repository remains authoritative. Wiki publication tooling is outside the initial scope.

## Relationship with `fj` and Other Projects

`fj` is an origin of practical experience and may provide examples, but it is not a Source of Truth for `agent-workflow-kit`. `agent-workflow-kit` is not currently a dependency of `fj`, and it must not require `fj` or another project to operate.

Assets from `fj` must be analyzed and generalized before reuse. Automatic synchronization and cross-repository mutation are outside the initial scope. Any future adoption by `fj` requires a separate investigation and Human Decision.

## Conditional Future Capabilities

New capabilities may be considered only after real usage demonstrates a recurring need. In particular, a small tool may be considered when repeated manual work provides evidence that tooling would reduce error or maintenance cost. A CLI is not part of the initial product, and this document does not define one.

Future consideration does not imply approval. Capabilities must be introduced incrementally and should avoid speculative abstraction, premature tooling, unnecessary platform coupling, and expansion into autonomous operation.

## Boundary Changes

Any material expansion or change to these boundaries requires explicit human review and a recorded Human Decision. A boundary change must remain consistent with `PROJECT_CONSTITUTION.md`; it must not be established by automation, implementation alone, or external-system configuration.
