<div align="center">
  <img src="./assets/logo.svg" alt="research-brief logo" width="120">
  <h1>Research Brief</h1>
  <p><i>An agent skill for real-world research — from DIY and hobbies to science: multi-source, multilingual, verified and cited answers</i></p>

  <p>
    <a href="https://github.com/empty-complete/research-brief/commits/main">
      <img src="https://img.shields.io/github/commit-activity/m/empty-complete/research-brief" alt="GitHub commit activity">
    </a>
    <a href="https://github.com/empty-complete/research-brief/stargazers">
      <img src="https://img.shields.io/github/stars/empty-complete/research-brief" alt="GitHub stars">
    </a>
    <a href="https://github.com/empty-complete/research-brief/blob/main/LICENSE">
      <img src="https://img.shields.io/github/license/empty-complete/research-brief" alt="License">
    </a>
  </p>

  <p>
    <a href="https://code.claude.com/docs/en/skills"><img src="https://img.shields.io/badge/Claude-Agent_Skill-D97757" alt="Claude Agent Skill"></a>
    <a href="https://developers.openai.com/codex"><img src="https://img.shields.io/badge/Codex-compatible-000000" alt="Codex compatible"></a>
    <a href="./SKILL.md"><img src="https://img.shields.io/badge/SKILL.md-portable-3178C6" alt="Portable SKILL.md"></a>
  </p>

  <p>
    <a href="https://t.me/neffortit">
      <img src="https://img.shields.io/badge/Telegram-follow-229ED9?logo=telegram" alt="Telegram">
    </a>
  </p>

  <p><a href="README.ru.md">Русская версия</a></p>
</div>

---

## Features

| Feature | Description |
| --- | --- |
| **Everyday questions are first-class** | Crafts, DIY, hobbies and purchases get the same rigor as science — without forcing academic framing on them |
| **Explains "down to atoms"** | When a source recommends a method, tool or material, the skill researches *that* too: what it is, why it fits, prerequisites, steps, how to check the result |
| **Depth tiers** | Quick / Standard / Deep / Exhaustive with rough tool-call budgets, so simple questions stay fast |
| **Broad, multilingual search** | Web, Reddit, YouTube, Telegram, TikTok, Instagram, Facebook, forums, scholarly databases, archives — in the languages the topic actually lives in |
| **Evidence registry** | Every source labelled by type, access level, date, evidence family and conflicts of interest; only registered sources may be cited, URLs only from pages actually opened |
| **SIFT / lateral reading** | Unfamiliar sources are checked from the outside; freshness checks for fast-moving facts; no single source may carry the whole answer |
| **Critique loop** | The draft is reviewed as a skeptic, a beginner doing it tomorrow, a domain expert and a reader from another region; gaps become follow-up searches |
| **Per-claim confidence** | High / medium / low with reasons, the strongest counter-argument in disputed sections, no sycophantic flip-flopping |
| **Comparison matrix** | Options × criteria tables with unknowns marked as unknown and the deciding criterion named |
| **Honest coverage notes** | What was searched, what was blocked, what wasn't tried — and whether more searching would change the answer |

### Requirements

| Capability | Status | Used for |
| --- | --- | --- |
| Web search | **required** | Discovery |
| Web page fetch | recommended | Reading original pages, `t.me/s` Telegram previews |
| Clock / current date | recommended | Freshness, correct years in queries |
| Browser automation | optional | Native search on social networks, Telegram Web, institutional access |
| Image search | optional | Visual references for DIY / creative tasks |
| Code execution | optional | Calculations, testing snippets, saving notes and registry files |
| Subagents | optional | Parallel research for Deep / Exhaustive tiers |

Missing capabilities don't break the skill: it uses what exists and reports gaps in the coverage note.

---

## Quick Start

### Installation

**Claude Code**

```bash
# personal — all projects
git clone https://github.com/empty-complete/research-brief.git ~/.claude/skills/research-brief

# or project-only — share with your team via git
git clone https://github.com/empty-complete/research-brief.git .claude/skills/research-brief
```

**Claude apps (claude.ai, desktop, mobile)**

```bash
git clone https://github.com/empty-complete/research-brief.git
zip -r research-brief.zip research-brief -x "research-brief/.git/*"
```

