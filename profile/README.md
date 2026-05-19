# Interkom

> Internal chat for modern teams.

A focused, end-to-end team-messaging product — workspaces, DMs, group chats, channels, announcements, stories, voice messages, push, and search — across iOS, macOS, and the web, with **Supabase** (Postgres + RLS, Auth, Realtime, Storage, Edge Functions) as the backend of record.

## Repositories

### Clients

| Repo | Stack | Status |
| --- | --- | --- |
| [`interkom-ios`](https://github.com/interkom-app/interkom-ios) | Swift, SwiftUI, The Composable Architecture | Beta |
| [`interkom-mac`](https://github.com/interkom-app/interkom-mac) | Swift, SwiftUI, The Composable Architecture | In progress |
| [`interkom-web`](https://github.com/interkom-app/interkom-web) | Next.js 16, React 19, Tailwind v4 | In progress |

### Shared

| Repo | Purpose |
| --- | --- |
| [`interkomkit`](https://github.com/interkom-app/interkomkit) | Swift package — domain models, Supabase repositories, caching, push, design tokens. Consumed by `interkom-ios` and `interkom-mac`. |

### Marketing

| Repo | Purpose |
| --- | --- |
| [`interkom-homepage`](https://github.com/interkom-app/interkom-homepage) | Landing page. Vite + React + TypeScript + Tailwind v4. |

Cloned side-by-side, the Swift clients use a local `.package(path: "../interkomkit")` dep so the package and apps iterate together.

## Features

- **Workspaces** with invites, admin controls, per-workspace settings
- **DMs, group chats, and channels** with reactions, replies, mentions, voice messages, files, and images
- **Announcements channel** — company-wide feed of posts (admins post; everyone reads)
- **Stories / reels** for lightweight async updates
- **Push notifications** with deep-linking and per-chat notification levels (all / mentions / muted)
- **Search** across people, chats, and messages — including jump-to-message with pagination through older history

## Backend

Supabase project shared by all clients: Postgres with row-level security policies, Auth, Realtime channels for live chat/typing/presence, Storage for attachments and avatars, Edge Functions for the bits that don't fit in SQL.

## Status

Beta on iOS. Pre-1.0 across the suite.
