# Senior Dev Agents

An AI dev team for Claude Code, organized like an IT company: 12 departments, 16 leads and 64 specialist agents that help understand a tool, scope it, design it, build it, test it, secure it and ship it.

This repository is a Claude Code plugin and its own private marketplace. Install it once and every skill and agent is available in Claude Code on that computer.

## What's inside

| Path | What it is |
|---|---|
| `skills/` | 107 skills: 106 copied as plain files from their official repositories, plus `senior-dev-team` (the team rules) |
| `agents/` | 10 reviewer and auditor agents |
| `.claude-plugin/` | Plugin and marketplace files that let Claude Code install this repo |
| `CLAUDE.md` | The team rules, for when you work inside this repo itself |
| `docs/team-hierarchy.md` | The org chart as a text tree |
| `docs/org-chart.html` | The interactive org chart (open in a browser) |
| `docs/team-skills-table.md` / `.csv` | Every skill, with a one-line description, agent role and department |
| `docs/default-tech-stack.md` | The default tech stack, its options, and which skills cover each layer |
| `THIRD_PARTY_NOTICES.md`, `licenses/` | Where every skill came from, at which commit, under which license |

There are no hooks, plugins, MCP servers, settings files or telemetry in this repository.

## How to use it

In Claude Code, run:

```
/plugin marketplace add aiahman/senior-dev-agents
/plugin install senior-dev-agents@senior-dev-agents
```

Then restart Claude Code. Skills show up as `senior-dev-agents:<skill>` (for example `senior-dev-agents:security-review`), and the agents appear in `/agents`.

Because the repository is private, the computer needs GitHub access: be signed in with `gh auth login`, or have git credentials that can clone `aiahman/senior-dev-agents`. For background auto-updates, also set a `GITHUB_TOKEN` environment variable. To pull new versions by hand, run `/plugin marketplace update senior-dev-agents`.

Some skills ship scripts that only run when an agent uses that skill, and Claude Code asks before running them (codeql, semgrep, supply-chain-risk-auditor, turnstile-spin, ui-ux-pro-max, design, eas-workflows). The codeql and semgrep skills need those scanners installed.

## Not included yet (each needs its own OK)

These change settings, add plugins or MCP servers, run installers, or need a sign-in, so they are added one at a time, per project:

1. **BMAD Method** (analyst, PM, PO, architect, UX, dev, review personas): `npx bmad-method install` inside the project.
2. **Understand-Anything** (understand-* skills): Claude Code plugin. Leave auto-update off.
3. **git-guardrails-claude-code**: a hook in `.claude/settings.json` that blocks force-push and `reset --hard`.
4. **Motion AI Kit** (motion, motion-reviewer): `npx motion-ai`, adds 2 hosted Motion MCP servers.
5. **21st.dev CLI**: `npm i -g @21st-dev/cli`, then `21st login` (done by the owner personally), then its MCP config.
6. **REA** (reverse-engineer-anything): `npx rea-agents setup`, adds an MCP server.
7. **SkillSpector**: scanner to check new skills before adding them (Docker or pip).
8. **claude-code-security-review**: GitHub Action for each app repository, needs an API key secret.
9. **Better Auth skills** (create-auth, organization, two-factor, security...): [better-auth/skills](https://github.com/better-auth/skills) has no license file, so it isn't copied here. Install it from the source in the app project that uses Better Auth.

Deliberately left out: graphify, Agent-Reach, last30days, gstack, GSD, headroom, claude-mem, and Stripe's Claude plugin (its hooks).
