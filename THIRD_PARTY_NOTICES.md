# Third-party notices

Every skill and agent under `skills/` and `agents/` was copied unchanged from the repositories below (except where noted). Each source keeps its own license; full license texts are in [`licenses/`](licenses/). Copyright stays with the original authors.

| Source | Commit | License | Skills and agents copied |
|---|---|---|---|
| [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) | `e997ac5` | MIT | accessibility-auditor (agent), accessibility-engineering, api-and-interface-design, browser-testing-with-devtools, ci-cd-and-automation, code-reviewer (agent), context-engineering, documentation-and-adrs, frontend-ui-engineering, git-workflow-and-versioning, observability-and-instrumentation, performance-optimization, security-and-hardening, security-auditor (agent), shipping-and-launch, test-driven-development, test-engineer (agent), web-performance-auditor (agent) |
| [trailofbits/skills](https://github.com/trailofbits/skills) | `149d7b2` | CC-BY-SA-4.0 | agentic-actions-auditor, audit-context-building, codeql, cvss-scoring, differential-review, fp-check, property-based-testing, semgrep, sharp-edges, spec-to-code-compliance, supply-chain-risk-auditor, variant-analysis |
| [cloudflare/skills](https://github.com/cloudflare/skills) | `ff191de` | Apache-2.0 | agents-sdk, cloudflare, cloudflare-app-bootstrap, cloudflare-one, durable-objects, nextjs-on-cloudflare, turnstile-spin, web-perf, workers-best-practices, workers-development, workers-profiling, wrangler |
| [affaan-m/ECC](https://github.com/affaan-m/ECC) | `4adeee6` | MIT | android-clean-architecture, backend-patterns, build-error-resolver (agent), contract-first, customer-billing-ops, dart-flutter-patterns, database-reviewer (agent), deployment-patterns, docker-patterns, e2e-runner (agent), e2e-testing, error-handling, mcp-dependency-review, nextjs-turbopack, postgres-patterns, prisma-patterns, react-native-patterns, react-patterns, react-performance, react-reviewer (agent), security-review, seo, swiftui-patterns, typescript-patterns, typescript-reviewer (agent) |
| [nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) | `0170613` | MIT | banner-design, brand, design, design-system, slides, ui-styling, ui-ux-pro-max |
| [obra/superpowers](https://github.com/obra/superpowers) | `22f0b46` | MIT | brainstorming, writing-plans |
| [juliusbrussee/caveman](https://github.com/juliusbrussee/caveman) | `e74a11c` | Apache-2.0 | caveman, caveman-commit, caveman-review, investigate-first, lean-build, migration, safe-refactor, surgical-patch, verify-and-stop |
| [mattpocock/skills](https://github.com/mattpocock/skills) | `6f7f783` | MIT | codebase-design, improve-codebase-architecture, prototype |
| [expo/skills](https://github.com/expo/skills) | `6d0506a` | MIT | eas-app-stores, eas-update, eas-workflows, expo-data-fetching, expo-native-ui, expo-overview, expo-router |
| [resend/resend-skills](https://github.com/resend/resend-skills) | `063246e` | MIT | email-best-practices, react-email, resend |
| [honojs/skills](https://github.com/honojs/skills) | `e54ce51` | MIT | hono |
| [inngest/inngest-skills](https://github.com/inngest/inngest-skills) | `082798a` | Apache-2.0 | inngest-durable-functions, inngest-setup |
| [neondatabase/agent-skills](https://github.com/neondatabase/agent-skills) | `d3601d9` | Apache-2.0 | neon-postgres |
| [prisma/skills](https://github.com/prisma/skills) | `b4bebff` | MIT | prisma-client-api, prisma-orm-setup |
| [cloudflare/security-audit-skill](https://github.com/cloudflare/security-audit-skill) | `c1c8a8c` | MIT | security-audit |
| [stripe/ai](https://github.com/stripe/ai) | `d4b19a9` | MIT | stripe-best-practices, stripe-implementation-planner |
| [alpha-omega-security/threat-model](https://github.com/alpha-omega-security/threat-model) | `192fd60` | MIT | threat-model, threat-model-authoring, threat-model-backtest, threat-model-interview, threat-model-recon, threat-model-sidecar, threat-model-surface, threat-model-triage |
| [raroque/vibe-security-skill](https://github.com/raroque/vibe-security-skill) | `850938f` | MIT | vibe-security |

## Notes

- **Trail of Bits skills (CC-BY-SA-4.0):** share-alike. If you change these skill files and share them, the changed files must stay under CC-BY-SA-4.0 with credit to Trail of Bits.
- **Apache-2.0 sources** (cloudflare, caveman, inngest, neon): keep the license and any NOTICE text if you redistribute.
- **Better Auth skills are not included.** [better-auth/skills](https://github.com/better-auth/skills) has no license file, so copying it into another repository is not clearly allowed. Install it straight from the source instead (see README).
- Upstream test folders inside skills were removed; nothing else was changed, apart from these README/CLAUDE files.
