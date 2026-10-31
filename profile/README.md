<div align="center">

# 🛍️ Ukaaz | عکاظ

### AI-Powered Auction & E-Commerce Marketplace
**UIT University · Final Year Project (FYP 2026–2027) · Group 11**

[![Fastify](https://img.shields.io/badge/Fastify-v5-black?style=flat&logo=fastify)](https://fastify.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue?style=flat&logo=typescript)](https://www.typescriptlang.org/)
[![Flutter](https://img.shields.io/badge/Flutter-3.x-02569B?style=flat&logo=flutter)](https://flutter.dev/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-336791?style=flat&logo=postgresql)](https://www.postgresql.org/)
[![Drizzle ORM](https://img.shields.io/badge/Drizzle_ORM-0.38-C5F74F?style=flat&logo=drizzle)](https://orm.drizzle.team/)
[![Redis](https://img.shields.io/badge/Redis-7-DC382D?style=flat&logo=redis)](https://redis.io/)

<p align="center">
  A modern, high-throughput commerce ecosystem engineered specifically for Pakistani online commerce.<br />
  Combining fixed-price storefronts with real-time auctions, escrow settlement, and automated fraud prevention.
</p>

---

</div>

## 📌 About Ukaaz

Traditional e-commerce in emerging markets often faces low buyer trust, non-serious bidding, and counterparty delivery defaults. **Ukaaz** (inspired by the historical *Souq Ukaz*) modernizes market trading by providing:

* ⏱️ **Real-Time & Scheduled Auctions**: High-concurrency bidding engine with sub-second websocket state propagation, anti-sniping dynamic time extensions, and automated reserve price enforcement.
* 🛡️ **Escrow Transaction Settlement**: Structured multi-phase buyer protection holding funds securely until milestone delivery verification.
* 🤖 **AI-Assisted Operations**: Automated catalog enrichment, market pricing guidance, and fraudulent/shill bid pattern detection.
* 📦 **Omnichannel Order & Inventory Lifecycle**: Unified management across direct purchases and competitive auctions.

---

## 🏛️ Ecosystem Architecture

```
                    ┌───────────────────────────────┐
                    │      Ukaaz Mobile Client      │
                    │   (Flutter 3 + Riverpod)     │
                    └───────────────┬───────────────┘
                                    │  HTTPS / WSS
                                    ▼
                    ┌───────────────────────────────┐
                    │      Ukaaz Core Server        │
                    │   (Fastify v5 TypeScript)    │
                    └───┬───────────┬───────────┬───┘
                        │           │           │
          ┌─────────────┴──┐  ┌─────┴──────┐  ┌─┴───────────────┐
          │   PostgreSQL   │  │   Redis    │  │ S3-Compatible   │
          │  (Drizzle ORM) │  │ (Pub/Sub)  │  │ Storage (MinIO) │
          └────────────────┘  └────────────┘  └─────────────────┘
```

---

## 📂 Active Repositories

| Repository | Scope & Description | Tech Stack |
| :--- | :--- | :--- |
| [**`ukaaz-server`**](https://github.com/ukaaz/ukaaz-server) | Modular monolith backend server with REST APIs, WebSocket gateways, escrow state machine, and database layer. | Fastify v5, TypeScript, Drizzle ORM, Better Auth, PostgreSQL, Redis |
| [**`ukaaz-mobile`**](https://github.com/ukaaz/ukaaz-mobile) | Customer and merchant mobile application following a strict repository pattern with typed routing. | Flutter, Dart, Riverpod, GoRouter, Retrofit/Dio, Talker |

---

## 👥 FYP Group 11 Roster

| Name | Role | Responsibilities |
| :--- | :--- | :--- |
| **Sahir Ul Hassan** | Project Lead / System Architect | Overall system architecture, database schema, core plugins, PR reviews, CI/CD pipelines |
| **Javaria Owais** | Full-Stack Developer | Feature module implementation, business services, integration testing |
| **Kainat Bintay Faisal** | Full-Stack Developer | Feature module implementation, API routes, schema validation |
| **Zunaira Manzoor** | Full-Stack Developer | Feature module implementation, mobile integration, documentation |

---

## 📋 Engineering Standards

All repositories under the `ukaaz` organization follow strict development practices:
* **Conventional Commits**: `feat:`, `fix:`, `refactor:`, `chore:`, `docs:` commit messages.
* **Feature Branching**: Branches originate from `main` using `feature/<module>` or `fix/<ticket>`.
* **Automated Quality Checks**: Formatting and linting (Biome for server, Dart/Flutter analyze for mobile) must pass on every change.

For detailed guidelines, please refer to our [Contributing Guide](https://github.com/ukaaz/.github/blob/main/CONTRIBUTING.md).
