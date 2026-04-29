<p align="center">
  <img src="public/logo.svg" alt="ThesisForge Logo" width="80" height="80" />
</p>

<h1 align="center">ThesisForge</h1>

<p align="center">
  <strong>Free LaTeX Thesis Generator</strong><br />
  Generate a complete, compilable LaTeX thesis in minutes. No LaTeX knowledge required.
</p>

<p align="center">
  <a href="https://thesisforge-web.vercel.app" target="_blank">
    <img src="https://img.shields.io/badge/Live-Demo-534AB7?style=for-the-badge&logo=vercel" alt="Live Demo" />
  </a>
  <img src="https://img.shields.io/badge/Next.js-16.1-black?style=for-the-badge&logo=next.js" alt="Next.js" />
  <img src="https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react" alt="React" />
  <img src="https://img.shields.io/badge/TypeScript-5-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Tailwind_CSS-4-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white" alt="Tailwind CSS" />
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="License" />
</p>

<p align="center">
  <a href="#features">Features</a> &middot;
  <a href="#tech-stack">Tech Stack</a> &middot;
  <a href="#getting-started">Getting Started</a> &middot;
  <a href="#usage-guide">Usage</a> &middot;
  <a href="#architecture">Architecture</a> &middot;
  <a href="#deployment">Deployment</a>
</p>

---

ThesisForge is a browser-based academic thesis creation tool that guides you through a 6-step wizard, from template selection to downloadable `.tex` + `.bib` files ready for Overleaf, TeXStudio, or any LaTeX editor. It runs entirely client-side with IndexedDB persistence — no account required, no data leaves your browser.

---

## Features

### Multi-Format Import

Import existing work from **5 formats** — `.pdf`, `.tex`, `.docx`, `.md`, `.txt` — with intelligent content extraction, confidence scoring, and automatic field mapping. Multi-file merge support lets you combine chapters from different sources into a single thesis.

### Template System

Choose from 5 academic templates, each with pre-configured structures and formatting defaults:

| Template | Default Style | Chapter Count | Features |
|----------|--------------|---------------|----------|
| Bachelor's Thesis | APA, 12pt, 1.5 spacing | 5 | IMRAD structure, acknowledgment |
| Master's Thesis | APA, 12pt, 1.5 spacing | 6 | Dedication, appendices, per-chapter numbering |
| PhD Dissertation | IEEE, 12pt, double spacing | 7 | Glossary, nomenclature, listings, front/back matter |
| Research Report | IEEE, 11pt, single spacing | 3 | Streamlined, concise format |
| Conference Paper | IEEE, 10pt, single spacing | 5 | Compact, page-limited submission format |

### LaTeX Generation Engine

- **Smart escape system** — 100+ Unicode-to-LaTeX mappings with context-aware segmentation that preserves existing LaTeX commands while escaping plain text
- **36 lint rules** — Post-generation validation across structural, formatting, academic writing, and expert-level categories. Errors block export; warnings and info do not
- **Compilation recipes** — Support for `pdflatex`, `xelatex`, and `lualatex` with configurable pass counts and bibliography backends (`bibtex` / `biber`)

### Reference Management

- 9 reference types: article, book, inproceedings, techreport, thesis, online, misc, dataset, software
- 5 citation styles: IEEE, APA, Vancouver, Chicago, Harvard
- BibTeX generation with automatic deduplication and type classification

### Intelligence Panel

An AI-powered writing assistant with 17 analysis modules that provides real-time feedback as you write:

- **Completeness scoring** — 8-dimension thesis completeness tracker with progress ring visualization
- **Writing coach** — Academic writing feedback including tone, clarity, and structure suggestions
- **Passive voice detection** — Identifies excessive passive voice with inline suggestions
- **Transition analysis** — Evaluates paragraph transitions for logical flow
- **Acronym consistency** — Checks that acronyms are defined before first use and used consistently
- **Citation graph** — Network analysis of in-text citations vs bibliography, detecting undefined and uncited references
- **Structure balance** — Measures word count distribution across chapters against academic norms
- **Reading statistics** — Per-chapter word counts, reading time estimates, and long-sentence detection
- **Keyword extraction** — Automatically extracts research keywords from content
- **LaTeX heuristics** — 12 auto-fixable rules for common LaTeX mistakes (smart quotes, percent signs, deprecated commands)
- **Reference deduplication** — Exact, normalized, and fuzzy matching to find duplicate bibliography entries

