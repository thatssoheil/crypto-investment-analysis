# skills

A skills.sh-compatible collection of [Agent Skills](https://skills.sh) by [thatssoheil](https://github.com/thatssoheil). Each skill is a self-contained `SKILL.md` that works with ANY AI agent — Hermes, Claude Code, Codex, Cursor, Goose, OpenCode, Zed, and more.

All skills are agent-agnostic: they work as agent skills, or can be copy-pasted as system prompts into any AI chat.

**No terminal? No problem.** Copy-paste prompt versions for non-technical users are available at [thatssoheil/prompts](https://github.com/thatssoheil/prompts).

## Skills in this collection

| Skill | Description |
|---|---|
| [crypto-investment-analysis](skills/crypto-investment-analysis/SKILL.md) | A professional 4-layer cryptocurrency analysis workflow — Macro, Fundamental, On-Chain, and Technical — for trading and long-term holding. |
| [fitness-program](skills/fitness-program/SKILL.md) | A structured, conversational fitness coaching workflow — intake, vision-based body analysis, program generation, weekly check-ins. Multilingual. |

## Install

Skills are agent-agnostic. Install the one you want for your agent:

### crypto-investment-analysis

```bash
# Hermes Agent
npx skills add thatssoheil/skills --skill crypto-investment-analysis --agent hermes-agent -g -y

# Claude Code
npx skills add thatssoheil/skills --skill crypto-investment-analysis --agent claude-code -g -y

# OpenAI Codex
npx skills add thatssoheil/skills --skill crypto-investment-analysis --agent codex -g -y

# Cursor
npx skills add thatssoheil/skills --skill crypto-investment-analysis --agent cursor -g -y

# Goose
npx skills add thatssoheil/skills --skill crypto-investment-analysis --agent goose -g -y

# OpenCode
npx skills add thatssoheil/skills --skill crypto-investment-analysis --agent opencode -g -y

# Zed
npx skills add thatssoheil/skills --skill crypto-investment-analysis --agent zed -g -y
```

### fitness-program

```bash
# Hermes Agent
npx skills add thatssoheil/skills --skill fitness-program --agent hermes-agent -g -y

# Claude Code
npx skills add thatssoheil/skills --skill fitness-program --agent claude-code -g -y

# OpenAI Codex
npx skills add thatssoheil/skills --skill fitness-program --agent codex -g -y

# Cursor
npx skills add thatssoheil/skills --skill fitness-program --agent cursor -g -y

# Goose
npx skills add thatssoheil/skills --skill fitness-program --agent goose -g -y

# OpenCode
npx skills add thatssoheil/skills --skill fitness-program --agent opencode -g -y

# Zed
npx skills add thatssoheil/skills --skill fitness-program --agent zed -g -y
```

### Install a skill for ALL agents at once

```bash
npx skills add thatssoheil/skills --skill crypto-investment-analysis --agent hermes-agent claude-code codex cursor goose opencode zed -g -y
npx skills add thatssoheil/skills --skill fitness-program --agent hermes-agent claude-code codex cursor goose opencode zed -g -y
```

Notes:
- `-g` installs to the user (global) skills directory; drop it for project-scoped install.
- `-y` skips confirmation prompts (useful in CI/CD).
- See [skills.sh](https://skills.sh) for the full list of supported agents.

## Use without installing

```bash
# Print the skill prompt to stdout
npx skills use thatssoheil/skills --skill crypto-investment-analysis
npx skills use thatssoheil/skills --skill fitness-program

# Start a supported agent interactively with the generated prompt
npx skills use thatssoheil/skills --skill fitness-program --agent claude-code
```

## Repository structure

```
skills/
├── skills/
│   ├── crypto-investment-analysis/
│   │   └── SKILL.md          # the skill (frontmatter + instructions)
│   └── fitness-program/
│       └── SKILL.md          # the skill (frontmatter + instructions)
├── skills.sh.json            # skills.sh grouping manifest
├── package.json
└── README.md
```

This follows the [skills.sh](https://skills.sh) / Agent Skills format: one folder per skill under `skills/`, each containing a `SKILL.md` with `name` and `description` in the YAML frontmatter.

## License

MIT
