# Project Guidance

This file records project-wide defaults and user decisions. The project skill set is in `skills/`. These skill files use the Agent Skills format. Read them from this project when their task applies. They are not installed in a personal skills directory.

For full-stack application work, read [the consolidated workflow](skills/full-stack-project/SKILL.md). It routes to the backend, frontend, documentation, writing, and presentation skills. For a focused task, read the relevant skill directly. Keep this file as the source for project decisions. Keep detailed workflows in the skill files.

## Approved stack

- Backend and database: Flask, PostgreSQL, SQLAlchemy 2, and Alembic.
- API: REST JSON endpoints under `/api/v1`, Flask app factories and blueprints, and Pydantic request and response schemas. Keep `openapi.yaml` aligned with the routes and schemas. Generate the TypeScript client with `openapi-typescript` and `openapi-fetch` when the API contract changes.
- Frontend: Next.js 14 App Router, React, TypeScript, and Tailwind CSS. Check current official Next.js documentation when you set up or upgrade the stack.
- Local development: Docker Compose with the frontend, backend, and PostgreSQL. The frontend image installs its own packages. Use the Compose port mapping to report the local URL.
- Tests: pytest for API and database integration tests. Use the Playwright Python pytest plugin for browser end-to-end tests. Add tests after all approved functionality is implemented. Do not add unit or smoke tests unless the user changes this decision.

Keep route handlers, business logic, and feature-specific database queries in separate modules. Do not add a generic repository base class by default. Do not add login or account features unless the user asks for them or requirements need them. Store main records in structured tables. Add optional fields only when a project requirement needs them. Do not add enrichment history, provider payload storage, or provenance tables by default. Add queues, caches, microservices, or deployment infrastructure only when approved requirements need them.

Load configuration from environment variables. Keep placeholder values in `.env.example`. Do not store secrets in source control. Define consistent API errors and database constraints for important data rules.

## Project decisions

- Use Docker Compose for local runs.
- Keep the first release useful and within the scope the user approves.
- Use IBM Plex Sans and a compact, formal work-platform style for the lead dashboard example. Use the Purple light palette, restrained accents, clear sections, compact spacing, readable tables, and visible filters.
- Use ASD-STE100 as the writing guide for all project-authored files. See [the writing skill](skills/writing/SKILL.md).
- Do not use subagent-driven implementation by default. Use it only when the user asks for it or a task requirement or applicable instruction makes delegation necessary.

## Skill routing

| Task | Read |
| --- | --- |
| Full-stack design, implementation, and handoff | [Full-stack project](skills/full-stack-project/SKILL.md) |
| Flask API, PostgreSQL, SQLAlchemy, or Alembic | [Backend](skills/backend/SKILL.md) |
| Next.js pages, React components, or UI design | [Frontend](skills/frontend/SKILL.md) |
| Build progress, decisions, demo guide, diagrams, or production handoff | [Documentation](skills/documentation/SKILL.md) |
| Project prose, UI copy, comments, docstrings, or slide text | [Writing](skills/writing/SKILL.md) |
| Final project presentation | [Presentation](skills/presentation/SKILL.md) |

Create and maintain project records only after design approval, when work enters an approved implementation. Do not create them for planning-only chats or instruction-file updates. Follow the documentation skill when these records apply.

Use the requested design and implementation process. Get approval before application code, project scaffolding, or dependency installation. Do not write or run automated application tests before approved functionality is complete. Do not use test-driven development. Manual checks are allowed; report them as manual checks. Do not claim success without observing the required result. Report any check that you could not run.