### Real-Time Preview

- Monaco-based LaTeX editor with syntax highlighting, autocomplete, and inline diagnostics
- Custom LaTeX and BibTeX tokenizers for accurate color-coding
- PDF preview panel with simulation mode
- 50+ academic LaTeX snippets accessible from the editor toolbar

### Persistence & Export

- **Auto-save** to IndexedDB — resume your thesis anytime, no account required
- **Undo/redo** with full state history (Ctrl+Z / Ctrl+Shift+Z)
- **Export as ZIP** — Downloadable `.tex` + `.bib` files that compile without errors
- **Project import/export** — Save and restore your entire project as JSON
- **Smart Import Review** — Drag-and-drop files, review extracted data, then apply with confidence scores

### SEO & Content

- **Structured data** — 3 JSON-LD schemas: `SoftwareApplication`, `HowTo`, `FAQPage` (server-rendered in `<head>`)
- **OpenGraph & Twitter Cards** — Dynamic OG image generation via `next/og` with quill and forge logo
- **Sitemap** — Dynamic sitemap with 20+ URLs covering templates, citation styles, VS pages, blog, and editor
- **robots.txt** — Allows all major crawlers (Googlebot, Bingbot, Twitterbot, facebookexternalhit)
- **Favicon** — SVG favicon for modern browsers, PNG fallbacks (192x192, 512x512), Apple Touch Icon (180x180)
- **Web App Manifest** — PWA-ready with theme-color for light/dark modes, standalone display mode
- **Canonical URL + hreflang** — Proper canonicalization with `en` and `x-default` alternate links

### Mobile Support

- **Responsive wizard** — Full 6-step thesis wizard adapts to all screen sizes with a hamburger menu and mobile-optimized layouts
- **Intelligence panel across all viewports** — Inline sidebar on desktop (768px+), slide-out Sheet on mobile, with no dead zones on tablets
- **Mobile editor** — Monaco editor adapts to mobile with simplified toolbar, disabled minimap, word-wrap enabled, and touch-friendly sidebar
- **Touch-friendly** — All buttons and interactive elements meet minimum 44px tap target size
- **Safe-area aware** — Mobile Sheet panels respect notch and home indicator safe areas (iOS)
- **Overscroll containment** — Prevents browser pull-to-refresh from interfering with scroll areas

---

## Tech Stack

| Category | Technology | Notes |
|----------|-----------|-------|
| **Framework** | Next.js 16.1 (App Router) | Standalone output, Turbopack bundler |
| **React** | React 19 + React Compiler | Automatic memoization |
| **Language** | TypeScript 5 (strict mode) | Path aliases via `@/*` |
| **Typography** | Poppins, Inter, JetBrains Mono | Google Fonts |
| **Styling** | Tailwind CSS 4 | tailwind-merge, CVA, tw-animate-css |
| **Design System** | Custom CSS tokens | 9-step type scale, semantic colors, motion, elevation |
| **UI Components** | shadcn/ui (new-york style) | 40+ Radix UI primitives |
| **Animation** | Framer Motion 12 | Shared layout, AnimatePresence |
| **State** | Zustand 5 | Granular selectors, persist middleware |
| **Forms** | React Hook Form 7 + Zod 4 | Validation schemas |
| **Editor** | Monaco Editor 4.7 | Custom LaTeX/BibTeX tokenizers |
| **PDF Parsing** | pdfjs-dist 5 | Web Worker for async extraction |
| **DOCX Parsing** | JSZip 3 | XML-based content extraction |
| **Database** | Prisma 6 + SQLite | Optional server-side persistence |
| **Client Storage** | IndexedDB (idb) | Auto-save, snapshots, history |
| **Charts** | Recharts 2.15 | Intelligence panel visualizations |
| **DnD** | @dnd-kit/core + sortable | Chapter and reference reordering |
| **Toasts** | Sonner | Success, warning, error, undo actions |
| **Dark Mode** | next-themes | Class-based, system-preference detection |
| **Runtime** | Bun / Node.js | Bun for local dev, Node for production |
| **Image** | AVIF + WebP | Next.js image optimization |

---

## Project Structure

