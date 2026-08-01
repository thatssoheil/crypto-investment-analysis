# 🧠 Skills — AI Agent Skills

A collection of ready-made **"skills"** (expert instructions) that teach any AI agent to do professional work — **crypto investment analysis** and **AI fitness coaching**.

> **What's a "skill"?** It's a set of expert instructions an AI agent loads so it knows exactly *how* to help you. Instead of starting from scratch, the AI follows a proven, professional workflow. No writing prompts — it's all built in.

- **Works with any AI agent:** Hermes, Claude Code, Codex, Cursor, Goose, OpenCode, Zed, and more.
- **Agent-agnostic:** the same skill runs on every agent.
- **No terminal? No problem.** Plain copy-paste prompt versions (for ChatGPT, Claude, Gemini) are in the [prompts repository](https://github.com/thatssoheil/prompts).

---

## 📦 What's inside

| Skill | What it does |
|---|---|
| **crypto-investment-analysis** | A professional 4-layer cryptocurrency analysis — Macro, Fundamental, On-Chain, and Technical — for both trading and long-term holding. |
| **fitness-program** | A complete fitness coaching workflow — intake, body analysis from photos, custom workout program, weekly check-ins. Multilingual. |

---

## 🚀 How to install

### Option 1: For regular users (easiest — no terminal)

Skip installation entirely and use the **copy-paste prompt** versions here:
👉 [github.com/thatssoheil/prompts](https://github.com/thatssoheil/prompts)

Just copy the text and paste it into ChatGPT, Claude, or Gemini.

### Option 2: For developers (install as an agent skill)

Skills are agent-agnostic. Install the one you want for your agent:

```bash
# Hermes Agent
npx skills add thatssoheil/skills --skill crypto-investment-analysis --agent hermes-agent -g -y
npx skills add thatssoheil/skills --skill fitness-program --agent hermes-agent -g -y
```

Works the same for every agent — just change the `--agent` name:

```bash
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

### Install ONE skill for ALL agents at once

```bash
npx skills add thatssoheil/skills --skill crypto-investment-analysis --agent hermes-agent claude-code codex cursor goose opencode zed -g -y
npx skills add thatssoheil/skills --skill fitness-program --agent hermes-agent claude-code codex cursor goose opencode zed -g -y
```

**Options explained:**
- `-g` → installs globally (available to all your projects on this machine).
- `-y` → skips confirmation prompts.
- `--skill <name>` → which skill to install (or `*` for all).

### See a skill without installing

```bash
# Print the skill instructions to the screen
npx skills use thatssoheil/skills --skill fitness-program
```

---

## 🗂 Repository structure

```
skills/
├── skills/
│   ├── crypto-investment-analysis/
│   │   └── SKILL.md          # the skill (instructions + setup)
│   └── fitness-program/
│       └── SKILL.md          # the skill (instructions + setup)
├── skills.sh.json            # skills.sh grouping manifest
├── package.json
└── README.md
```

Follows the [skills.sh / Agent Skills](https://skills.sh) standard: one folder per skill under `skills/`, each containing a `SKILL.md`.

---

## 🌍 Languages

- [English](README.md)
- [فارسی (Farsi)](README.fa.md)

---

## 📄 License

MIT
