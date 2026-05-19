# Interkom

> Internal chat for modern teams.

A focused, end-to-end team-messaging app — workspaces, DMs, group chats, channels, announcements, stories, voice messages, push, and search — built with **SwiftUI**, the **Composable Architecture** (TCA), and **Supabase** (Postgres + RLS, Auth, Realtime, Storage, Edge Functions).

Currently shipping on iOS; macOS is next, sharing the same `InterkomKit` package.

## Repositories

| Repo | Purpose |
| --- | --- |
| [`interkom-ios`](https://github.com/interkom-app/interkom-ios) | iOS app target. SwiftUI + TCA. Bundle ID `app.interkom.ios`. |
| [`interkomkit`](https://github.com/interkom-app/interkomkit) | Shared Swift package — domain models, Supabase repositories, caching, push, design tokens. Consumed by every Interkom client. |

Cloned side-by-side, the iOS app uses a local `.package(path: "../interkomkit")` dependency so both repos can iterate together.

## Features

- **Workspaces** with invites, admin controls, per-workspace settings
- **DMs, group chats, and channels** with reactions, replies, mentions, voice messages, files, and images
- **Announcements channel** — company-wide feed of posts (admins post; everyone reads)
- **Stories / reels** for lightweight async updates
- **Push notifications** with deep-linking and per-chat notification levels (all / mentions / muted)
- **Search** across people, chats, and messages — including jump-to-message with pagination through older history

## Stack

- Swift 6, SwiftUI, Swift Concurrency
- The Composable Architecture (pointfreeco/swift-composable-architecture)
- Supabase (Postgres + RLS, Auth, Realtime, Storage, Edge Functions)
- Targets: iOS 18+, macOS 14+ (planned)

## Status

Beta. Pre-1.0, iterating fast.