```
thesisforge/
├── public/                       # Static assets
│   ├── logo.svg                 # ThesisForge logo (Quill & Forge mark)
│   ├── favicon.svg              # SVG favicon (modern browsers)
│   ├── favicon-192.png          # PNG favicon fallback
│   ├── favicon-512.png          # High-res favicon
│   ├── apple-touch-icon.png     # iOS home screen icon
│   ├── og-image.jpg             # OpenGraph image (1200x630)
│   ├── manifest.webmanifest     # PWA manifest
│   ├── sw.js                    # Service Worker
│   ├── pdf.worker.min.mjs       # PDF.js Web Worker
│   └── robots.txt               # Crawler rules
│
├── src/
│   ├── app/                     # Next.js 16 App Router
│   │   ├── layout.tsx           # Root layout (SEO meta, JSON-LD, PWA, fonts)
│   │   ├── page.tsx             # Homepage + 6-step wizard
│   │   ├── globals.css          # Design system, themes, animations, utilities
│   │   ├── opengraph-image.tsx  # Dynamic OG image generation (next/og)
│   │   ├── sitemap.ts           # Dynamic sitemap (20+ URLs)
│   │   ├── robots.ts            # Robots.txt generation
│   │   ├── editor/              # Standalone LaTeX editor page
│   │   ├── templates/[slug]/    # SEO template landing pages (5 templates)
│   │   ├── citation-styles/[style]/ # Citation style reference pages (5 styles)
│   │   ├── blog/                # Blog index + [slug] individual posts
│   │   ├── vs/[slug]/           # Comparison pages (vs Overleaf, Word, LaTeX)
│   │   └── api/                 # API routes (health check, generate-latex)
│   │
│   ├── core/                    # Core business logic (28+ modules)
│   │   ├── fsm.ts               # Finite state machine for wizard flow
│   │   ├── fsmGuard.ts          # FSM validation guard for step transitions
│   │   ├── linter.ts            # 36-rule LaTeX lint engine (4 severity categories)
│   │   ├── export.ts            # ZIP export (main.tex + references.bib)
│   │   ├── bib.ts               # BibTeX generation (9 reference types)
│   │   ├── persistence.ts       # IndexedDB auto-save & snapshots
│   │   ├── history.ts           # Undo/redo state stack
│   │   ├── compilation-simulator.ts # Simulated LaTeX compilation
│   │   ├── preview-renderer.ts  # Preview rendering pipeline
│   │   ├── templates.ts         # LaTeX template generation per thesis type
│   │   ├── ast.ts               # Abstract syntax tree for LaTeX
│   │   ├── ast-builder.ts       # AST builder
│   │   ├── serializer.ts        # Project JSON serialization (version 2)
│   │   ├── validators.ts        # Input validation
│   │   ├── editor-bridge.ts     # Bridge between wizard and LaTeX editor
│   │   └── importer/            # Multi-format import system
│   │       ├── index.ts         # Public API — routes to format importers
│   │       ├── pdfImporter.ts   # PDF text extraction (pdfjs-dist)
│   │       ├── texImporter.ts   # LaTeX source parser
│   │       ├── docxImporter.ts  # DOCX/XML extraction (JSZip)
│   │       ├── markdownImporter.ts # Markdown parser
│   │       ├── txtImporter.ts   # Plain text structure detector
│   │       ├── bibtexParser.ts  # BibTeX entry parser
│   │       ├── contentIntelligence.ts # Content classification, IMRAD, quality
│   │       ├── fieldMapper.ts   # Import data -> ThesisData field mapping
│   │       ├── confidenceScorer.ts   # Per-field confidence scoring
│   │       ├── templateDetector.ts   # Thesis template type detection
│   │       └── textUtils.ts     # Levenshtein distance, fuzzy match, utilities
│   │
│   ├── engine/                  # LaTeX generation engine
│   │   ├── escape.ts            # Smart LaTeX escaper (100+ Unicode mappings)
│   │   ├── packages.ts          # LaTeX package management
│   │   └── intelligence.ts      # Engine-level intelligence integration
│   │
│   ├── intelligence/            # AI-powered writing analysis (17 modules)
│   │   ├── scheduler.ts         # Run scheduler with debounced algorithm pipeline
│   │   ├── writingCoach.ts      # Academic writing feedback
│   │   ├── citationParser.ts    # Citation extraction and analysis
│   │   ├── citationGraph.ts     # Citation network analysis + dedup
│   │   ├── structureAnalyzer.ts # Document structure + word counting
│   │   ├── completenessScorer.ts # Thesis completeness scoring
│   │   ├── passiveVoiceDetector.ts # Passive voice detection
│   │   ├── transitionAnalyzer.ts # Paragraph transition quality
│   │   ├── acronymChecker.ts    # Acronym consistency checking
│   │   ├── keywordExtractor.ts  # Keyword extraction + cross-check
│   │   ├── readingStats.ts      # Reading statistics + chapter health
│   │   ├── latexExpertAnalyzer.ts # LaTeX expertise analysis
│   │   ├── latexHeuristics.ts   # 12 auto-fixable LaTeX heuristic rules
│   │   ├── semanticGraph.ts     # Semantic content graph
│   │   ├── thesisMemory.ts      # Cross-session thesis memory, velocity
│   │   ├── deduplicator.ts      # Reference deduplication (exact + fuzzy)
│   │   └── types.ts             # Intelligence type definitions
│   │
│   ├── lib/                     # Shared libraries
│   │   ├── thesis-types.ts      # TypeScript type system (ThesisData, templates)
│   │   ├── thesis-store.ts      # Zustand store for wizard state (FSM-gated)
│   │   ├── editor-store.ts      # Zustand store for LaTeX editor state
│   │   ├── latex-generator.ts   # High-level LaTeX generation orchestrator
│   │   ├── config.ts            # App configuration and site URL
│   │   ├── monaco-setup.ts      # Monaco editor configuration
│   │   └── utils.ts             # Utility functions (cn, debounce, etc.)
│   │
│   ├── components/
│   │   ├── thesis/              # Domain components (30 files)
│   │   │   ├── Logo.tsx         # Reusable logo (4 sizes, hover animation)
│   │   │   ├── homepage.tsx     # Landing page (hero, features, stats, CTA)
│   │   │   ├── template-selector.tsx  # Step 1: Choose thesis type
│   │   │   ├── metadata-form.tsx      # Step 2: Title, abstract, author
│   │   │   ├── chapter-editor.tsx     # Step 3: Write chapter content
│   │   │   ├── reference-editor.tsx   # Step 4: Manage references
│   │   │   ├── format-editor.tsx      # Step 5: Configure output
│   │   │   ├── generate-preview.tsx   # Step 6: Preview and export
│   │   │   ├── intelligence-panel.tsx  # AI writing assistant (sidebar + Sheet)
│   │   │   ├── ImportReviewModal.tsx  # Import field review and apply
│   │   │   ├── ImportDropZone.tsx     # Drag-and-drop file import
│   │   │   ├── step-indicator.tsx     # Step progress indicator
│   │   │   ├── save-indicator.tsx     # Auto-save status indicator
│   │   │   ├── latex-editor/          # Monaco editor components (10 files)
│   │   │   └── ...                   # Appendix editor, theme provider, diff viewer
│   │   ├── ui/                 # shadcn/ui primitives (40+ components)
│   │   └── ErrorBoundary.tsx  # Global error boundary
│   │
│   ├── hooks/                   # Custom React hooks
│   │   ├── use-mobile.ts       # Viewport breakpoint detection
│   │   ├── use-toast.ts        # Toast notification hook
│   │   └── useLatexWorker.ts   # Web Worker hook for LaTeX processing
│   │
│   ├── ui/
│   │   └── tokens.css          # Design system tokens (colors, type, spacing, motion)
│   ├── workers/                # Web Workers (import, LaTeX processing)
│   ├── utils/                  # Utility functions (debounce, deep-merge, hash)
│   └── tests/                  # Test files
│
├── prisma/
│   └── schema.prisma           # SQLite database schema
│
├── next.config.ts              # Next.js configuration (standalone, React compiler)
├── tailwind.config.ts          # Tailwind CSS configuration
├── tsconfig.json               # TypeScript configuration (strict mode)
├── components.json             # shadcn/ui configuration (new-york style)
├── postcss.config.mjs          # PostCSS configuration
└── package.json                # Dependencies and scripts
```

