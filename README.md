# implemented-feature-change-handoff

A lightweight skill that keeps **changes to already implemented features** connected to the new implementation and test plans needed to realize them.

Use it at either existing work entry point:

- **Requirements/design revision:** when a change requires new implementation planning, record a temporary marker in the surviving requirements/design canon.
- **Implementation planning:** transfer the requested change to new implementation and test plans, then clear its temporary marker once the handoff is complete.

There is **one** skill definition, [`SKILL.md`](./SKILL.md), shared by both entry points. The change is allowed to exist in the authoritative requirements/design before the implementation has caught up.

## Installation in a working repository

1. Make this repository's [`SKILL.md`](https://github.com/supersovaa/implemented-feature-change-handoff/blob/main/SKILL.md) available to the AI agent through its supported skill-loading or GitHub-reading mechanism.
2. In the working repository's **existing requirements/design revision entry**, add a direct reference to that skill for changes to already implemented features.
3. In its **existing implementation-planning entry**, add a direct reference to the same skill for planning those changes.
4. Follow the working repository's established guidance layout. Use `scope-aligned-guidance` if entries need to be identified or introduced. Keep the operational rules in this skill's single canonical `SKILL.md`.

A dedicated command or separate handoff entry is not required. Both existing work types activate the appropriate part of the same skill.

## Responsibility boundaries

- [`grill-into-pr`](https://github.com/supersovaa/grill-into-pr) owns requirements/design discussion and its documentation PR.
- [`plan-driven-planning`](https://github.com/supersovaa/plan-driven-implementation/blob/main/skills/plan-driven-planning/SKILL.md) owns implementation planning.
- [`test-evidence-planning`](https://github.com/supersovaa/requirement-driven-testing/blob/main/skills/planning/SKILL.md) owns test planning.

This skill owns the temporary handoff between these phases, without changing their generic rules. Its marker is removed after planning handoff, not after the later code change.
