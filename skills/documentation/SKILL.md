---
name: project-documentation
description: Use when creating or updating project progress records, decision logs, demo guides, architecture diagrams, or production-readiness documents.
---

# Documentation Skill

Use this skill during an approved project implementation. Do not create project records for a planning-only chat or an instruction-file update. Read the root `AGENTS.md` and the writing skill. Apply ASD-STE100 to every project-authored document.

## Project records

Create these files after design approval and before implementation begins:

- `docs/BUILD_PROGRESS.md` records the goal, approved scope, current status, milestones, and file-by-file changes.
- `docs/DECISION_LOG.md` records durable, cross-cutting decisions and their trade-offs.
- `docs/DEMO_GUIDE.md` explains the implemented project from a demo user's point of view.

Use these structures:

```markdown
# Build Progress
## Goal
## Approved scope
## Current status
- Completed:
- In progress:
- Next:
- Blockers:
## Milestones
## File-by-file implementation record
### [Milestone name]
**User-visible result:** [What a user can now do or understand.]
**Architecture impact:** [Which boundary, dependency, or data flow changed.]

| File | Role in the flow | Change and reason | Connections or impact | Evidence / status | Decision |
```

```markdown
# Decision Log
## [Decision name]
- Date:
- Decision:
- Why this decision fits the approved requirements:
- Alternative considered:
- Why the alternative was not selected:
- Code and architecture affected: [Modules, routes, components, API contracts, data models, migrations, services, or diagrams. Explain how each is affected.]
- Production fit and limits:
- Scaling path and the condition that would justify it:
- Trade-offs:
```

```markdown
# Demo Guide
## Demo overview
## Setup
## Demo flow
| Step | Action to show | Expected result | Files used |
## File-by-file implementation and use
| File | Responsibility | Place in the user flow | Related files or dependencies | What to show in the demo |
## Limits and follow-up work
```

Update `BUILD_PROGRESS.md` at each implementation milestone and before a pause. Start each milestone with the user-visible result and architecture impact. Add one chronological row for each file created, changed, or removed. For each file, explain its responsibility, what changed, why it changed, and how it connects to other files or the user flow. Record evidence or mark it as unchecked. Link the entry to a design decision when one applies. Use direct language and define technical terms when they first appear. Do not use a file path as the full explanation. Do not rewrite history.

Record each durable design decision in `DECISION_LOG.md` when the user approves it or when the architecture or scope changes. For every decision, explain why it fits the approved requirements, which reasonable alternative you considered and why you did not select it, which code and architecture parts it affects, and how the choice behaves in production. Name affected modules, routes, components, API contracts, data models, migrations, services, or diagrams when they apply. Explain the relationship; do not only list paths. State the scaling path and the observable condition that would justify it. Separate verified facts from recommendations. Do not invent traffic targets, performance limits, or reliability guarantees. Keep implementation history in `BUILD_PROGRESS.md`. Link progress entries to relevant decisions.

Start `DEMO_GUIDE.md` with the intended demo flow. Update it after each milestone and before a pause. Keep it current until all approved requirements are complete. Explain every project-owned file created or changed. State each file's responsibility, where it fits in the user flow, how it connects to related files, and what the demo user can observe because of it. Include setup commands, demo actions, expected results, limitations, and supporting files that are not visible in the interface. Organize the guide around demo steps. Use plain language and define technical terms. Do not copy source code or turn the guide into a work log. Verify it against the final implementation before marking it complete.

## Architecture files

Use Mermaid source unless the project has an established diagram format. Create:

- `docs/architecture/README.md` for system boundaries, module ownership, dependency direction, and diagram maintenance.
- `docs/architecture/system-context.mmd` for users, the application, and external systems.
- `docs/architecture/module-map.mmd` for the frontend, backend modules, services, and data stores when those boundaries help maintain the code.
- `docs/architecture/data-flow.mmd` for the main user flow through input, validation, business logic, persistence, and response. Include important external calls and failure paths.

Draft diagrams from the approved design. Show the relevant code modules and dependency direction. Add source paths to module descriptions or labels when the paths are verified. Update diagrams when implementation changes. Before completion, compare them with the routes, service modules, database models, and frontend flow. State any diagram that you could not check. Do not add a renderer dependency only to export an image unless the user needs that format.

## Production-readiness handoff

At project completion, create `docs/operations/production-readiness.md`. Separate observed facts, assumptions, recommendations, and remaining work. Include:

- The deployed or proposed system shape and current readiness status.
- Expected traffic, data volume, and reliability targets. State when these are unknown.
- Scaling options and the evidence or thresholds that would justify them.
- Failure modes, timeouts, retry and idempotency needs, and recovery steps.
- Health checks, logs, metrics, alerts, and incident ownership.
- Database backup, restore, migration, and connection-capacity needs.
- Security and secret-management gaps.
- Known limits, open decisions, and prioritized work before launch.

Do not invent load targets, SLOs, recovery objectives, or guarantees. Do not claim production readiness from code review alone. Do not deploy infrastructure or expand approved scope to address a recommendation. Record that work as a recommendation until the user approves it.

## HTML code walkthrough

When the user asks for a website that explains an existing codebase, use [the HTML code walkthrough prompt](references/html-code-walkthrough.md). Inspect the supplied source before writing the page. Save one self-contained `index.html` in the requested output location. If the user does not specify a location, place it under `docs/code-walkthrough/` when that folder fits the repository. Do not change application code. Verify setup commands against repository files. State whether you ran each command. Label claims that the source does not confirm. Do not include secrets or sensitive values.