---

## Architecture

### Data Flow

```
User Input (Wizard Steps)
     |
     v
Zustand Store (thesis-store.ts)
  ├── FSM-gated navigation (fsm.ts + fsmGuard.ts)
  ├── Input sanitization + validation
  └── Granular selectors (prevent unnecessary re-renders)
     |
     ├──► Intelligence Pipeline (17 modules, debounced)
     |      ├── Completeness scoring
     |      ├── Structure balance analysis
     |      ├── Citation graph analysis
     |      ├── Writing coach feedback
     |      └── LaTeX heuristic auto-fixes
     |
     ├──► IndexedDB Persistence (auto-save every 1s)
     |      ├── Draft save/restore
     |      ├── Snapshots (manual Ctrl+S)
     |      └── State history (undo/redo)
     |
     ├──► LaTeX Generation Engine
     |      ├── Smart escaper (100+ mappings, 2-phase)
     |      ├── Template renderer (5 thesis types)
     |      ├── BibTeX generator (9 ref types)
     |      └── Lint engine (36 rules)
     |
     └──► ZIP Export (main.tex + references.bib)
```

### Import Pipeline

```
File Input (.pdf / .tex / .docx / .md / .txt)
     |
     v
Format Router --> Format-Specific Importer
                    |-- pdfImporter (pdfjs-dist)
                    |-- texImporter (LaTeX parser)
                    |-- docxImporter (JSZip XML)
                    |-- markdownImporter (AST-based)
                    +-- txtImporter (heuristic detection)
     |
     v
ImportResult
  +-- ExtractedMetadata (title, author, institution, year, abstract, keywords)
  +-- ExtractedChapter[] (title, body, subsections)
  +-- ExtractedReference[] (BibTeX fields)
  +-- Confidence Scores (per-field + overall, format boost)
  +-- Warnings[] (parse issues, missing data)
     |
     v
Content Intelligence
  +-- Content Classification (thesis / paper / dissertation / report / monograph)
  +-- IMRAD Structure Detection (completeness + IMRAD score)
  +-- Quality Scoring (6 dimensions with actionable suggestions)
  +-- Reference Deduplication (exact + normalized + fuzzy + author+year)
  +-- Reference Type Classification (9 BibTeX types)
     |
     v
Field Mapper --> Import Review Modal --> Apply to Wizard
```

