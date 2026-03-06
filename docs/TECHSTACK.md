# Tech Stack

## Frontend

| Tool | Purpose | Why |
|------|---------|-----|
| **Next.js 16** | Full-stack React framework | App Router, Server Components, Server Actions, API Routes |
| **TypeScript** | Type safety | Catches bugs early, better DX |
| **Tailwind CSS** | Utility-first styling | Pairs perfectly with shadcn/ui |
| **shadcn/ui** | Component library | Accessible, composable, unstyled at core |

## Backend / Data

| Tool | Purpose | Why |
|------|---------|-----|
| **Supabase** | Database + Auth + Realtime | Postgres under the hood, great DX, free tier |
| **Consumet API** | Anime data source | Aggregates multiple anime sources (AniList, MAL, streaming sites), self-hostable |
| **Next.js API Routes / Server Actions** | Backend logic | Colocated with frontend, no separate server needed |

## Auth & Security

- **Supabase Auth** — email/password + optional OAuth (Google, Discord)
- **Cloudflare Turnstile** — bot protection widget on register + comment forms (works on any host, not just Cloudflare)
  - Client: embed the `<script>` widget, get a token on submit
  - Server: POST the token to `https://challenges.cloudflare.com/turnstile/v0/siteverify`
  - If verification fails, reject the request before touching the DB
- Row Level Security (RLS) on Supabase tables to protect data at the DB level

## Hosting & Infrastructure

| Tool | Purpose |
|------|---------|
| **Vercel** | Host the Next.js app — auto-deploys on every push to main |
| **GitHub** | Source control + triggers Vercel deployments |
| **Docker** | Local dev + Consumet self-hosted instance |
| **docker-compose** | Orchestrate Next.js + Consumet locally |

## Database Schema (Planned)

```
profiles       — extends Supabase auth.users
anime_cache    — cached anime data from Consumet
comments       — user comments on anime
comment_reactions — likes/reactions on comments
```

## Key Concepts Per Tool

### Next.js App Router
- `app/` directory structure
- Server Components (default) vs Client Components (`"use client"`)
- Server Actions for form submissions / mutations
- Route handlers (`route.ts`) for API endpoints

### Supabase
- `createClient` for server vs browser contexts (different clients!)
- RLS policies: who can SELECT / INSERT / UPDATE / DELETE
- Realtime subscriptions (optional: live comments)

### shadcn/ui
- Not installed as a package — components are copied into your project
- Fully customizable, Radix UI primitives underneath
- Run `npx shadcn@latest add <component>` to add components

### Docker
- `Dockerfile` for the Next.js app
- Multi-stage builds to keep image small
- `docker-compose.yml` to wire services together
