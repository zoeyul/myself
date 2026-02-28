## myself

> Personal portfolio and technical blog. Built with Next.js 16, React 19, and TypeScript. Features real-time performance monitoring, interactive data visualizations, and browser-native WAAPI animations.

### Live

[your-domain.com](https://your-domain.com)

### Technical Highlights

- **Performance Monitoring Overlay**
  Real-time Web Vitals (LCP, CLS, INP), FPS counter, and long task detection using the PerformanceObserver API. Toggleable overlay widget that monitors the site itself. Custom SVG sparkline visualizations — no charting library.

- **Interactive Data Visualization**
  Tech stack and experience data rendered as custom SVG charts, built without D3 or any charting library. Demonstrates data visualization capability through practical, meaningful content.

- **Animation System (Web Animation API)**
  Scroll-triggered section reveals, micro-interactions, and page transitions using browser-native `Element.animate()`. Respects `prefers-reduced-motion`. Zero animation library dependencies.

- **MDX Blog**
  Technical writing on performance and browser APIs, with syntax highlighting (Shiki) and custom interactive components.

### Engineering Approach

- Server Components by default, `'use client'` only where browser APIs are needed
- Custom hooks as the primary abstraction layer (`usePerformanceObserver`, `useFPS`, `useAnimation`)
- Tested with Vitest + React Testing Library
- Accessible: semantic HTML, keyboard navigation, skip links, ARIA labels, WCAG 2.1 AA contrast

### Architecture

```
src/
├── app/            # Next.js App Router pages
├── components/
│   ├── layout/     # Header, Footer
│   ├── sections/   # Hero, About, Projects, Experience, Contact
│   ├── perf/       # Performance overlay (Sparkline, MetricCard)
│   ├── blog/       # PostCard, MDX components
│   └── ui/         # Shared primitives (Section, Badge, SkipLink)
├── content/posts/  # MDX blog posts
├── hooks/          # usePerformanceObserver, useFPS, useAnimation, useIntersection
└── lib/            # Types, constants, MDX utilities
```

### Stack

Next.js 16 (App Router) · React 19 · TypeScript (strict) · Tailwind CSS 4 · Web Animation API · PerformanceObserver API · MDX · Vitest

### Development

```bash
pnpm install
pnpm dev          # localhost:3000
pnpm test         # vitest
pnpm build        # production build
```
