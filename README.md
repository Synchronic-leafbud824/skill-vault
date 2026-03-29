# Skill Vault

A personal skill library manager for Claude Code. Organize, analyze, and search through all the skills you find across the internet — with built-in security analysis.

## Quick Start

```bash
git clone https://github.com/YOUR_USERNAME/skill-vault.git
cd skill-vault
claude
```

That's it. Open the project with Claude Code and the Vault Master agent is ready. No dependencies, no setup, no build step.

## What It Does

**Skill Vault** solves three problems:

1. **Organize** — Save skills from GitHub, skills.sh, npm, or anywhere. Each skill is analyzed and filed into a category folder with full metadata.

2. **Analyze** — Every skill goes through a 13-point security checklist before being saved. The Vault Master flags dangerous patterns (malicious commands, data exfiltration, credential theft) and assigns a safety rating: SAFE, CAUTION, or DANGEROUS.

3. **Recommend** — Describe what you're building and the Vault Master searches your personal library to recommend the right skills for your project.

## Commands

| Command | What it does |
|---------|-------------|
| `/vault-add` | Add a skill from a GitHub URL, pasted content, skill name, or file path |
| `/vault-search` | Search your vault by keyword or description |
| `/vault-recommend` | Describe your project, get skill recommendations from your vault |
| `/vault-discover` | Search external sources (skills.sh, GitHub, skillsmp.com) for new skills |
| `/vault-list` | Display all saved skills grouped by category |
| `/vault-stats` | View vault statistics and run a consistency check |
| `/vault-remove` | Remove a skill from the vault |

## How Skills Are Stored

```
categories/
├── automation/
│   ├── _category.md          # What this category is for
│   ├── playwright-cli.md     # Skill entry with metadata + security analysis
│   └── browser-automation.md
├── design-ui/
│   ├── _category.md
│   └── shadcn-ui.md
└── ...
```

Each skill entry contains:
- **Metadata** — name, source URL, category, tags, version
- **Security analysis** — safety rating + detailed findings from the 13-point checklist
- **Install command** — how to add the skill to your Claude Code setup
- **Original content** — the full SKILL.md preserved for reference

The master index at `catalog.md` provides a searchable table of all skills.

## Security Analysis

Every skill is checked against a 13-point security rubric before being saved:

| Rating | Meaning |
|--------|---------|
| **SAFE** | No shell commands, no network calls, limited tool access |
| **CAUTION** | Uses Bash/network but commands are bounded and reasonable |
| **DANGEROUS** | Contains suspicious patterns — requires explicit confirmation to save |

Auto-dangerous triggers include: `rm -rf`, `curl \| bash`, credential file access, obfuscated code, data exfiltration patterns, overly broad permissions, and prompt injection attempts.

See `security-rubric.md` for the full analysis methodology.

## Default Categories

| Category | What belongs here |
|----------|-------------------|
| `automation` | Browser automation, workflow scripting, task runners |
| `code-quality` | Linting, refactoring, best practices, code review |
| `design-ui` | Frontend design, UI components, design systems |
| `devops-deploy` | Docker, CI/CD, deployment, infrastructure |
| `documentation` | READMEs, changelogs, API docs, technical writing |
| `organization` | Project management, workflow organization, planning |
| `productivity` | Text processing, meeting notes, content creation |
| `research` | Web research, data gathering, analysis |
| `testing` | Unit tests, E2E tests, test frameworks |
| `web-development` | React, Next.js, Vue, full-stack, APIs |

New categories are created automatically when a skill doesn't fit existing ones.

## Contributing

1. Fork this repo
2. Add skills using `/vault-add` or manually create entries in `categories/` following the template in `templates/skill-entry.md`
3. Submit a PR

## License

MIT
