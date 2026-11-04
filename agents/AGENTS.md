# AGENTS.md

## Project

Project description...


## Stack

- Languages: TypeScript, JavaScript, HTML, CSS, Markdown/MDX
- Framework: Astro
- Styling: Tailwind CSS v4
- Formatting: Prettier (with Astro and Tailwind plugins)
- Package manager & runtime: `bun`


## Project structure

- `astro.config.mjs` — Astro configuration.
- `.husky/` — Git hooks (`pre-commit` runs `lint-staged`, which formats staged files with Prettier).
- `internal/` — Internal notes and tooling not shipped with the site.
- `public/` — Static files copied as-is.
- `src/assets/` — Images (SVG, PNG) imported into pages, components and MD/MDX. Image optimization is disabled.
- `src/components/` — Astro components.


## Commands & Workflow

- Install dependencies: `bun install`
- Run development server: `bun run dev`
- Build project: `bun run build`
- Preview production build: `bun run preview`
- Type & Astro check: `bun run check`
- Format: `bunx prettier --write <files>`


## Code & Architecture Rules

- Write strict TypeScript. Never use `any` unless unavoidable (prefer `unknown` or explicit types).
- Do not introduce new abstractions without a clear need.
- Follow the existing project structure.
- Prefer existing utilities over duplicate code.
- Always identify and fix the underlying root cause of an issue rather than masking its symptoms.
- All layouts, custom components, tables, math blocks, and visualizations must be fully responsive across mobile, tablet, and desktop viewports.
- Build components as static `.astro` files. Add client-side interactivity only when strictly required, via a `<script>` in the `.astro` component.
- Prefer Tailwind utility classes; scoped `<style>` is acceptable for complex components.
- Ensure all custom components and SVGs support both light and dark themes.
- Before finishing, run `bun run check` and `bun run build`, and format changed files with Prettier.


## Restrictions

- Modify only files directly related to the task. Do not refactor unrelated code.
- Do not add, upgrade, or remove packages in `package.json` without explicit user approval.
- Do not bypass Husky hooks (`--no-verify`).


## MCP

- Prefer Chrome DevTools MCP over Playwright for inspecting DOM, layout, styles and verifying visual rendering of formulas and SVGs.
