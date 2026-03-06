# Feature Checklist

Legend: [ ] = not started | [~] = in progress | [x] = done

---

## Phase 1 — Project Setup

- [ ] Initialize Next.js 16 app with TypeScript (`create-next-app`)
- [ ] Install and configure Tailwind CSS
- [ ] Install shadcn/ui and add base components
- [ ] Set up Supabase project (cloud)
- [ ] Connect Supabase to Next.js (env vars, client utils)
- [ ] Write Dockerfile for Next.js app
- [ ] Add Consumet API service to docker-compose.yml
- [ ] Write docker-compose.yml (Next.js + Consumet)
- [ ] Confirm app + Consumet run inside Docker

## Phase 2 — Anime Data (Consumet API)

- [ ] Explore Consumet API endpoints (top anime, search, details, episodes)
- [ ] Create a server-side fetch utility for Consumet
- [ ] Build home page — display top/trending anime
- [ ] Build search page with query params
- [ ] Build anime detail page `/anime/[id]`
- [ ] Cache fetched anime in Supabase `anime_cache` table (optional but good practice)

## Phase 3 — Auth

- [ ] Set up Supabase Auth (email/password)
- [ ] Create login page
- [ ] Create register page
- [ ] Protect routes (middleware or layout guards)
- [ ] Create `profiles` table linked to `auth.users`
- [ ] Show login/logout in nav

## Phase 4 — Comments

- [ ] Create `comments` table in Supabase
- [ ] Add RLS policies (users can only edit/delete own comments)
- [ ] Build comment form (Server Action)
- [ ] Display comments list on anime detail page
- [ ] Support reply-to-comment (nested/threaded)
- [ ] Delete own comment

## Phase 5 — Reactions

- [ ] Create `comment_reactions` table
- [ ] Add RLS policies
- [ ] Build reaction UI (like button, count)
- [ ] Toggle reaction on/off
- [ ] Show who reacted (optional)

## Phase 6 — Profile Page

- [ ] User profile page `/profile`
- [ ] Show user's comments
- [ ] Show user's reactions
- [ ] Edit display name / avatar (optional)

## Phase 7 — Polish

- [ ] Loading states and skeletons
- [ ] Error boundaries
- [ ] Mobile responsive layout
- [ ] SEO metadata per page
- [ ] Dark mode (shadcn/ui supports this out of the box)

## Stretch Goals

- [ ] Realtime comments via Supabase Realtime
- [ ] Watchlist feature (save anime)
- [ ] OAuth login (Google / Discord)
- [ ] Rate limiting on API routes
- [ ] Deploy to a hosting platform (Vercel, Fly.io, etc.)
