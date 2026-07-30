# crypto-investment-analysis

A skills.sh-compatible [Agent Skill](https://skills.sh) for AI coding agents. A professional, institutional-grade 4-layer cryptocurrency analysis workflow — Macro & Market Sentiment, Fundamental Analysis, On-Chain Data, and Technical Analysis — for both short-term trading and long-term holding.

Agent-agnostic: works as a Hermes skill or as a system prompt pasted into any AI chat.

**No terminal? No problem.** A copy-paste prompt version for non-technical users is available at [thatssoheil/prompts](https://github.com/thatssoheil/prompts).

## Install

The skill is agent-agnostic. Install for your agent:

```bash
# Hermes Agent
npx skills add thatssoheil/crypto-investment-analysis --skill crypto-investment-analysis --agent hermes-agent -g -y

# Claude Code
npx skills add thatssoheil/crypto-investment-analysis --skill crypto-investment-analysis --agent claude-code -g -y

# OpenAI Codex
npx skills add thatssoheil/crypto-investment-analysis --skill crypto-investment-analysis --agent codex -g -y

# Cursor
npx skills add thatssoheil/crypto-investment-analysis --skill crypto-investment-analysis --agent cursor -g -y

# Goose
npx skills add thatssoheil/crypto-investment-analysis --skill crypto-investment-analysis --agent goose -g -y

# OpenCode
npx skills add thatssoheil/crypto-investment-analysis --skill crypto-investment-analysis --agent opencode -g -y

# Zed
npx skills add thatssoheil/crypto-investment-analysis --skill crypto-investment-analysis --agent zed -g -y
```

### Install for ALL agents at once

```bash
npx skills add thatssoheil/crypto-investment-analysis --skill crypto-investment-analysis --agent hermes-agent claude-code codex cursor goose opencode zed -g -y
```

Notes:
- `-g` installs to the user (global) skills directory; drop it for project-scoped install.
- `-y` skips confirmation prompts (useful in CI/CD).
- See [skills.sh](https://skills.sh) for the full list of supported agents.

## Use without installing

```bash
# Print the skill prompt to stdout
npx skills use thatssoheil/crypto-investment-analysis --skill crypto-investment-analysis

# Start a supported agent interactively with the generated prompt
npx skills use thatssoheil/crypto-investment-analysis --skill crypto-investment-analysis --agent claude-code
```

## What it does

A 4-layer analysis framework for any cryptocurrency:

1. **Macro & Market Sentiment (The Wind)** — BTC dominance, Fear & Greed index, stablecoin liquidity.
2. **Fundamental Analysis (The Engine)** — tokenomics, utility, developer activity, social dominance.
3. **On-Chain Data (The Truth)** — network health, transaction activity, exchange flows, MVRV ratio.
4. **Technical Analysis (The Entry)** — price structure, relative strength vs BTC, key levels, volume profile.

Plus three ahead scenarios (bullish / neutral / bearish) and a structured output format with executive summary, verdict, and a DCA/exit plan.

## Repository structure

```
crypto-investment-analysis/
├── skills/
│   └── crypto-investment-analysis/
│       └── SKILL.md          # the skill (frontmatter + instructions)
├── skills.sh.json            # optional skills.sh grouping manifest
├── package.json
└── README.md
```

This follows the [skills.sh](https://skills.sh) / Agent Skills format: one folder per skill under `skills/`, each containing a `SKILL.md` with `name` and `description` in the YAML frontmatter.

## License

MIT
