# Essential Skills

This repository contains project instructions and six focused agent skills for a full-stack web application. It helps an agent follow one shared design, implementation, and handoff process.

## Use these files in a project

Copy `AGENTS.md` and the `skills/` folder into the project root. The agent reads `AGENTS.md` first. It contains the project defaults and points to the relevant skill files. The skills stay in the project. They are not installed in a personal skills directory.

For a full-stack project, start with `skills/full-stack-project/SKILL.md`. It links to the focused skills. For a single task, read only the skill that matches the work.

## Files

| File | Use it for |
| --- | --- |
| `AGENTS.md` | Project defaults, user decisions, and skill routing |
| `skills/full-stack-project/SKILL.md` | Design, implementation, verification, and project handoff |
| `skills/backend/SKILL.md` | Flask APIs, PostgreSQL, SQLAlchemy, Alembic, and backend checks |
| `skills/frontend/SKILL.md` | Next.js, React, TypeScript, Tailwind CSS, and reusable UI |
| `skills/documentation/SKILL.md` | Progress records, decision logs, demo guides, diagrams, and production handoff |
| `skills/writing/SKILL.md` | ASD-STE100 prose and Humanizer guidance |
| `skills/presentation/SKILL.md` | The final project presentation |

## Default stack

The project defaults use Flask, PostgreSQL, SQLAlchemy 2, Alembic, Next.js 14 App Router, React, TypeScript, Tailwind CSS, and Docker Compose. The API uses REST JSON, Pydantic schemas, and an `openapi.yaml` contract.

The defaults do not include login or account features. The test plan uses pytest for API and database integration tests and the Playwright Python pytest plugin for browser end-to-end tests. Add these tests after approved functionality is complete. Do not add unit or smoke tests unless the user changes this decision.

## Shared project rules

- Get approval for the design before application code, scaffolding, or dependency installation.
- Keep work within the approved scope. Reuse existing code and dependencies. Make the smallest complete change.
- Use Docker Compose for local development.
- Write project-authored files in clear English guided by ASD-STE100.
- Create project records after design approval. Update them at each implementation milestone.
- Verify the final user flow and report observed results, unchecked items, and known limits.
- Create the presentation after final implementation and verification. Use the approved Slidesgo template and include only evidence from the project.

## UI and writing resources

The frontend skill links to [ibelick/ui-skills](https://github.com/ibelick/ui-skills) for focused UI guidance and [Taste Skill](https://github.com/Leonxlnx/taste-skill) for new interfaces or major redesigns. The writing skill links to [Humanizer](https://github.com/blader/humanizer) as a supplementary prose review.

The presentation skill uses the [Slidesgo Minimalist Business Slides template](https://slidesgo.com/theme/minimalist-business-slides#position-1&rs=home-popular). Check its current terms and keep required credits.
