---
name: next-react-frontend
description: Use when designing, building, or reviewing Next.js pages, React components, and Tailwind CSS interfaces in this project.
---

# Frontend Skill

Use this skill for browser UI work in this project. Read the root `AGENTS.md` first. Follow its stack and approved visual direction.

## Stack and boundaries

- Use Next.js 14 with the App Router, React, TypeScript, and Tailwind CSS.
- Use file-based routes. Check current official Next.js documentation when you set up or upgrade Next.js.
- Keep state in the closest component that needs it. Add a shared state library only when approved requirements need state across distant components or pages.
- Use existing project components and installed packages before adding a dependency.
- Do not add a component library by default. Add an accessible primitive only when an interaction needs it and the dependency is approved.
- Keep business-specific components in feature folders.

## Shared UI foundation

Keep shared app components in `frontend/components/ui/`. Create only folders that contain real components:

```text
frontend/components/ui/
  forms/
  data-display/
  feedback/
  layout/
  overlays/
  README.md
frontend/app/dev/component-gallery/page.tsx
```

Build the smallest shared component set that the approved flow needs. Use native HTML with Tailwind for simple controls. Use an existing accessible primitive when an interaction needs keyboard or focus behavior. Do not mix primitive systems in one interaction. Do not wrap every library component.

Give shared components focused responsibilities, typed props, and typed callbacks. Document their purpose, states, accessibility needs, and one example in the UI README. Use the gallery route to preview components. Keep feature data and API calls out of it. Keep the route out of production navigation and make it unavailable in production. Show normal, loading, empty, error, disabled, and long-content states when they apply. Do not add Storybook or another component tool without an approved need.

Add design tokens after the user accepts a visual direction. Use semantic tokens for text, surfaces, fills, borders, and accents. Do not copy another site's palette or typography unless the user selects it.

## UI skill resources

Use [ibelick/ui-skills](https://github.com/ibelick/ui-skills) as a reference for UI tasks. Use `ui-skills-root` to select the smallest useful skill by topic, stack, and goal. Use one skill by default, two when the task needs two clear areas of guidance, and no more than three for a broad review or redesign.

- Use `baseline-ui` for a visual cleanup.
- Use `fixing-accessibility` when adding or changing interactive controls or accessibility behavior.
- Use `improve-ui` only for a read-only review. It must not edit product code. It produces evidence-based plans under `design-plans/`. Do not use it when the user asks for direct implementation.
- Do not install the full collection or add its CLI or MCP server unless the user approves.

Use [Taste Skill](https://github.com/Leonxlnx/taste-skill), skill name `design-taste-frontend`, for a new interface or a major visual redesign. Use its app-screen guidance for dashboards and other working interfaces. Review the result in a browser at desktop, tablet, and phone widths. Fix the main visible issues. Do not run its full workflow for a small component change. Keep the approved product style and task scope. Do not add motion, assets, or dependencies only to follow the skill. When you use third-party images, check the license and include the required credit.

## Interface quality

Apply these rules when they fit the approved design:

- Give icon-only controls accessible names. Prefer native buttons, links, and form elements.
- Give every field a visible label. Show validation errors beside the related field and connect errors to fields with accessible markup.
- Keep paste enabled. Give disabled controls a clear reason when needed.
- Use a confirmation dialog for destructive or irreversible actions. Use an accessible primitive for focus management.
- Show visible keyboard focus. Check text contrast. Do not use color alone to show status.
- Match loading placeholders to the content they replace. Give an empty state one clear action.
- Keep motion off unless the user or approved design asks for it. When motion is needed, keep it brief, use opacity or transform, and respect reduced-motion settings.
- Use tabular numbers when alignment helps. Let long technical text wrap or scroll. Keep full values available when truncating.
- Use spacing to group content before adding divider lines. Use borders to show structure and subtle shadows only to show depth.
- Check responsive layouts and the loading, empty, error, disabled, and long-content states that apply.
