<div align="center">

# Board

**A 14-seat AI advisory board for Claude.**
Pressure-test any business decision, force real disagreement, turn the verdict into owned actions, and grade the board's own past calls.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Agent Skill](https://img.shields.io/badge/Agent%20Skill-SKILL.md-orange)](skills/board/SKILL.md)
[![Claude Code plugin](https://img.shields.io/badge/Claude%20Code-plugin-8A2BE2)](#install)
[![Version](https://img.shields.io/badge/version-1.0.0-green)](CHANGELOG.md)

</div>

---

## Why

Asking one AI for advice gets you one confident answer. Real decisions need the CFO who worries about runway, the lawyer who asks whether it can be undone, and the customer voice who asks who ends up worse off, all disagreeing out loud before anyone commits.

**Board** gives Claude that structure:

- **Seats, not personas.** Each seat is a business function with its own principles, the question it always asks, and the seats it hands work to.
- **Disagreement is enforced.** Every seat commits to a position before reasoning. If everyone agrees, a seat is assigned to argue the other side, and the unanimity is flagged as a warning.
- **Blockers can't be ignored.** Finance, Risk, Ops and Customer can stop a decision until it is resolved with evidence or carried to you.
- **Claims are tagged.** Every claim is marked as a Fact, an Assumption or a Judgment.
- **It acts.** Decisions become actions with an owner, a deliverable and a date, and the board executes what it can with your connected tools.
- **It keeps score.** Every decision is logged with a prediction, then graded at check-in, so you learn which seats you should trust.

## The seats

| Core (every session) | Situational (seated only when relevant) |
|---|---|
| **Strategy**: what to do now, next, never | **Growth**: experiments, funnel, self-serve |
| **Product**: what it is, for whom, at what price | **People**: hiring, org design, capacity |
| **Revenue**: pipeline to cash | **Risk**: legal, regulatory, downside exposure |
| **Marketing**: positioning, go-to-market, demand | **AI**: approach, evaluations, build vs buy |
| **Finance**: cash, margins, unit economics | **Capital**: raising, debt, M&A |
| **Customer**: retention and customer evidence | **Partnerships**: channels and alliances |
| **Ops**: delivery capacity and expansion order | |
| **Technology**: what gets built, how, at what cost | |

Full briefs are in [`skills/board/references/seats.md`](skills/board/references/seats.md).

## How it works

```
Size → Frame → Seat → Commit → Independent takes → Cross-examine
     → Dissent → Blockers → Pre-mortem → Chair synthesis → Actions → Log
```

| Size | When | What happens |
|---|---|---|
| **Quick** | Easy to undo, below your stakes threshold | One lead seat, ten lines or fewer, plus who would disagree |
| **Session** | Hard to undo or touches several functions | Full protocol with 3 to 5 seats |
| **Full board** | Bet-the-company or a quarterly review | Every active seat, plus a pre-mortem |

When Claude can spawn subagents, each seat runs as its own agent in parallel, so no seat sees another's answer before committing.

## Install

### Claude Code (plugin)

```
/plugin marketplace add AlaaEssam24/board-skill
/plugin install board@board-skill
```

### Claude Code (manual)

Copy the skill folder into your personal skills directory:

```bash
git clone https://github.com/AlaaEssam24/board-skill.git
cp -r board-skill/skills/board ~/.claude/skills/board
```

To share it with a project team, use `.claude/skills/board` inside the repo instead.

### Claude.ai and the Claude desktop app

1. Download `board.zip` from the [latest release](https://github.com/AlaaEssam24/board-skill/releases/latest), or zip the `skills/board` folder yourself.
2. Go to **Settings → Capabilities → Skills** and upload the zip.

### Other agents that support Agent Skills

```bash
npx skills add AlaaEssam24/board-skill
```

## Usage

Just talk to it:

| You say | The board does |
|---|---|
| `Ask the board: should we raise prices 20% for new customers?` | Sizes the decision, then runs it |
| `Ask the Finance seat what hiring two engineers does to runway` | One seat answers, then names who should weigh in |
| `Full board: should we expand to Saudi Arabia next quarter?` | Every active seat plus a pre-mortem |
| `Board, do it` | Skips the debate and executes the action plan |
| `Board check-in` | Reports late actions, grades past calls, proposes the next three moves |

On first use the board builds a short **company profile** (what you sell, to whom, stage, your recurring strategic tension, your stakes threshold) and saves it, together with a **decision log**, to your connected document tool.

## Example output

> **Decision (Session):** Run a 90-day pilot sold from the home entity to the six leads already in that market. No local hire, no local entity yet.
>
> | Seat | Position | Confidence | Would change its mind if |
> |---|---|---|---|
> | Strategy (lead) | Go, as a capped pilot | Medium | Home-market growth is still limited by sales capacity |
> | Finance | Go only if capped at 8% of cash | Medium | Downside-case payback exceeds 18 months |
> | Risk (dissent) | No-go until cross-border terms are checked | High | Counsel confirms selling from the home entity is allowed |
>
> **Blocker (Risk):** no contract is signed until counsel confirms cross-border terms.
> **Tripwire:** fewer than two pilot deals by day 60 means stop and log why.
> **Prediction:** three paying customers by day 90, confidence medium.

See the full worked example at the end of [`SKILL.md`](skills/board/SKILL.md).

## Repository layout

```
board-skill/
├── .claude-plugin/
│   ├── plugin.json         # Claude Code plugin manifest
│   └── marketplace.json    # lets /plugin marketplace add find it
├── skills/
│   └── board/
│       ├── SKILL.md        # the skill: protocol, sizing, output, decision log
│       └── references/
│           └── seats.md    # full brief for all 14 seats
├── CHANGELOG.md
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

## Customize

- **Change a seat's principles.** Edit its brief in `seats.md`, or just tell the board in chat: "the Finance seat should prioritize growth over margin this year."
- **Add a seat.** Follow the brief format and give it an "Active when" condition and a natural opposition.
- **Set your stakes threshold.** Tell the board the amount of money or time above which a decision counts as big.

## Disclaimer

The board gives AI-generated analysis, not professional advice. For legal, tax and investment matters it flags where you need a licensed professional. You make the decisions.

## Contributing

Issues and pull requests are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

## Author

Built by **Alaa Essam**, AI Transformation Leader.
[GitHub](https://github.com/AlaaEssam24) · [LinkedIn](https://www.linkedin.com/in/alaa-essam-ai)

If the board helped you make a better call, consider giving the repo a ⭐.

## License

[MIT](LICENSE) © 2026 Alaa Essam
