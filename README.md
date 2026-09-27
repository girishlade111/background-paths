# Background Paths

An animated SVG hero background component built with React, Tailwind CSS, and Framer Motion. Two layered sets of 36 flowing bezier paths drift across the screen with randomized durations, sitting behind a letter-by-letter spring-animated headline and a glassmorphic CTA button. Light/dark mode aware.

## What it does

- Renders 72 procedurally generated SVG paths (two mirrored `FloatingPaths` layers) that continuously draw themselves via animated `pathLength`/`pathOffset`, producing a soft, flowing "topographic line" backdrop.
- Reveals the headline one letter at a time with a spring-physics entrance, using gradient-clipped text.
- Ships a glassmorphic "Discover Excellence" call-to-action button with hover lift and arrow-slide micro-interactions.
- Adapts to dark mode (`dark:` variants) — white-on-neutral-950 in dark, slate paths on white in light.

## Features

- **Animated flowing line art** — 36 bezier curves per layer, each with unique width, opacity, and 20–30s loop duration
- **Letter-by-letter title reveal** — staggered spring animation, configurable via the `title` prop (default `"Background Paths"`)
- **Glassmorphism CTA** — backdrop-blurred, gradient-bordered button with hover states
- **Dark mode support** — CSS-driven via Tailwind's dark variant
- **Pointer-events safe** — the SVG layer is non-interactive, so it never blocks clicks

## Tech stack

- **React** (client component, `"use client"`)
- **Framer Motion** (`motion` primitives: `motion.path`, `motion.span`, `motion.div`)
- **Tailwind CSS** (layout, gradients, dark-mode variants)
- **shadcn/ui** `Button` component (`@/components/ui/button`)
- **TypeScript** (`.tsx`)

## Quick start

This repo ships just the component. To use it in a Next.js/Tailwind project with Framer Motion and shadcn/ui installed:

```bash
# 1. Install dependencies
npm install framer-motion

# 2. Copy the component into your project
cp components/kokonutui/background-paths.tsx your-project/components/

# 3. Render it anywhere
import BackgroundPaths from "@/components/background-paths"

export default function Page() {
  return <BackgroundPaths title="Your headline here" />
}
```

Required peer dependencies in the host project:

- `framer-motion`
- `tailwindcss` (with dark mode configured)
- `@/components/ui/button` from shadcn/ui

Props:

| Prop    | Type     | Default            | Description                          |
| ------- | -------- | ------------------ | ------------------------------------ |
| `title` | `string` | `"Background Paths"` | Headline rendered letter by letter |

## Project structure

```
background-paths/
├── README.md
└── components/
    └── kokonutui/
        └── background-paths.tsx   # FloatingPaths layers + headline + CTA
```

## Environment variables

None.

## Deployment notes

There is nothing to deploy — this repository contains a single reusable UI component, not a runnable app. To preview it, drop it into a Next.js + Tailwind + Framer Motion project and render `<BackgroundPaths />`. It was originally generated with [v0](https://v0.app) (see commit history).

---

Built by Girish Lade — [ladestack.in](https://ladestack.in)
