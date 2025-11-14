# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Design Patterns Cheatsheet project built with **Astro**, a modern static site generator optimized for fast, content-driven websites. The project follows Astro's minimal starter template structure.

## Development Commands

- `pnpm dev` - Start the local development server (runs at `localhost:4321` by default)
- `pnpm build` - Build the production site to the `./dist/` directory
- `pnpm preview` - Preview the production build locally
- `pnpm astro` - Run Astro CLI commands
- `pnpm astro -- --help` - Get help on available Astro commands

## Project Structure

```
/
├── src/
│   ├── pages/          # Astro pages - each .astro or .md file becomes a route
│   │   └── index.astro # Main landing page
│   ├── components/     # Reusable Astro/React/Vue/Svelte components
│   └── layouts/        # Layout components for pages
├── public/             # Static assets (images, fonts, etc.)
├── dist/               # Production build output (generated, not in repo)
├── astro.config.mjs    # Astro configuration
├── tsconfig.json       # TypeScript configuration (uses Astro strict config)
└── package.json        # Project dependencies and scripts
```

## Tech Stack

- **Astro 5.x** - Main framework for static site generation
- **TypeScript** - Strict TypeScript configuration via Astro's preset
- **pnpm** - Package manager

## Key Architecture Notes

### Astro File-Based Routing

Astro automatically creates routes based on the file structure in `src/pages/`:
- Each `.astro` or `.md` file in `src/pages/` becomes a page route
- Filenames determine the URL path (e.g., `src/pages/patterns/singleton.astro` → `/patterns/singleton/`)
- `index.astro` or `index.md` serves as the root route for its directory

### Static Site Generation

This is a fully static site - all pages are pre-rendered during the build process. There is no server-side runtime; content is generated to HTML/CSS/JS files.

### Astro Components

Components can be placed in `src/components/` and support:
- Astro files (`.astro`) - zero JavaScript by default
- Frontend frameworks (React, Vue, Svelte, Preact, etc.) - with island architecture for interactivity
- Markdown with components integration via MDX

## Development Workflow

1. Edit files in `src/` - changes automatically hot-reload in dev server
2. Run `pnpm build` to generate the production build in `dist/`
3. Use `pnpm preview` to test the production build locally before deployment
