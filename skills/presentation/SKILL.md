---
name: project-presentation
description: Use when creating, editing, or reviewing the final PowerPoint presentation for a completed project in this workspace.
---

# Presentation Skill

Create the final project deck after implementation, agreed tests, and final verification are complete. Read `AGENTS.md` and the documentation skill. Use the relevant presentation authoring skill available in the session.

## Template

Use the [Slidesgo Minimalist Business Slides template](https://slidesgo.com/theme/minimalist-business-slides#position-1&rs=home-popular). Use the actual template when available. Follow its 16:9 layout and visual system. Choose a color variant that fits the approved project design. Preserve required template elements. Check the current license terms. If the free version requires attribution, keep its credit slide. If you cannot access the template, report the blocker before choosing another template.

## Content

Create seven content slides in this order. Adapt examples to the approved project. Do not imply that the project has a feature, provider, or result that it does not have.

| Slide | Content |
| --- | --- |
| 1. Problem and user | Name the user, their current difficulty, and the decision the app helps them make. For a lead dashboard, explain how a sales representative decides which businesses to contact first and why. |
| 2. MVP scope | Show the approved core flow, such as import → enrich → score → rank → inspect. State the key exclusions and why the MVP focused on this flow. |
| 3. Architecture and data flow | Show a simple frontend → backend → database diagram and any external provider. Mark where validation, business logic, and persistence happen. Match the implemented system. |
| 4. Live demo | Give a short action checklist for the core flow. Do not use screenshots as a substitute for the demo steps. Include one missing-data or failure case. |
| 5. Key implementation decisions | Explain three important choices and their trade-offs. For a lead scoring app, cover the stack and UI approach, scoring method, and external API handling. Name one reasonable alternative for each. |
| 6. Verification and limitations | Report checks that were actually run and their results. Identify fixture data, known gaps, and anything not verified. |
| 7. Production next steps | Rank the three most important next steps. Give the evidence or condition that would trigger each one. Do not invent production targets or claim unverified readiness. |

Use speaker notes for the explanation behind each slide. Keep slide text brief and readable. Use project facts, observed check results, and approved decisions. Follow the writing skill for all slide text and notes. Keep slide text editable when the template allows it.

## Review and delivery

Save the final deck as `docs/PROJECT_DEMO.pptx`. Record the deck in `docs/BUILD_PROGRESS.md` and `docs/DEMO_GUIDE.md`. Record the template choice in `docs/DECISION_LOG.md`.

Render and inspect every slide. Check content coverage, template match, readability, text fit, diagram accuracy, editability, and required credits. Compare slides with the source template. Do not report a check that you did not run. Do not deliver temporary files unless the user asks for them.
