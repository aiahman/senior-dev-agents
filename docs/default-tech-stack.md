# Senior Dev Agents: default tech stack

Date: 2026-11-26. Draft for Aiah's review. Nothing is installed or set up.

**The rule:** every tool starts on the **Default** column. An agent switches to an **Option** only for the reason written next to it, and says why in the project's architecture notes (documentation-and-adrs skill).
**The idea behind it:** one language everywhere (TypeScript), Cloudflare as the foundation for hosting, edge and security, and only tools our agents already have skills for. Where no skill exists yet, the row says **Skill gap**.

## Foundation (used by every tool)

| Layer | Default | Why | Options, and when to use them | Team skills that cover it |
|---|---|---|---|---|
| Language | **TypeScript** | One language for web, API and mobile, so every agent can read every part. | Python only for data or AI scripts. Swift/Kotlin only for native mobile (see Mobile). | typescript-patterns, typescript-reviewer |
| Code home | **GitHub** monorepo, **pnpm** packages, **Turborepo** when web and mobile share code | Reviews, CI and security scans all live in one place. | None needed. | git-workflow-and-versioning |
| Hosting and edge | **Cloudflare Workers** (Next.js runs there through **vinext**, Cloudflare's current default for new Next.js projects; OpenNext is the fallback), Cloudflare DNS and CDN | Fast worldwide, generous free tier, and security comes built in. | **Vercel** if a Next.js feature doesn't work on Workers. **Docker on Fly.io or Render** for servers that must run for a long time (big jobs, websockets at scale). | deployment-patterns, docker-patterns. New: cloudflare, nextjs-on-cloudflare, workers-best-practices, wrangler, cloudflare-app-bootstrap, workers-development, workers-profiling (cloudflare/skills) |
| Security perimeter | **Cloudflare WAF, rate limiting, Turnstile** (bot check on forms), SSL | Blocks attacks and bots before they reach the app. | Cloudflare Zero Trust (Access) to lock admin pages to your team only. | security-and-hardening, sharp-edges. New: turnstile-spin, cloudflare-one (cloudflare/skills) |
| Secrets | **Cloudflare secrets** for the app, **GitHub encrypted secrets** for CI. Never in code. | Keys stay out of the repo and out of the AI's view. | 1Password or Doppler once several people share keys. | security-review, vibe-security |

## Building blocks

| Layer | Default | Why | Options, and when to use them | Team skills that cover it |
|---|---|---|---|---|
| Web front end | **Next.js + React**, **Tailwind + shadcn/ui** (components from 21st.dev), **Motion** for animation | It's the best-covered area of the team: React, Next.js, design and animation skills all fit. | **Astro** for a marketing or content-only website. **Vite + React** for a simple internal dashboard with no SEO. | nextjs-turbopack, react-patterns, react-performance, frontend-ui-engineering, ui-ux-pro-max, motion, 21st.dev, seo, accessibility-engineering |
| Back end and API | **Next.js route handlers and server actions**, with an **OpenAPI contract written first** | One codebase for the website and its API. The contract keeps web and mobile in sync. | **Hono on Cloudflare Workers** as a separate API when several apps or outside customers use it. **Node in Docker** for long-running workers. | backend-patterns, contract-first, api-and-interface-design, error-handling. New: hono (honojs/skills) |
| Database | **PostgreSQL on Neon**, connected through **Cloudflare Hyperdrive**, using **Prisma** | Real Postgres that scales to zero and makes a copy of the database per branch for safe testing. | **Supabase** when you want database, login and file storage in one product. **Cloudflare D1** for tiny tools with simple data. | postgres-patterns, prisma-patterns, database-reviewer. New: neon-postgres (neondatabase/agent-skills), prisma-orm-setup, prisma-client-api (prisma/skills) |
| Login (auth) | **Better Auth**, stored in our own Postgres | Open source, no per-user fees, user data stays in our database. | **Clerk** when a B2B SaaS needs team accounts and company SSO fast. **Supabase Auth** if the project is on Supabase. **Neon Auth** (Better Auth hosted by Neon) if you'd rather not run it yourself. | security-and-hardening, security-review. New: create-auth, best-practices, emailAndPassword, organization, twoFactor, security (better-auth/skills) |
| File storage | **Cloudflare R2** | Cheap, and no fees when users download files. | Supabase Storage on Supabase projects. AWS S3 only if a client requires AWS. | security-and-hardening |
| Background jobs | **Cloudflare Queues + Cron Triggers** | Same platform, nothing extra to run. | **Inngest or Trigger.dev** for long, multi-step jobs that need retries and a dashboard. | Cloudflare's general skills cover Queues lightly. Option: inngest-setup, inngest-durable-functions (inngest/inngest-skills). **Small gap:** no dedicated Queues skill |
| Payments | **Stripe** (subscriptions, checkout, customer portal) | The team has a Stripe billing skill and it's the standard for SaaS. | **Paddle or Lemon Squeezy** when you want them to handle worldwide sales tax for you. **RevenueCat** for in-app purchases, which Apple and Google require for digital goods in mobile apps. | customer-billing-ops, security-review (payments). New: stripe-implementation-planner, stripe-best-practices (stripe/ai, plain skills only) |
| Email | **Resend + React Email** | Simple API, email templates written in React like the rest of the app. | **Postmark** when delivery rates are critical (password resets at volume). **Cloudflare Email Routing** for receiving email. | New: resend, react-email, email-best-practices (resend/resend-skills) |
| AI features | **Claude API** (Anthropic SDK) through **Cloudflare AI Gateway** | One gateway logs, caches and rate-limits every AI call. | Cloudflare Workers AI for cheap small tasks such as tagging or embeddings. | context-engineering. New: agents-sdk (cloudflare/skills) |

## Apps beyond the web

| Layer | Default | Why | Options, and when to use them | Team skills that cover it |
|---|---|---|---|---|
| Mobile | **Expo (React Native)** with **EAS Build** to publish to the app stores | Same TypeScript and React as the web, so code and agents are shared. | **Flutter** for a very custom, animation-heavy UI. **SwiftUI / Kotlin** when the app leans heavily on phone hardware (camera, Bluetooth, widgets). | react-native-patterns. New: expo-overview, expo-router, expo-native-ui, expo-data-fetching, eas-app-stores, eas-update, eas-workflows (expo/skills). Options: dart-flutter-patterns, swiftui-patterns, android-clean-architecture |
| Desktop | **Installable web app (PWA)** first | No second codebase. Most tools don't need more. | **Tauri** for a real desktop app (small and locked down by default). **Electron** only if a needed library requires it. | **Skill gap:** no official Tauri or Electron skill exists yet. Fine for now, since desktop starts as a web app |

## Quality, shipping and watching

| Layer | Default | Why | Options, and when to use them | Team skills that cover it |
|---|---|---|---|---|
| Testing | **Vitest** (unit), **Playwright** (end-to-end, web), tests written first | Fast, TypeScript-native, and the team has Playwright skills and a test runner agent. | **Maestro** for mobile end-to-end tests. | test-driven-development, e2e-testing, e2e-runner, test-engineer, browser-testing-with-devtools |
| CI/CD | **GitHub Actions**: test, scan, then deploy with Cloudflare's `wrangler`. Every pull request gets a preview link. | Nothing ships without passing tests and security scans. | **EAS Workflows** for mobile builds. | ci-cd-and-automation, shipping-and-launch |
| Security in CI | **Semgrep + CodeQL + Dependabot** on every pull request, plus **claude-code-security-review** | Catches code holes, data-flow bugs and risky packages before merge. | SkillSpector before adding any new agent skill. | semgrep, codeql, supply-chain-risk-auditor, differential-review, security-auditor (candidates for approval) |
| Monitoring | **Sentry** (errors), **Cloudflare Workers Logs + Web Analytics** | See crashes and slow pages for web, API and mobile in one place. | **PostHog** for product analytics and feature flags. **Grafana / OpenTelemetry** once traffic is large. | observability-and-instrumentation, performance-optimization, web-performance-auditor. New: web-perf (cloudflare/skills) |

## What this means for the shortlist

- This answers open question 2 in the install shortlist: the ECC **Web** and **Back end / SaaS** skills plus **react-native-patterns** become core. Flutter, SwiftUI and Android skills stay optional.
- **Skill gaps:** filled on 2026-11-26 with official skills from each vendor (below). Still open: a dedicated Cloudflare Queues skill, and desktop (Tauri/Electron), which has no official skill.

## Official skills that fill the gaps (candidates, not installed)

All are from the company that makes the tool. I read each repo without running anything. Rule for all of them: copy the plain skill folders only; don't install the plugin or its MCP server without your OK.

| Repo | Stars | License | Skills we'd use | Safety notes |
|---|---|---|---|---|
| [cloudflare/skills](https://github.com/cloudflare/skills) | 3.5k | Apache-2.0 | 13 of 24 (Workers, Next.js, Wrangler, Turnstile, Zero Trust, web-perf, agents) | Plugin adds Cloudflare's hosted MCP server (needs your Cloudflare login). turnstile-spin runs 4 local shell scripts that use a Cloudflare token; they strip other secrets first. nextjs-on-cloudflare tells the agent to install more skills (`npx skills add cloudflare/vinext`); our agents must ask first. |
| [expo/skills](https://github.com/expo/skills) | 4.2k | MIT | 7 of 26 | Plugin adds Expo's hosted MCP server. 2 small helper scripts (one fetches Expo docs). No hooks. |
| [stripe/ai](https://github.com/stripe/ai) | 2.1k | MIT | 2 plain skills | **Skip the Claude plugin:** its hooks run on session start, every prompt and every tool use, and sometimes ask the agent to send Stripe feedback. Plain skills are fine. |
| [better-auth/skills](https://github.com/better-auth/skills) | 231 | none listed | all 6 | Plain text skills, no scripts or hooks. No license file, so it's fine to use but not to redistribute. |
| [resend/resend-skills](https://github.com/resend/resend-skills) | 220 | MIT | 3 of 5 | Plugin adds Resend's hosted MCP server. One small reference script. |
| [neondatabase/agent-skills](https://github.com/neondatabase/agent-skills) | 120 | Apache-2.0 | 1 (neon-postgres) | Plugin adds Neon's hosted MCP server. Scripts are only for the repo's own checks. |
| [prisma/skills](https://github.com/prisma/skills) | 80 | MIT | 2 of 11 | Plain text, no scripts. Newer than ECC's prisma-patterns; prefer these. |
| [inngest/inngest-skills](https://github.com/inngest/inngest-skills) | 29 | Apache-2.0 | 2 (option only) | Its MCP setting points only at the local dev server on your machine. |
| [honojs/skills](https://github.com/honojs/skills) | 21 | MIT | 1 (hono) | Plain text. Tells the agent to read Hono's docs site with curl. |

Also seen: [triggerdotdev/skills](https://github.com/triggerdotdev/skills) (36 stars, no license) if you pick Trigger.dev over Inngest.

**Stack change from this research:** Cloudflare's own skill now says to use **vinext** instead of OpenNext for new Next.js apps on Workers, so the Hosting row was updated.
