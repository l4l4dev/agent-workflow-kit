# Project Constitution

## 1. Purpose

`agent-workflow-kit` is a provider-neutral, repository-first workflow kit for AI-assisted software development. It exists to preserve investigation, human decisions, implementation records, evidence, independent review, remediation, independent re-review, finalization, deferred items, and session handoff as durable project records. It supports accountable human-led work; it is not an autonomous software-development system or a task-management system.

## 2. Repository as the Source of Truth

The repository is the authoritative source for approved project state. Material conclusions, decisions, evidence, review outcomes, and handoff information must be recorded in reviewable repository artifacts before they are treated as established project state. Chat history, transient tool output, and agent or human memory are contextual aids only and must not be treated as authoritative records.

## 3. Human Authority and Decision Gates

Humans retain final decision authority and accountability. AI may investigate, identify alternatives, explain trade-offs, and prepare recommendations, but it must not independently finalize significant decisions.

Explicit Human Decision Gates are required for architecture, breaking changes, legal or licensing matters, security policy, public release, external dependency adoption, data migration, governance, and major scope changes. For each such decision, a human must make and record the final decision before dependent work is treated as approved.

## 4. Separation of Implementation and Review

Implementation and Independent Review must be separate roles for work requiring independent verification. A reviewer must assess the work independently of the implementer's conclusions. AI self-assessment, including a second pass by the same acting implementer, is not Independent Review. Review findings, remediation, and any required Independent Re-Review must remain traceable.

## 5. Evidence-Based Verification

AI output and confidence are claims, not evidence of correctness. Claims about behavior, quality, completion, security, or compliance must be distinguished from recorded evidence. Verification should use evidence appropriate to the claim, and limitations or missing evidence must be stated. This workflow does not guarantee correctness, security, or compliance.

## 6. Provider Neutrality

Project principles and durable records must not depend on a particular AI provider, model, product, or proprietary interaction format. Provider-specific capabilities may assist work only when they do not become prerequisites for interpreting the authoritative project record.

## 7. Constrained Automation

Automation must default to minimal, transparent, mechanical assistance. It must remain subordinate to human authority and recorded decisions. Automatic mutation of external systems is outside the project's initial boundary; any future expansion of that boundary requires an explicit Human Decision and safeguards proportionate to the impact.

## 8. Safe and Traceable Records

Repository records must protect privacy and must never contain credentials or secrets. Personal data and other sensitive information may be recorded only when necessary, authorized, and appropriately protected. Sensitive values must be excluded, redacted, or represented by safe references appropriate to their handling requirements.

Changes must be small enough to review, attributable to a clear purpose, and traceable through their rationale, evidence, and review history. Deferred work and unresolved limitations should be recorded explicitly rather than implied to be complete.

## 9. Amending This Constitution

This constitution is the project's highest-level governance document. Any amendment must receive explicit human review and approval and must be recorded as a focused, reviewable change with its rationale. No AI system or automated process may approve or enact a constitutional change on its own.
