# Interkom

> A private social network for your company.

Chat, group chats, channels, company announcements, stories, voice notes,
audio/video calls, presence, and search — **end-to-end encrypted**,
workspace-scoped, with no public feed — across **iOS, macOS, and the web**.
Built on a lean-native **AWS** backend (Cognito, API Gateway + Lambda over
Aurora, AWS IoT, S3 / CloudFront).

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
| [`interkomkit`](https://github.com/interkom-app/interkomkit) | Swift package — domain models, AWS-backed repositories, caching, realtime, push, E2EE, and design tokens. Consumed by `interkom-ios` and `interkom-mac`. Also home to **`FEATURES.md`**, the canonical capability inventory for all three clients. |
| [`interkom-aws`](https://github.com/interkom-app/interkom-aws) | Infrastructure-as-code (Terraform) + backend services — Cognito, API Gateway + Lambda over Aurora, AWS IoT realtime, S3 / CloudFront. |

### Marketing & releases

| Repo | Purpose |
| --- | --- |
| [`interkom-homepage`](https://github.com/interkom-app/interkom-homepage) | Landing page — Vite + React + TypeScript + Tailwind v4. Deployed to GitHub Pages at [interkom.app](https://interkom.app); also serves the macOS Sparkle appcast at `/mac/appcast.xml`. |
| [`interkom-releases`](https://github.com/interkom-app/interkom-releases) | Public download artifacts (macOS DMG, …) for the apps. |

Cloned side-by-side, the Swift clients use a local `.package(path: "../interkomkit")` dep so the package and apps iterate together.

## Features

- **Workspaces** with invites, admin controls, per-workspace settings and profiles, and multi-account switching
- **DMs, group chats, and channels** with reactions, replies, mentions, voice messages, files, and images
- **End-to-end encryption** — per-device key wrapping; on encrypted workspaces the server only ever stores ciphertext it can't read
- **Audio / video calls** with screen sharing and an in-call group grid — CallKit on iOS, in-app ringing on macOS (web in progress)
- **Announcements channel** — company-wide feed of posts (admins post; everyone reads)
- **Stories / reels** for lightweight, 24-hour async updates
- **Presence & live updates** — typing indicators, read state, realtime delivery
- **Push notifications** with deep-linking and per-chat notification levels (all / mentions / muted)
- **Search** across people, chats, and messages — including jump-to-message with pagination through older history

See [`interkomkit/FEATURES.md`](https://github.com/interkom-app/interkomkit/blob/main/FEATURES.md) for the full, authoritative capability list the iOS, macOS, and web clients are kept in lockstep with.

## Backend

A lean-native **AWS** stack shared by every client, replacing the original
Supabase backend:

- **Amazon Cognito** — authentication and user pools
- **API Gateway (HTTP API) + AWS Lambda** — a data-API over **Aurora Serverless v2 (PostgreSQL)**
- **AWS IoT Core (MQTT)** — realtime chat, typing, presence, and call signaling
- **Amazon S3 + CloudFront** — attachments, avatars, and media
- **Stripe** for billing; **APNs** for push

Infrastructure and services live in [`interkom-aws`](https://github.com/interkom-app/interkom-aws).

## Status

Beta across iOS, macOS, and web. Pre-1.0 throughout the suite.
