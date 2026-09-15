# Architecture — G3 Gamer Store

## Overview

G3 Gamer Store is a Vite + React single-page application focused on a gamer e-commerce experience. The application combines a product-oriented landing page with an interactive PC-building flow.

The repository is structured around React pages and reusable UI components. Routing is handled by React Router DOM, while TanStack Query is provided at the application root for asynchronous state management and caching.

## Stack

- React 18.3
- TypeScript 5.8
- Vite 5.4
- React Router DOM 6.30
- Tailwind CSS 3.4
- shadcn/ui and Radix UI
- Framer Motion 12.27
- TanStack Query 5.83
- React Hook Form 7.61
- Zod 3.25
- Vitest 3.2
- Testing Library
- ESLint 9
- Vercel configuration

## Application structure

```text
src/
├── assets/
├── components/
│   ├── ui/
│   ├── BrandsSection.tsx
│   ├── BuildPCWizard.tsx
│   ├── CategoriesSection.tsx
│   ├── FeaturesSection.tsx
│   ├── Header.tsx
│   ├── Hero.tsx
│   ├── OffersSection.tsx
│   ├── ProductCard.tsx
│   └── ...
├── pages/
│   ├── Index.tsx
│   ├── BuildPC.tsx
│   └── NotFound.tsx
├── test/
│   ├── example.test.ts
│   └── setup.ts
├── App.tsx
├── App.css
├── index.css
└── main.tsx
```

## Application entry and routing

`src/App.tsx` creates the application providers and route tree.

The application currently exposes these route behaviors:

- `/` → `Index`
- `/monte-seu-pc` → `BuildPC`
- `*` → `NotFound`

`QueryClientProvider` wraps the application and exposes a shared TanStack Query client. `TooltipProvider`, the two toaster systems, and `BrowserRouter` are also configured at the application root.

## Landing page

`src/pages/Index.tsx` composes the main storefront experience from independent sections:

- `Header`
- `Hero`
- `FeaturesSection`
- `HighlightBar`
- `OffersSection`
- `CategoriesSection`
- `NewsletterSection`
- `BrandsSection`
- `Footer`
- `WhatsAppButton`

This keeps page composition separate from the implementation details of each section.

## PC builder flow

`src/pages/BuildPC.tsx` contains the interactive PC-building experience.

The page defines a sequence of build steps covering processor, cooler, motherboard, memory, GPU, storage, case, PSU and peripherals.

Each step contains component data with fields such as name, specifications, price, brand, compatibility and image URL.

The UI maintains local state for the current step, selected components, search term, brand filter and cart modal state. Components can be filtered by name/specification and brand within the active step.

Framer Motion is used for animated interactions and Lucide icons provide the visual controls.

## Component system

The repository contains a reusable `components/ui` layer based on shadcn/ui and Radix UI primitives. These components provide common interface patterns such as dialogs, inputs, buttons, dropdowns, tabs, tooltips, sliders and other controls.

Higher-level storefront components compose these primitives into application-specific sections such as the header, product cards, offers and PC builder.

## Styling

Tailwind CSS provides the utility-based styling layer. Supporting utilities such as `clsx`, `tailwind-merge` and `class-variance-authority` are available for conditional and variant-based class composition.

## State and data

TanStack Query is configured at the application root through a shared `QueryClient`.

The inspected application also contains local component state for interactive flows such as the PC builder. This documentation does not claim an external API or production data backend because the inspected code does not establish one.

## Forms and validation

React Hook Form and Zod are installed as the form-management and validation stack, with `@hookform/resolvers` providing integration between form state and schema validation.

No specific form coverage is claimed because the current test suite does not exercise these areas.

## Testing architecture

Vitest is configured in `vitest.config.ts` with:

- `jsdom` environment
- global test APIs
- `src/test/setup.ts` as the setup file
- inclusion of `.test.ts`, `.test.tsx`, `.spec.ts` and `.spec.tsx` files under `src/`

The setup imports `@testing-library/jest-dom` and provides a `window.matchMedia` implementation for DOM-based tests.

At the time of this documentation pass, the repository contains one test file: `src/test/example.test.ts`. It contains only a basic smoke assertion (`true` is expected to be `true`).

Therefore, the current repository has testing infrastructure but no demonstrated functional test coverage for the application's pages, components or business flows.

## Build and deployment

The project uses Vite for development and production builds. The package scripts expose `dev`, `build`, `build:dev`, `preview`, `test`, `test:watch` and `lint` commands.

`vercel.json` configures Vercel with:

- Bun installation
- `bun run build` as the build command
- `dist` as the output directory
- Vite as the framework
- an SPA rewrite to `/index.html`

The repository metadata documents `https://g3-gamer-store.vercel.app` as the project homepage. Its current public availability is not asserted by this document.

## Engineering notes

The package name was corrected from the generic `vite_react_shadcn_ts` to `g3-gamer-store` during the documentation branch. No other source-code change is part of this documentation work.

The project did not contain a LICENSE file on `main`; the documentation branch adds the requested MIT license.

## Scope and limitations

This document intentionally describes only behavior and structure supported by repository inspection. It does not claim:

- a specific test coverage percentage;
- passing test/build/lint results before those commands are executed;
- an independently verified active production deployment;
- a backend or external product database that is not established by the inspected code.
