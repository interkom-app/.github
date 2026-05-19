# Interkom

> Internal chat for modern teams.

Built with **SwiftUI**, the **Composable Architecture** (TCA), and **Supabase** (Postgres, Auth, Realtime, Storage, Edge Functions). One shared Swift package — `InterkomKit` — powers iOS today and macOS next.

## Repositories

| Repo | Purpose |
| --- | --- |
| [`interkom-ios`](https://github.com/interkom-app/interkom-ios) | iOS app target (SwiftUI + TCA, consumes `InterkomKit`) |
| [`interkomkit`](https://github.com/interkom-app/interkomkit) | Shared Swift package — domain models, Supabase repositories, caching, push, design tokens |

## What you can do

- **Workspaces** with invites, roles, and admin controls
- **DMs, group chats, and channels** with reactions, mentions, replies, voice messages, files, and images
- **Announcements channel** — company-wide posts that read like a feed
- **Stories / reels** for lightweight async updates
- **Push notifications** with deep-linking and per-chat notification levels
- **Search** across people, chats, and messages

## Stack

- Swift 6, SwiftUI, Swift Concurrency
- The Composable Architecture (pointfreeco)
- Supabase (Postgres + RLS, Auth, Realtime, Storage, Edge Functions)
- iOS 18+, macOS 14+

## Status

Beta. Pre-1.0, iterating.
