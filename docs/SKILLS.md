# Skills You'll Learn

This project is designed to teach real-world full-stack development. Here's what you'll pick up at each phase.

---

## Next.js (App Router)

- **File-based routing** — folders become routes, `page.tsx` renders the page
- **Layouts** — shared UI without re-rendering (`layout.tsx`)
- **Server Components** — render on the server, no JS sent to client by default
- **Client Components** — `"use client"` — when you need interactivity, hooks, browser APIs
- **Server Actions** — run server-side code from a form or button, no API route needed
- **Dynamic routes** — `[id]` folders for parameterized pages
- **Metadata API** — `export const metadata` for SEO
- **Loading and Error UI** — `loading.tsx`, `error.tsx` per route segment
- **Middleware** — intercept requests (auth guards, redirects)

## TypeScript

- Typing API responses (Consumet data shapes)
- Typing Supabase query results
- Generics, utility types (`Partial`, `Pick`, `Omit`)
- Understanding when `any` is a red flag

## Supabase / PostgreSQL

- Creating tables with proper types and constraints
- Foreign keys and relationships
- **Row Level Security (RLS)** — the most important Supabase concept
  - Writing policies like "user can only update rows where `user_id = auth.uid()`"
- Using the Supabase JS client: `select`, `insert`, `update`, `delete`
- Server vs browser Supabase clients (important distinction)
- Auth flow: sign up, sign in, session management, cookies

## shadcn/ui

- How component libraries built on Radix UI work
- Composing UI from primitives (Dialog, DropdownMenu, Tooltip, etc.)
- Customizing components via Tailwind classes and `cn()` utility
- Understanding the difference between "headless" and "styled" component libraries

## Docker

- Writing a `Dockerfile` for a Node.js app
- Multi-stage builds (build stage vs runtime stage)
- `docker-compose.yml` for running multiple services
- Environment variables in containers
- Basic Docker commands: `build`, `run`, `compose up/down`

## Web Fundamentals

- HTTP request/response cycle
- REST API consumption (Consumet API)
- Cookies vs localStorage for auth tokens
- When to fetch on the server vs the client

## Software Design

- Separating concerns — data fetching, UI, business logic
- Database schema design for social features (comments, reactions, replies)
- Caching strategies — why cache third-party API data
- Feature-driven development — build vertical slices, not horizontal layers

---

## Agent Skills (Installed)

These skills are installed locally and guide best practices as we build:

| Skill | What it Teaches |
|-------|----------------|
| `nextjs-app-router-patterns` | App Router conventions, data fetching patterns, Server vs Client components |
| `nextjs-supabase-auth` | Wiring Supabase Auth into Next.js correctly (cookies, middleware, server client) |
| `supabase-postgres-best-practices` | Schema design, RLS policies, indexing, Postgres conventions |
| `find-skills` | Discover and install more skills as we need them |

---

## Learning Order (Recommended)

1. Next.js routing + Server Components basics
2. Fetching from Consumet API (data layer)
3. shadcn/ui components (UI layer)
4. Supabase setup + tables (database layer)
5. Supabase Auth (identity)
6. RLS policies (security)
7. Comments + reactions (social features)
8. Docker + Consumet self-hosted instance (deployment)
