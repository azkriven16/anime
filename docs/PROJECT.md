# Anime Scraper App — Project Overview

## What We're Building

A full-stack web app where users can browse scraped anime data, comment, reply, and react — all behind authentication.

## High-Level Architecture

```
Browser (Next.js Frontend)
     |
     |-- Server Components / Server Actions
     |-- Supabase (Auth + DB)
     |-- Scraper Layer (Next.js API Routes or cron)
     |
  Docker Container
```

## Scraping Strategy

We'll use the **Consumet API** (https://github.com/consumet/api.consumet.org) — an open-source anime/manga data aggregation API.
- Pulls from multiple sources: AniList, MyAnimeList, streaming sites, and more
- Self-hostable — we can run our own instance inside Docker alongside the app
- Covers anime metadata, episodes, streaming links, genres, characters, etc.
- We'll fetch and cache results in Supabase so we're not hammering the API on every request

This is true scraping infrastructure — Consumet scrapes the upstream sites so we don't have to.

## Pages / Routes (Planned)

| Route | Description |
|-------|-------------|
| `/` | Home — trending/top anime |
| `/anime/[id]` | Anime detail page |
| `/anime/[id]/comments` | Comments section |
| `/search` | Search anime |
| `/profile` | User profile |
| `/auth/login` | Login |
| `/auth/register` | Register |

## Key User Flows

1. Browse anime without logging in (read-only)
2. Log in via Supabase Auth (email or OAuth)
3. Comment on an anime
4. Reply to a comment (nested)
5. React to a comment (like, etc.)
6. View your own profile and activity