**Confidence scoring** applies per-format boosts: TeX (1.10x), Markdown (1.05x), DOCX (1.00x), PDF (0.95x), TXT (0.85x).

**Reference deduplication** uses a multi-layer approach: O(1) DOI/URL exact match, O(1) normalized title match, and trigram-based fuzzy matching with Levenshtein distance as a final check.

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) 18+ (or [Bun](https://bun.sh/))
- npm, yarn, or bun

### Installation

```bash
# Clone the repository
git clone <repository-url>
cd thesisforge

# Install dependencies
npm install

# (Optional) Set up environment variables
cp .env.example .env.local

# Run the development server
npm run dev
```

The app will be available at [http://localhost:3000](http://localhost:3000).

### Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `NEXT_PUBLIC_SITE_URL` | `https://thesisforge-web.vercel.app` | Canonical URL for SEO (OG images, sitemap, JSON-LD) |
| `DATABASE_URL` | `file:./db/custom.db` | SQLite database path (optional, for server features) |

### Production Build

```bash
# Build for production
npm run build

# Start the production server
npm start
```

The production build includes:
- Static HTML generation for all 20+ pages (templates, citation styles, blog posts, comparisons)
- Standalone output for deployment to Vercel, Docker, or any Node.js host
- Optimized bundles with code splitting for each wizard step
- AVIF + WebP image optimization
- React Compiler automatic memoization

---

## Usage Guide

### Path 1: Guided Wizard (Recommended)

1. **Choose a template** — Select from Bachelor's, Master's, PhD, Research Report, or Conference Paper
2. **Fill in metadata** — Enter title, author, university, supervisor, abstract, and keywords
3. **Write chapters** — Use the rich editor to add and organize your chapter content with drag-and-drop reordering and subsections
4. **Manage references** — Add citations manually or import from BibTeX. Choose your citation style (IEEE, APA, Vancouver, Chicago, Harvard)
5. **Configure format** — Set font size, paper size, line spacing, margins, numbering, and TOC depth
6. **Generate and export** — Preview your LaTeX source in the Monaco editor, review lint results, then download the ZIP file containing `main.tex` and `references.bib`

### Path 2: Direct LaTeX Editor

1. Open the [LaTeX Editor](/editor) from the homepage
2. Write LaTeX directly with syntax highlighting, autocomplete, and 50+ academic snippets
3. Use the diagnostics panel for real-time feedback
4. Export as ZIP when ready

### Path 3: Import Existing Work

1. From the homepage, click **"Import Thesis"** (supports `.pdf`, `.tex`, `.docx`, `.md`, `.txt`)
2. Drop or select one or more files — multi-file merge is supported
3. Review the import in the modal: check extracted metadata, chapters, and references with confidence scores
4. Apply the import to populate the wizard fields
5. Continue editing and export as usual

### Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl+Z` | Undo |
| `Ctrl+Shift+Z` / `Ctrl+Y` | Redo |
| `Ctrl+S` | Save snapshot |
| `Ctrl+Arrow Right` / `Ctrl+Arrow Down` | Next step |
| `Ctrl+Arrow Left` / `Ctrl+Arrow Up` | Previous step |
| `Ctrl+Enter` | Go to next step (when valid) |
| `?` | Show shortcuts panel |
| `Esc` | Back to homepage (from Step 1) |

---

## Deployment

### Vercel (Recommended)

1. Push the repository to a Git branch
2. Import the project in [Vercel](https://vercel.com)
3. Vercel auto-detects the Next.js framework and configures the build
4. No environment variables are required for the core functionality
5. Set `NEXT_PUBLIC_SITE_URL` for proper canonical URLs and OG images

### Docker

```dockerfile
FROM node:18-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

FROM node:18-alpine AS runner
WORKDIR /app
COPY --from=builder /app/.next/standalone ./
COPY --from=builder /app/.next/static ./.next/static
COPY --from=builder /app/public ./public
EXPOSE 3000
ENV NODE_ENV=production
CMD ["node", "server.js"]
```

### Self-Hosted

```bash
npm run build
npm start  # Starts on port 3000 using standalone server
```

The production build uses Next.js standalone output for optimal cold starts and minimal server resource usage (~80MB total).

---

## Design System

ThesisForge uses a custom design token system defined in `src/ui/tokens.css`:

- **9-step type scale** — from `text-xs` (11px) to `text-5xl` (48px)
- **Semantic color palette** — oklch-based with light/dark theme variants (background, foreground, primary, secondary, muted, accent, destructive, card, popover, border, input, ring)
- **Elevation system** — 4 shadow levels (sm, md, lg, xl) with theme-aware opacity
- **Motion language** — 4 timing presets (instant 80ms, fast 150ms, normal 220ms, slow 350ms) with 3 easing curves (snap, smooth, bounce)
- **Spacing scale** — 4px grid system with semantic names (space-1 through space-12)
- **Component tokens** — Issue cards, reference items, step dots, score rings, template cards, and more

Styling is split between:
- `globals.css` — Theme variables, component CSS classes, animations, utilities
- `tokens.css` — Raw design tokens consumed by Tailwind CSS 4's `@theme` directive
- Tailwind utility classes — Applied in JSX for layout, spacing, and responsive design

---

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/my-feature`
3. Make your changes and ensure the build passes: `npm run build`
4. Commit with descriptive messages: `git commit -m "feat: add my feature"`
5. Push to your branch: `git push origin feature/my-feature`
6. Open a Pull Request

### Code Style

- TypeScript strict mode with explicit types for public APIs
- React functional components with hooks (no class components except error boundaries)
- Tailwind CSS utility classes for styling (avoid inline styles)
- Zustand stores with granular selectors to minimize re-renders
- `React.memo` for expensive child components
- `useCallback` for handler functions passed as props
- shadcn/ui primitives for all interactive UI elements

---

## License

MIT

---

## Changelog

### v2.2 — April 2026

**Mobile & Accessibility Fixes:**
- Fixed wizard footer safe-area: changed from fixed `h-[72px]` to `min-h-[72px]` so iOS safe-area padding expands the footer instead of squishing button content
- Added global `overscroll-behavior: contain` on `html` to prevent browser pull-to-refresh from interfering with scroll areas on mobile
- Added safe-area bottom padding to the editor preview Sheet on mobile (iOS home indicator cut-off)

**Previous Fixes (v2.1):**
- Fixed tablet dead-zone (640px-768px) where intelligence panel was invisible
- Fixed Sheet collision: staggered intelligence panel open by 150ms to prevent overlay conflicts
- Fixed Sheet safe-area padding for clean mobile panel rendering
- Removed `forceOpen` prop from Sheet component that bypassed Radix state machine
- Fixed `isNarrow` SSR hydration mismatch (initialized to false, corrected on mount)

**Previous Fixes (v2.0):**
- Fixed `handleExport` stale closure
- Fixed citation styles H1 showing SEO keyword instead of human-readable title
- Fixed citation breadcrumb hardcoded link
- Replaced API placeholder with health check endpoint
- Added 2MB body size limit and JSON parse error handling to generate-latex API
- Fixed blog future dates
- Replaced `router.push` with Next.js `Link` in blog navigation
- Added blog URLs and editor route to sitemap
