# Senior Dev Agents

An AI dev team for Claude Code, organized like an IT company: 12 departments, 16 leads and 64 specialist agents that help understand a tool, scope it, design it, build it, test it, secure it and ship it.

This repository is the team's home. Open it in Claude Code (or copy its `.claude/` folder into a project) and every skill and agent below is available in that project.

## What's inside

| Path | What it is |
|---|---|
| `.claude/skills/` | 106 skills, copied as plain files from their official repositories |
| `.claude/agents/` | 10 reviewer and auditor agents |
| `CLAUDE.md` | Rules every agent follows: the team structure, the default stack, and safety rules |
| `docs/team-hierarchy.md` | The org chart as a text tree |
| `docs/org-chart.html` | The interactive org chart (open in a browser) |
| `docs/team-skills-table.md` / `.csv` | Every skill, with a one-line description, agent role and department |
| `docs/default-tech-stack.md` | The default tech stack, its options, and which skills cover each layer |
| `THIRD_PARTY_NOTICES.md`, `licenses/` | Where every skill came from, at which commit, under which license |

There are no hooks, plugins, MCP servers, settings files or telemetry in this repository.

## How to use it

- **Work inside this repo:** clone it and run `claude` in the folder.
- **Use the team in another project:** copy `.claude/skills/` and `.claude/agents/` into that project's `.claude/` folder. If a skill with the same name already exists there, keep one of them.

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
