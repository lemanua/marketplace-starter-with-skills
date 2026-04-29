# GitHub Copilot Instructions - Template for SitecoreAI Marketplace extensions

## Project overview

This project is the starter template for building Sitecore Marketplace extensions. Sitecore Marketplace extensions are TypeScript apps that extend and customize SitecoreAI products and give Sitecore users new capabilities tailored to their needs.
The project demonstrates five extension points: Custom Field, Dashboard Widget, Fullscreen, Pages Context Panel, and Standalone. Each extension point has its own UI and integration with the Sitecore Marketplace SDK.

Assume the application is based on:

- SitecoreAI CMS / XM Cloud
- Next.js
- React
- TypeScript
- Sitecore Marketplace SDK
- Sitecore Blok design system
- Sitecore Content SDK
- Experience Edge for layout and content delivery
- Page Builder for visual editing
- Sitecore CLI / serialization where applicable

SitecoreAI was previously known as XM Cloud in parts of the documentation and code examples. Treat both names as referring to the same product family unless the codebase clearly distinguishes them.

## General coding rules

- Use TypeScript-first implementation.
- Prefer small, composable React code.
- Preserve existing project conventions before introducing new patterns.
- Do not hardcode Sitecore item IDs, API keys, hostnames, context IDs, or environment-specific values.
- Use environment variables for configuration.
- Keep components compatible with Sitecore visual editing and Page Builder.
- Do not bypass Sitecore field helper components unless there is a clear technical reason.
- Do not replace Sitecore-managed content with static frontend-only content unless explicitly requested.
- Avoid broad refactors unless the task explicitly asks for them.

## Sitecore-specific rules

- Treat Sitecore templates, fields, renderings, placeholders, layouts, page designs, partial designs, and datasource items as part of the application contract.
- When creating or changing components, consider:
  - rendering definition
  - datasource template
  - datasource location
  - placeholder usage
  - field names and types
  - editing behavior in Page Builder
  - multilingual behavior
  - Experience Edge delivery behavior
- Prefer author-friendly behavior over silent failure.
- Components without required datasource data should show a clear editing-time fallback where the existing codebase supports it.
- Changes that affect layout data, rendering configuration, templates, or serialized items may require publishing or serialization updates.

## Commands

Before modifying commands, inspect package.json and existing scripts.

Common commands may include:

```bash
npm install
npm run dev
npm run build
npm run lint
npm test
```

## Sitecore Marketplace skills
The workspace contains 7 skills in `.github/skills/` that guide developers through scaffolding, building, and deploying Marketplace apps using the Sitecore Marketplace SDK (v0.4).

The skills target **Next.js App Router** apps deployed on **Vercel**, using the **Blok** design system (Sitecore's shadcn-based theme).

## Sitecore Marketplace skills key files

- `.github/skills/*/SKILL.md` — Skill definitions (frontmatter + instructions)
- `.github/skills/*/references/*.md` — Pre-curated API docs and code patterns