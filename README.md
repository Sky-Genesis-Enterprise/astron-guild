# 🌐 Astron — Guild Center

**Guild Center** is an open-source application within the [Astron](https://astron-collection.com) ecosystem. It serves as a public, modular, and real-time guild directory — similar to Disboard or Top.gg — fully integrated with Astron bots. Server owners can create a public profile, receive votes and bumps, and link their guilds into collective hubs.

---

## 🚀 Key Features

- 🔎 **Advanced search and filtering** of listed public guilds
- 📢 **Public profile pages** for each server, with stats, tags, and banners
- 🗳️ **Voting and bumping system** with anti-spam handling
- 🧑‍🤝‍🧑 **Guild hubs** to group multiple servers under a shared identity
- 🔗 **Direct integration with Astron bots** to automate bumps and track stats
- 🛡️ **Optional moderation** of listed profiles (handled by Sky Genesis Enterprise)
- 🧠 Seamless **integration with Astron Dashboard**, unlocking more features

---

## 🔧 Technical Overview

| Layer | Stack |
|-------|-------|
| **Frontend** | React + TypeScript (TSX) |
| **Backend API** | Node.js (Express) via `https://api.astron-collection.com` |
| **Database** | PostgreSQL (hosted on o2switch) |
| **Discord Bot** | Discord.js (v14+) |
| **Authentication** | Discord OAuth2 (user login + guild ownership check) |

---

## 🛠️ Getting Started

### Requirements

- Node.js v18+
- PostgreSQL
- A Discord bot with scopes: `bot`, `applications.commands`, `identify`, `guilds`

### 1. Clone the Repository

```bash
git clone https://github.com/Sky-Genesis-Enteprise/astron-guild.git
cd guild-center
````

### 2. Environment Setup

Copy the example env file:

```bash
cp .env.example .env
```

Fill in your own values:

```env
DISCORD_CLIENT_ID=...
DISCORD_CLIENT_SECRET=...
DISCORD_BOT_TOKEN=...
API_BASE_URL=https://api.astron-collection.com
POSTGRES_URL=postgresql://user:pass@localhost:5432/guildcenter
```

### 3. Start the Frontend (Vite)

```bash
cd frontend
npm install
npm run dev
```

### 4. Start the API

```bash
cd api
npm install
npm run dev
```

---

## ✨ Usage

1. Log in via Discord on [Guild Center](https://astron-collection.com/guild-center)
2. Select one of your guilds and make it public
3. Customize its profile (description, tags, banner, etc.)
4. Invite the Astron bot to your guild to enable bumping and voting
5. Share your guild or hub page with your community!

---

## 📌 Core API Endpoints

* `GET /guilds/public` – List all public guilds with filters
* `GET /guild/:id` – Get full details of a guild
* `POST /guild/:id/bump` – Bump the guild (rate-limited)
* `POST /guild/:id/vote` – Vote for a guild (OAuth2)
* `PATCH /guild/:id` – Update guild info (owner only)

---

## 🔐 Permissions & Security

* Only guild owners or admins (via RBAC) can manage public listings
* Anti-spam throttling for voting and bumping
* All user actions are tied to their Discord account via OAuth2

---

## 🧑‍💻 Contributing

We welcome community contributions! Please read [`contributing.md`](.github/CONTRIBUTING.md) before submitting a pull request.

```bash
# Fork, then create a feature branch:
git checkout -b feature/your-feature-name
```

---

## 🧠 About

Developed and maintained by **Sky Genesis Enterprise** as part of the [Astron](https://astron-collection.com) suite.
Contact: [`support@skygenesisenterprise.com`](mailto:support@skygenesisenterprise.com)

## 📄 License

This project is released under the **AGPLv3 licence**.
See [`LICENSE`](./LICENSE) for details.