# Repository Agent Rules

## Purpose and Authority

This document defines how AI agents must work in the `agent-workflow-kit` repository. It operationalizes, but does not redefine, the project's approved governance and product boundaries. It applies without dependence on a particular provider, model, IDE, or agent product.

Conflicting instructions must be resolved in this order:

1. Human instructions
2. `PROJECT_CONSTITUTION.md`
3. `PROJECT_BOUNDARIES.md`
4. `AGENTS.md`
5. Approved Work Item definitions
6. Implementation

An agent must surface conflicts between authoritative sources for Human Decision and must not resolve them by assumption.

## Source of Truth

The repository is the Source of Truth for approved project state. Chat history and agent memory are context only and are not authoritative. A new session must recover state from repository artifacts rather than continue from chat history alone.

An agent must not invent files, records, approvals, decisions, evidence, or repository state. Uncertain or unavailable information must be reported explicitly.

## Before Starting Work

Before acting, an agent must:

- inspect the repository tree and Git status;
- read the authoritative documents relevant to the task;
- identify the approved scope and explicit non-goals;
- identify staged, modified, and untracked user-owned changes; and
- confirm the assigned task and role.

Existing user changes must be preserved unless their modification is explicitly authorized.

## Scope and Task Execution

An agent must work on one approved task and one assigned role at a time. It must make only the smallest change required by the approved scope and must not perform opportunistic refactoring, unrelated cleanup, or work intended for another task or phase.

Approval for one task, role, phase, file, or operation must not be treated as approval for another. If the approved scope is insufficient, conflicts with an authoritative source, or requires expansion, the agent must stop and request Human Decision before proceeding.

Only files explicitly authorized by the task may be created or modified. Existing files must be inspected before editing.

## Human Decision Gates

Explicit human approval is required before:

- implementation following an Investigation or design proposal;
- architecture decisions;
- breaking changes;
- security-policy decisions;
- legal or licensing decisions;
- public release;
- external dependency adoption;
- data migration;
- governance changes;
- major scope changes;
- destructive or irreversible operations;
- external-system mutation;
- commit; or
- push.

An agent may investigate, compare alternatives, explain trade-offs, and prepare recommendations, but it must not make or imply the Human Decision.

## Role Separation

Roles must remain distinct:

- **Investigation:** read-only analysis that may present facts, alternatives, trade-offs, and recommendations. It must not implement or make Human Decisions.
- **Implementation:** changes only the files and behavior authorized by the approved task.
- **Independent Review:** read-only assessment by a reviewer separate from the implementation role. The reviewer must not modify the reviewed implementation. Implementation self-assessment is not Independent Review.
- **Remediation:** changes only findings explicitly adopted by a human and must not address deferred, rejected, or unrelated findings.
- **Independent Re-Review:** read-only verification of adopted remediation by an independent reviewer when required. It must not perform further remediation.
- **Finalization Assessment:** determines readiness from approved scope, evidence, reviews, and dispositions. It does not itself finalize through a commit or push.

Remediation must be followed by Independent Re-Review when the approved workflow requires it. A role must stop after producing its assigned output and must not silently continue into the next role.

## Verification and Evidence

Agents must distinguish claims from Evidence and must not treat agent confidence or AI output as Evidence of correctness.

Reports must identify commands and checks actually executed and distinguish them from proposed or skipped checks. An agent must not claim that a test, validation, or other check passed unless it ran successfully. Failures, limitations, skipped checks, unavailable Evidence, and unverified items must be reported accurately.

## File and Git Safety

Before completing work, an agent must inspect the complete diff and verify that only approved files changed. Untracked files must be accounted for explicitly because ordinary `git diff` may not display them.

An agent must not delete files, rewrite Git history, discard user changes, or force-push without separate explicit human approval. Destructive operations require their own Human Decision even when another task has been approved.

## Privacy and Security

Agents must never record credentials, secrets, private keys, or credentials embedded in URLs. Personal and other sensitive information must be minimized and may be recorded only when necessary, authorized, and appropriately protected. Safe references, redaction, and non-sensitive placeholders must be used where appropriate.

Suspected secret exposure must be reported immediately. An agent must not rewrite history, rotate or revoke credentials, or perform other credential-response actions without explicit Human Decision.

## External Systems

Agents must not automatically mutate GitHub Issues or Projects, Backlog.md, Jira, Linear, GitHub Wiki, releases, external repositories, or any other remote system. Read-only inspection may be used only when explicitly authorized and necessary for the approved task.

Provider-specific supplements or integrations require a separate approved task and must not be introduced implicitly.

## Commit and Push

Implementation completion and Finalization readiness do not imply commit approval. Commit and push are separate actions, and each requires explicit human approval.

Before an approved commit, only approved files may be staged, and the staged file list and complete staged diff must be inspected. Approval to commit does not authorize push.

## Session Recovery

When resuming work, an agent must:

1. inspect Git status and the repository tree;
2. read `PROJECT_CONSTITUTION.md`;
3. read `PROJECT_BOUNDARIES.md`;
4. read `AGENTS.md`;
5. locate the approved Work Item definition or explicit task instructions;
6. identify the current workflow phase and assigned role;
7. read only the records needed to resume safely; and
8. avoid continuing from chat history alone.

Until the Canonical Record Model is implemented, bootstrap tasks rely on available committed governance files and explicitly supplied task instructions. Agents must not invent record paths or assume missing records exist.

## Stop and Report

After completing the requested task or role, an agent must stop and report:

- task and role;
- files changed;
- work completed;
- verification performed and commands actually run;
- results, failures, limitations, and unverified items;
- unresolved findings or decisions;
- current Git state;
- recommended next action; and
- a recommended commit message when applicable.

An agent must not automatically begin the next task, role, implementation phase, commit, or push.
