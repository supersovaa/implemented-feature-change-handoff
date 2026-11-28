---
name: implemented-feature-change-handoff
description: Use when revising feature requirements or design, or when planning implementation of a feature revision. Track work owed by an existing implementation.
---

# Implemented Feature Change Handoff

When the feature is already implemented and the revision leaves implementation or test planning outstanding, use the entry point below for the current phase. Its existing owner retains responsibility for the requirements, design, or plan.

## When revising requirements or design

Use `grill-into-pr` for the requirements/design decisions and documentation-only PR when that workflow applies.

Treat settled requirements and revised design as the target. Existing code and tests are evidence of current behavior when consulted, rather than authority for preserving a feature, mechanism, or guarantee removed from the target.

When the change leaves implementation work that still needs a new plan, put a concise **`変更未計画`** marker in the relevant surviving requirements/design canon. Identify the intended change; detailed code and test impact analysis belongs to implementation planning.

For example: `復旧機能の削除：変更未計画`.

If the entire section describing a removed feature is deleted, put the marker in the surviving parent or nearest relevant section. Keep it near the change rather than creating a separate tracking document.

Use markers for changes requiring unplanned implementation work; ordinary editorial changes and work already fully accounted for in an applicable plan need no marker. The changed requirements/design remain authoritative while the old implementation still exists.

## When planning implementation

Work on the **requested** change and its associated marker(s). Other unplanned changes retain their own markers and do not block unrelated work.

Use the latest relevant repository state, settled requirements/design, and existing implementation/tests to identify the delta needed for the requested change, including removal of behavior or tests that no longer belong to the target. Treat completed historical implementation plans as context rather than automatically reopening them.

Use `plan-driven-planning` to create new, repository-persistent implementation plans covering the required delta and assigning each part to a plan. Use `test-evidence-planning` to establish the required test definitions and regression scope, recorded and linked to the plans before implementation readiness.

Remove each scoped `変更未計画` marker once all of its required implementation changes have planned owners and the corresponding test planning is complete. Keep a marker while any of those obligations remains unassigned or unfinished. The repository's normal revision history preserves the design change after the temporary marker is removed.

This skill owns only the handoff. `grill-into-pr` owns design resolution and its PR; `plan-driven-planning` owns implementation plans; `test-evidence-planning` owns test definitions. Implementation and executable test changes belong to their respective execution skills.
