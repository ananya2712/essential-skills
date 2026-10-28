---
name: full-stack-project-workflow
description: Use when taking an approved full-stack application from design through implementation, verification, and handoff in this project.
---

# Full-Stack Project Workflow

Use this skill for end-to-end application work in this project. Read the root `AGENTS.md` first. It contains the approved stack and user decisions. Read the focused skill files listed below when their work begins.

## Load the focused skills

- Read [`../backend/SKILL.md`](../backend/SKILL.md) for Flask, API, database, and integration work.
- Read [`../frontend/SKILL.md`](../frontend/SKILL.md) for Next.js, React, TypeScript, Tailwind, and UI work.
- Read [`../documentation/SKILL.md`](../documentation/SKILL.md) when creating or updating project records, diagrams, or the production handoff.
- Read [`../writing/SKILL.md`](../writing/SKILL.md) when writing project prose, interface text, comments, docstrings, or slide text.
- Read [`../presentation/SKILL.md`](../presentation/SKILL.md) at project completion when creating the final deck.

Load only the focused skills that apply to the current task. For full-stack implementation, use the backend and frontend skills together. Do not repeat their detailed rules here. Follow `AGENTS.md` when it sets a project-specific choice.

## Workflow

1. Inspect the repository and current stack. Learn the users, problem, inputs, outputs, constraints, and features that must wait. Read affected code. Trace its callers, data flow, configuration, and UI. Check for broken behavior, data loss, and data exposure.
2. Discuss the architecture, API, data model, frontend flow, reusable UI foundation, local run method, documentation, production handoff, and test scope. Explain important trade-offs. Mark unapproved choices as recommendations.
3. Present the proposed design in a concise summary. Include scope, exclusions, user flow, architecture, API, data, frontend, UI, local run, documentation, tests, and open questions.
4. Get user approval before writing application code, creating project scaffolding, or installing dependencies. If the user changes the design, revise the summary and get approval again.
5. After approval, create the progress and decision records, the initial demo guide, and the initial architecture diagrams. Follow the documentation skill.
6. Write a short milestone plan. Build the smallest complete user flow first. Reuse project code, platform features, and installed dependencies. Do not add options, abstractions, or dependencies for unapproved future needs.
7. At each milestone, update the project records and demo guide. Review the changed files and connected callers. Preserve required validation and error handling. Report progress in plain language.
8. Do not write or run automated application tests until all approved functionality is complete. Do not use test-driven development. Then run only the agreed test types from `AGENTS.md`. Use a separate test database. Do not use production data or live provider accounts.
9. Verify the agreed behavior. Check that Docker Compose starts the local app, the main user flow works, and saved data remains after restart. Compare architecture diagrams with the implementation. Inspect the affected code path, not only the diff. Report commands, observed results, unchecked items, and known risks.
10. Verify the demo guide against the final implementation. Create the production-readiness handoff. Mark the demo guide complete only when all approved requirements are complete and the guide matches the observed project.
11. After implementation and final verification, create `docs/PROJECT_DEMO.pptx` with the presentation skill. Use the approved template and seven-slide sequence. Use observed project evidence. Add speaker notes. Inspect every slide and verify the template terms and credits. Record the deck in the project records and demo guide.

## Small and complete changes

Choose the smallest complete solution that meets approved requirements. Reuse existing code and dependencies. Keep the current module structure. Do not add generic wrappers or speculative setup. When moving code, preserve validation and error handling. Complete all required caller, configuration, documentation, and UI updates.

Never cut trust-boundary validation, security, accessibility, or error handling that protects data. Keep comments short and explain why the code needs a non-obvious choice. Report checks that you did not run and known limits. Do not claim that the app works unless you observed the required result.

## Testing rules

- Add pytest API and database integration tests after approved functionality is implemented.
- Use the Playwright Python pytest plugin for browser end-to-end tests.
- Do not add unit or smoke tests unless the user changes this decision.
- Do not use test-driven development.
- If another test type appears necessary, explain why and ask before adding it.
- Before reporting that Docker is unavailable, run `docker compose ps` from the project root. If Docker works, report the Compose service status.

Do not use subagent-driven implementation by default. Use it only when the user asks or a task requirement or applicable instruction makes delegation necessary.
