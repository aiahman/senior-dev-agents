# Senior Dev Agents: team hierarchy

Date: 2026-11-26. Draft for Aiah's review. Nothing is installed.
Lead names are random Filipino names (made up). Skills each agent uses are in [brackets]. A * means the skill is still a Candidate (not approved yet). Every agent also follows **caveman** (short answers, small safe changes) as the company standard.
Departments are in build order: understand and scope, design, build, test, secure, ship. Full details per skill: [team-skills-table.md](team-skills-table.md).

```
IT DEPARTMENT
│
├── PRODUCT & BUSINESS ANALYSIS DEPARTMENT
│   │
│   ├── Andrea Dela Cruz (Product Lead)  [bmad-agent-pm, bmad-facilitate, bmad-party-mode]
│   │   ├── Project Coordinator  [bmad]
│   │   ├── Product Owner  [bmad-agent-po, writing-plans*]
│   │   └── Acceptance Reviewer  [spec-to-code-compliance*]
│   │
│   └── Paolo Reyes (Business Analysis Lead)  [bmad-agent-analyst]
│       ├── Business Analyst  [bmad-advanced-elicitation, bmad-ingest]
│       └── Brainstorming Facilitator  [bmad-brainstorming, bmad-forge-idea, brainstorming*]
│
├── RESEARCH & DISCOVERY DEPARTMENT
│   │
│   └── Bea Villanueva (Research Lead)  [bmad-deep-recon]
│       ├── Codebase Analyst  [understand, understand-chat, understand-explain, understand-diff]
│       ├── Domain Analyst  [understand-domain, understand-onboard, understand-dashboard]
│       ├── Knowledge Manager  [understand-knowledge]
│       └── Reverse Engineer  [REA reverse-engineer-anything]
│
├── SOLUTION ARCHITECTURE DEPARTMENT
│   │
│   └── Miguel Bautista (Chief Architect)  [bmad-agent-architect, bmad-architecture]
│       ├── API & Interface Designer  [api-and-interface-design]
│       ├── Codebase Architect  [codebase-design, improve-codebase-architecture]
│       ├── Cloud Architect  [cloudflare*]
│       ├── Payments Architect  [stripe-implementation-planner*]
│       └── Threat Modeler  [threat-model*]
│
├── UX/UI DESIGN DEPARTMENT
│   │
│   ├── Camille Mendoza (UX Design Lead)  [bmad-agent-ux-designer]
│   │   ├── UX Designer  [bmad-ux]
│   │   └── Design Handoff Specialist  [understand-figma]
│   │
│   └── Joaquin Ramos (UI Design Lead)  [ui-ux-pro-max]
│       ├── UI Designer  [design-system, ui-styling]
│       ├── Brand Designer  [brand, banner-design, design (logos, icons), slides]
│       └── Motion Designer  [motion, motion-reviewer]
│
├── FRONT END DEPARTMENT
│   │
│   └── Patricia Aquino (Front End Lead)  [react-reviewer, typescript-reviewer]
│       ├── Front End Developer  [frontend-ui-engineering, react-patterns, typescript-patterns, nextjs-turbopack]
│       ├── Component Specialist  [21st.dev CLI]
│       ├── React Performance Specialist  [react-performance]
│       ├── Email Template Developer  [react-email*]
│       └── SEO Specialist  [seo]
│
├── BACK END DEPARTMENT
│   │
│   ├── Rafael Garcia (Back End Lead)  [backend-patterns, contract-first]
│   │   ├── API Developer  [hono*, error-handling, migration]
│   │   ├── Edge / Cloud Developer  [workers-best-practices*, durable-objects*]
│   │   ├── Jobs & Email Developer  [resend*, email-best-practices*, inngest-setup*, inngest-durable-functions*]
│   │   └── Payments Engineer  [customer-billing-ops, stripe-best-practices*]
│   │
│   └── Kristine Navarro (Data & Auth Lead)  [database-reviewer]
│       ├── Database Engineer  [postgres-patterns, neon-postgres*, prisma-orm-setup*, prisma-client-api*, prisma-patterns]
│       └── Auth Engineer  [create-auth*, better-auth best-practices*, emailAndPassword*, organization*]
│
├── FULL STACK DEPARTMENT
│   │
│   └── Carlo Mercado (Full Stack Lead)  [bmad-agent-dev, bmad-build]
│       ├── Full Stack Developer  [bmad-build-auto, lean-build, nextjs-on-cloudflare*, workers-development*]
│       ├── Prototype Engineer  [prototype]
│       ├── Maintenance Engineer  [surgical-patch, safe-refactor]
│       ├── Debugging Specialist  [investigate-first, build-error-resolver]
│       └── AI Engineer  [agents-sdk*]
│
├── MOBILE DEPARTMENT
│   │
│   └── Jasmine Castillo (Mobile Lead)  [expo-overview*, react-native-patterns]
│       ├── Mobile Developer  [expo-router*, expo-data-fetching*]
│       ├── Mobile UI Developer  [expo-native-ui*]
│       ├── Mobile Release Engineer  [eas-app-stores*, eas-update*]
│       ├── iOS Developer (when needed)  [swiftui-patterns]
│       ├── Android Developer (when needed)  [android-clean-architecture]
│       └── Flutter Developer (when needed)  [dart-flutter-patterns]
│
├── QA & TESTING DEPARTMENT
│   │
│   └── Mark Anthony Torres (QA Lead)  [test-driven-development, verify-and-stop]
│       ├── QA Engineer  [test-engineer, browser-testing-with-devtools, property-based-testing*]
│       ├── QA Automation Engineer  [e2e-testing, e2e-runner, bmad-qa-generate-e2e-tests]
│       ├── Accessibility Specialist  [accessibility-engineering, accessibility-auditor]
│       └── Performance Engineer  [performance-optimization, web-performance-auditor, web-perf*]
│
├── CYBERSECURITY DEPARTMENT
│   │
│   ├── Leandro Pascual (Application Security Lead)  [security-and-hardening]
│   │   ├── Application Security Engineer  [security-review, vibe-security*, turnstile-spin*]
│   │   ├── Security Architect  [sharp-edges*]
│   │   ├── Identity & Access Engineer  [twoFactor*, better-auth security*]
│   │   └── Network Security Engineer  [cloudflare-one*]
│   │
│   └── Angelica Domingo (Security Audit Lead)  [security-audit*, security-auditor]
│       ├── Security Auditor  [audit-context-building*, fp-check*, variant-analysis*, cvss-scoring*]
│       ├── Security Code Reviewer  [differential-review*]
│       ├── Security Scanner Engineer  [semgrep*, codeql*]
│       ├── Supply-Chain Security Engineer  [mcp-dependency-review, supply-chain-risk-auditor*, SkillSpector*]
│       ├── DevSecOps Engineer  [agentic-actions-auditor*, claude-code-security-review*]
│       └── Security Officer  [git-guardrails-claude-code]
│
├── DEVOPS & RELEASE DEPARTMENT
│   │
│   └── Jerome Salazar (DevOps Lead)  [ci-cd-and-automation, deployment-patterns]
│       ├── DevOps Engineer  [git-workflow-and-versioning, caveman-commit, docker-patterns]
│       ├── Cloudflare Deploy Engineer  [wrangler*, cloudflare-app-bootstrap*]
│       ├── Mobile Pipeline Engineer  [eas-workflows*]
│       ├── Site Reliability Engineer  [observability-and-instrumentation, workers-profiling*]
│       └── Release Manager  [shipping-and-launch]
│
└── ENGINEERING LEADERSHIP (SENIOR DEV) DEPARTMENT
    │
    └── Ramon Villareal (Head of Engineering / Senior Dev)  [bmad-code-review, code-reviewer]
        ├── Lead Reviewer  [caveman-review, bmad-review, bmad-walkthrough]
        ├── Tech Lead  [bmad-project-context, context-engineering]
        ├── Technical Writer  [documentation-and-adrs]
        └── Engineering Manager  [bmad-retrospective]
```

Count: 12 departments, 16 leads, 64 specialist agents.
