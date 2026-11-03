---
name: project-presentation
description: Use when creating, editing, or reviewing the final PowerPoint presentation for a completed project in this workspace.
---

# Presentation Skill

Create the final project deck after implementation, agreed tests, and final verification are complete. Read `AGENTS.md` and the documentation skill. Use the relevant presentation authoring skill available in the session.

## Format

Use a clean 16:9 layout that fits the approved app style. Match the structure of the project's HTML code walkthrough when it exists. Use its section and subheadings as a guide, then shorten them for slides. Use diagrams, code paths, record shapes, and one worked example to carry technical detail. Keep slide text minimal. Put commands, evidence conditions, and deeper explanation in speaker notes. Keep diagrams readable and editable when practical. Do not use Mermaid.

## Content

Follow the HTML walkthrough's order where the content applies:

1. Project overview and requirements: user, problem, core flow, and key functional and quality needs.
2. Directory structure: key entry points and what owns each part.
3. Architecture: system boundaries, data sources, module calls, and persisted fields. Trace data through the diagram.
4. API walkthrough: one representative request, response, and failure path. Put the full inventory in notes or a reference slide only if useful.
5. Where data lives: input, derived values, saved records, and freshness.
6. Rules and business logic: deterministic inputs, one worked example, and limits.
7. Key decisions: important choices and trade-offs.
8. Production translation and extensibility: current limits, proposed changes, and the evidence that would trigger them.
9. Verification and limitations: observed checks, conditions, results, and open gaps.
10. Short demo guide: action sequence and one implemented recovery case. Label any simulation.

Combine or split topics to keep each slide legible. Use project facts and the writing skill. Distinguish implemented behavior, recorded verification, and proposed production work. If a recovery path is absent, state the gap and show it as proposed work.

## Review and delivery

Save the final deck as `docs/PROJECT_DEMO.pptx`. Record it in `docs/BUILD_PROGRESS.md` and `docs/DEMO_GUIDE.md`. Record a durable format choice in `docs/DECISION_LOG.md`.

Render and inspect every slide. Check the match with the HTML guide, readable text, diagram accuracy, and factual claims. Do not report a check that you did not run. Do not deliver temporary files unless the user asks for them.