Then open **Customize → Skills → + → Create skill → Upload a skill** and choose the zip. The archive must contain the `research-brief/` folder with `SKILL.md` directly inside. Code execution must be enabled — see [Use skills in Claude](https://support.claude.com/en/articles/12512180-use-skills-in-claude).

**OpenAI Codex CLI**

```bash
git clone https://github.com/empty-complete/research-brief.git ~/.codex/skills/research-brief
```

**Other agents** (Cursor, Gemini CLI, OpenClaw, custom) — any agent that supports `SKILL.md` uses the folder as-is. Otherwise add to your system prompt or `AGENTS.md`:

> For research questions, follow `research-brief/SKILL.md` and read the reference files it points to when they apply.

### 1. Fill in your profile (optional)

Open [`references/user-profile.md`](references/user-profile.md) and set what you need — everything else falls back to defaults:

```text
Output language: English
Extra search languages: German, Russian
Mandatory channels: Reddit, YouTube, Telegram
Signed-in services: YouTube and Telegram Web in the agent's browser (read-only)
NotebookLM: Pro plan — may create research notebooks and add sources
Institutional access: university network — ScienceDirect, Springer
Country for prices/availability: Germany
```

Never put passwords, API keys, cookies or tokens in the profile.

### 2. Ask a question

```text
/research-brief how do I make a candle that looks like a cinnamon roll? I'm a beginner
```

Or just ask — the agent picks the skill up from its description.

### 3. Done!

You get a short brief with links and confidence levels, then a guide, comparison table or detailed report depending on the question.

---

## Usage

### Example requests

- *"Find out how to make a candle that looks like a cinnamon roll — I'm a beginner."*
- *"Compare the three most popular budget 3D printers for a beginner in Germany."*
- *"What does current research say about intermittent fasting and muscle loss? Deep."*
- *"Which MATLAB solver fits my problem: continuous variables, nonlinear constraints, no gradients?"*
- *"What do Telegram communities say about <product> after the latest update?"*

### Modes

| Mode | Triggered by | Main deliverable |
| --- | --- | --- |
| Everyday & creative | Crafts, DIY, household, hobbies, aesthetics | Step-by-step guide with materials, checkpoints, troubleshooting |
| Technical project | Software and engineering implementation | Versioned recommendation, minimal example, pitfalls, alternatives |
| Scientific | Questions that need academic literature | Evidence table, synthesis by subquestion, limitations, bibliography |
| Comparison / decision | Choosing between options | Options × criteria matrix and a reasoned pick |

### Depth tiers

| Tier | When | Rough budget |
| --- | --- | --- |
| Quick | One fact, obvious how-to | 2–6 tool calls |
| Standard | Default | 8–20 tool calls |
| Deep | High stakes, contested topics, literature | 20–50 tool calls + critique loop |
| Exhaustive | "Cover everything" | Deep + more languages, platforms, saturation rounds |

### Browser & sign-ins

If your agent can drive your own browser (Claude in Chrome, a built-in browser pane, Playwright with your profile), list the services you're signed in to in the profile. The skill uses them **read-only** — it never posts, messages, reacts, joins groups or channels, buys, or changes settings.

### NotebookLM (optional)

If you enable NotebookLM in the profile, the skill uses it for bulk reading: it creates a notebook per research task, adds the YouTube videos, pages and PDFs it found, asks narrow questions across all of them, and then checks every load-bearing claim in the original source. NotebookLM's answers are treated as leads, not evidence; the report cites the videos and pages themselves. The notebook stays in your account so you can keep asking questions. The skill never deletes or shares notebooks and does not touch your other notebooks.

### Telegram

Works without any setup: public channels via `https://t.me/s/<channel>` (with `?q=` search inside a channel) and discovery through [TGStat](https://tgstat.ru/). A signed-in Telegram Web session adds global search and comments.

A Telethon-based Telegram MCP server is optional. Such servers usually get full account access (including sending and deleting), need API credentials from my.telegram.org, and automated use of a personal account can trigger Telegram's limits — the skill only ever calls their search/read tools.

---

## Project Structure

```
research-brief/
├── SKILL.md                         # entry point: workflow, tools, deliverables
├── agents/openai.yaml               # optional UI metadata for OpenAI Codex
├── assets/logo.svg
└── references/
    ├── user-profile.md              # YOUR settings: language, channels, sign-ins, access
    ├── depth-and-orchestration.md   # date anchor, tiers, planning, queries, subagents, stopping
    ├── quality-and-verification.md  # SIFT, source labels, registry, confidence, critique loop
    ├── social-and-media.md          # Reddit, YouTube, TikTok, Instagram, Facebook, forums, images
    ├── telegram.md                  # t.me/s previews, TGStat, Telegram Web, MCP
    ├── notebooklm.md                # optional bulk reading of videos/sources in NotebookLM
    ├── everyday-and-creative.md     # crafts, DIY, hobbies, how-to guides
    ├── method-breakdown.md          # recursive explanation of methods and dependencies
    ├── scientific.md                # literature search, appraisal, evidence tables
    └── access-and-sources.md        # paywalls, institutional access, source families
```

The repository root **is** the skill folder — keep it named `research-brief` to match `name:` in `SKILL.md`.

---

## Credits

Built on ideas from:

- Anthropic — [How we built our multi-agent research system](https://www.anthropic.com/engineering/multi-agent-research-system) — effort scaling, broad-then-narrow search, delegation briefs
- [199-biotechnologies/claude-deep-research-skill](https://github.com/199-biotechnologies/claude-deep-research-skill) — date anchor, modes, critique loop-back, persisted sources
- [daymade/claude-code-skills — deep-research](https://github.com/daymade/claude-code-skills/blob/main/deep-research/SKILL.md) — source-type labels, citation registry, concentration limits, confidence markers
- [Weizhena/Deep-Research-skills](https://github.com/Weizhena/Deep-Research-skills) — item × field comparison matrix
- [Imbad0202/academic-research-skills](https://github.com/imbad0202/academic-research-skills) — claim-faithfulness checks, anti-sycophancy
- The SIFT method by Mike Caulfield, as taught in university library guides

---

<div align="center">
  <h2>Contributing</h2>
  <p>Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.</p>
  <p>
    <sub>Made with ❤️ for everyone who asks "how do I…?"</sub>
  </p>
</div>

---
