# Senior Dev Agents

An AI dev team for Claude Code, organized like an IT company: 12 departments, 16 leads and 64 specialist agents that help understand a tool, scope it, design it, build it, test it, secure it and ship it.

This repository is a Claude Code plugin and its own private marketplace. Install it once and every skill and agent is available in Claude Code on that computer.

## What's inside

| Path | What it is |
|---|---|
| `skills/` | 137 skills: 136 copied as plain files from their official repositories, plus `senior-dev-team` (the team rules) |
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

Some skills ship scripts that only run when an agent uses that skill, and Claude Code asks before running them (codeql, semgrep, supply-chain-risk-auditor, turnstile-spin, ui-ux-pro-max, design, eas-workflows, the bmad-* skills, git-guardrails-claude-code). The codeql and semgrep skills need those scanners installed.

- **BMAD** skills need a one-time setup per project: ask for the `bmad` skill and it creates a `_bmad/` folder. Its scripts run with `uv`, and setup checks GitHub for BMAD updates.
- **git-guardrails-claude-code** is only instructions until you use it; using it adds a hook to that project's `.claude/settings.json`.
- **reverse-engineer-anything** is only instructions. Its full tool set needs the REA MCP server (`npx rea-agents setup`), which it asks for when needed.

## Not included (they can't live in this repo as skill files)

Each of these is a tool, plugin or service, not a skill folder. Install them yourself on the computer or in the project that needs them:

1. **Understand-Anything** (understand-* skills): a Claude Code plugin with its own hooks and built code, so the skill files don't work on their own. Install it as a plugin from [Egonex-AI/Understand-Anything](https://github.com/Egonex-AI/Understand-Anything) and turn auto-update off.
2. **Motion AI Kit** (motion, motion-reviewer): `npx motion-ai`, which adds 2 hosted Motion MCP servers.
3. **21st.dev CLI**: `npm i -g @21st-dev/cli`, then `21st login` (the owner does this personally), then its MCP config.
4. **SkillSpector**: a scanner for checking new skills before you add them (Docker or pip), from [NVIDIA/SkillSpector](https://github.com/NVIDIA/SkillSpector).
5. **claude-code-security-review**: a GitHub Action added to each app repository. It needs an API key secret.
6. **Better Auth skills** (create-auth, organization, two-factor, security...): [better-auth/skills](https://github.com/better-auth/skills) has no license file, so they aren't copied here. Install them from the source in the app project that uses Better Auth.

Deliberately left out: graphify, Agent-Reach, last30days, gstack, GSD, headroom, claude-mem, and Stripe's Claude plugin (its hooks).
