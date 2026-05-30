# Interkom

> A private social network for your company.

Chat, group chats, channels, company announcements, stories, voice notes,
presence, and search — workspace-scoped, with no public feed — across **iOS,
macOS, and the web**. Built on **Supabase** (Postgres + RLS, Auth, Realtime,
Storage, Edge Functions) as the backend of record.

🌐 [interkom.app](https://interkom.app) &nbsp;·&nbsp; 💬 [web.interkom.app](https://web.interkom.app)

## Repositories

### Clients

| Repo | Stack | Status |
| --- | --- | --- |
| [`interkom-ios`](https://github.com/interkom-app/interkom-ios) | Swift, SwiftUI, The Composable Architecture | Beta |
| [`interkom-mac`](https://github.com/interkom-app/interkom-mac) | Swift, SwiftUI, The Composable Architecture | Beta |
| [`interkom-web`](https://github.com/interkom-app/interkom-web) | Next.js 16, React 19, Tailwind v4 (Cloudflare Workers / OpenNext) | Beta · [web.interkom.app](https://web.interkom.app) |

### Shared & backend

| Repo | Purpose |
| --- | --- |
| [`interkomkit`](https://github.com/interkom-app/interkomkit) | Swift package — domain models, Supabase repositories, caching, push, design tokens. Consumed by `interkom-ios` and `interkom-mac`. Also home to **`FEATURES.md`**, the canonical capability inventory for all three clients. |
| [`supabase`](https://github.com/interkom-app/supabase) | Database migrations and Edge Functions for the shared Supabase project. |

### Marketing & releases

| Repo | Purpose |
| --- | --- |
| [`interkom-homepage`](https://github.com/interkom-app/interkom-homepage) | Landing page — Vite + React + TypeScript + Tailwind v4. Deployed to GitHub Pages at [interkom.app](https://interkom.app); also serves the macOS Sparkle appcast at `/mac/appcast.xml`. |
| [`interkom-releases`](https://github.com/interkom-app/interkom-releases) | Public download artifacts (macOS DMG, …) for the apps. |

Cloned side-by-side, the Swift clients use a local `.package(path: "../interkomkit")` dep so the package and apps iterate together.

## Features

- **Workspaces** with invites, admin controls, per-workspace settings and profiles
- **DMs, group chats, and channels** with reactions, replies, mentions, voice messages, files, and images
- **Announcements channel** — company-wide feed of posts (admins post; everyone reads)
- **Stories / reels** for lightweight, 24-hour async updates
- **Presence & live updates** — typing indicators, read state, realtime delivery
- **Push notifications** with deep-linking and per-chat notification levels (all / mentions / muted)
- **Search** across people, chats, and messages — including jump-to-message with pagination through older history

See [`interkomkit/FEATURES.md`](https://github.com/interkom-app/interkomkit/blob/main/FEATURES.md) for the full, authoritative capability list the iOS, macOS, and web clients are kept in lockstep with.

## Backend

A single Supabase project shared by every client: Postgres with row-level
security policies, Auth, Realtime channels for live chat / typing / presence,
Storage for attachments and avatars, and Edge Functions for the bits that
don't fit in SQL. Schema changes live in [`supabase`](https://github.com/interkom-app/supabase).

## Status

Beta across iOS, macOS, and web. Pre-1.0 throughout the suite.
