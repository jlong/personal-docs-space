# Next.js App Conventions

Conventions and patterns for Next.js apps.

## Tech Stack

- **Framework**: Next.js 15+ (App Router), React 18, TypeScript (strict mode)

- **Styling**: Tailwind CSS with custom design system

- **Database**: PostgreSQL via Prisma ORM

- **Auth**: WorkOS AuthKit with middleware-based route protection

- **Real-time**: TipTap + Hocuspocus + Yjs for collaborative editing

- **Testing**: Jest (unit), Playwright (E2E)

- **Hosting**: Vercel

## Directory Structure

```
app/
  (auth)/          # Auth pages (login, onboarding) — route group
  (main)/          # Main app pages (workspaces, tasks, pages) — route group
  api/v1/          # Versioned API routes
  layout.tsx       # Root layout
  globals.css      # Global styles

components/        # Reusable React components
  Chrome/          # Application shell (sidebar, navigation)
  Editor/          # TipTap-based rich text editor
  RichText/        # Rich text display/editing
  Button.tsx       # Standalone components at root level
  Avatar.tsx
  Box.tsx
  Form.tsx

lib/
  models/          # Database models & business logic (tasks, pages, users, workspaces)
  server/          # Server-only utilities (marked with `server-only` import)
  client/          # Client-only utilities
  shared/          # Shared utils (cn, colors, markdown, timeAgoInWords)
  hooks/           # React hooks
  editor/          # Editor config and TipTap extensions
  validation/      # Zod schemas
  utils/           # General utilities
  auth.ts          # Auth helpers
  database.ts      # Prisma client

prisma/
  schema.prisma    # Database schema
  seed.ts          # Database seeding
  migrations/      # Migration files

tests/
  e2e/             # Playwright specs (*.spec.ts)
  unit/            # Jest tests (*.test.ts / *.test.tsx)
  fixtures/        # Test fixtures

stories/           # Storybook stories
icons/             # SVG icon components (all use Base wrapper pattern)
```

## Component Conventions

### File Naming & Structure

- Component files use **camelCase** file names with **.tsx** extension

- Component functions use **PascalCase** names

- Complex components get their own directory (e.g., `Chrome/`)

- **Barrel exports** (`index.tsx`) used for directory-based components

### Props & TypeScript

- All components have typed props via TypeScript interfaces

- Extend `React.ComponentPropsWithoutRef<'element'>` when wrapping native elements

- Use `PropsWithChildren` for components accepting children

- No `any` types — define proper interfaces

### Server vs Client Components

- **Server components** are the default (no directive needed)

- **Client components** marked with `'use client'` at top of file

- Server-only utilities use `import 'server-only'` guard

- Prefer server components unless client interactivity is needed

### Styling

- **Tailwind CSS exclusively** — no custom CSS files, no inline styles

- Use `cn()` function (from `@/lib/shared/cn`) for conditional class merging (clsx + tailwind-merge)

- Define `styles` objects with state-based keys for complex components:

  ```tsx
  const styles = {
    base: 'rounded-lg font-medium',
    kind: { primary: 'bg-brand text-white', secondary: 'bg-quiet' },
    size: { small: 'px-2 py-1 text-sm', medium: 'px-4 py-2' }
  }
  ```

- Multi-line Tailwind: each responsive breakpoint on its own line, aligned vertically

- Semantic color names from custom theme (brand, accent, quiet, normal, loud, heading, success, danger, warning)

## Page & Layout Conventions

### Pages

- Async server components by default

- Use `params` as `Promise<{...}>` (Next.js 15+ convention)

- Fetch data directly in the component

- Use `generateMetadata` for page titles

### Layouts

- Use `requireSessionUser` helper for protected layouts

- Wrap children in `<Suspense>` for lazy loading

- Fetch workspace context and pass to Chrome shell

## API Route Conventions

- Located in `app/api/v1/` (versioned)

- Named exports for HTTP methods: `GET`, `POST`, `PUT`, `DELETE`

- Accept `NextRequest`, return `Response.json()`

- Auth via `getAuthenticatedSessionUser()`

- Consistent error format with proper status codes (400, 401, 500)

## Server Action Conventions

- Co-located `actions.ts` files alongside pages

- Marked with `'use server'` directive

- Authenticate with `getAuthenticatedSessionUser()`

- Validate workspace membership

- Call model functions for DB work

- Use `revalidatePath()` for cache invalidation

## Model/Data Layer Conventions

### Prisma Models

- Export both selection objects and derived types using `satisfies Prisma.XSelect`

- Derive types with `Prisma.XGetPayload<{ select: typeof XSelect }>`

- Rich text stored as JSON (TipTap format)

- UUIDs for task IDs, auto-increment for others

- Soft deletes via `isArchived` boolean

- Indexes on frequently queried fields

### Server Utilities

- Use React's `cache()` for request-level memoization

- Authorization checks in all queries: `workspace: { users: { some: { userId } } }`

- Input validation with Zod schemas

- Rich text sanitization before storing

## Test Conventions

### Unit Tests (Jest)

- Files: `tests/unit/**/*.test.ts(x)`

- React Testing Library for component tests

- Mock complex dependencies with `jest.mock()`

- Use `data-testid` attributes for targeting

### E2E Tests (Playwright)

- Files: `tests/e2e/**/*.spec.ts`

- Auth helpers in `tests/e2e/utils/auth-helpers.ts`

- `test.describe()` blocks with `test()` cases

## Config Highlights

### Tailwind (`tailwind.config.js`)

- Custom hues with 100-700 levels

- 8px base unit spacing scale

- Custom animations (fade, slide-and-fade, drawer-slide)

- Typography plugin for headings/lists

### TypeScript (`tsconfig.json`)

- Strict mode enabled

- `@/*` path alias for absolute imports

### Imports

- Use absolute imports: `@/lib/...`, `@/components/...`

- No semicolons (Prettier config)

## Code Style Quick Reference

- 2-space indentation

- No semicolons (unless necessary)

- camelCase for variables/functions, PascalCase for components/classes/constants

- Single quotes for strings

- Async/await over raw promises

- Comments explain "why", not "what"

- Functional components only — no class components
