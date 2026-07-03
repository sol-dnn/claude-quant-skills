# Claude Quant Skills

Custom slash commands for Claude Code, built for a quant internship workflow.

## What is `~/.claude/commands/`?

It's a folder that Claude Code reads automatically at startup. Every `.md` file you put in it becomes a slash command you can call with `/filename`.

The folder does **not** exist by default — you have to create it once.

## Install on a new machine

### Option 1 — one curl command (if GitHub is accessible from the terminal)

```bash
mkdir -p ~/.claude/commands && \
curl -sL https://raw.githubusercontent.com/sol-dnn/claude-quant-skills/master/weekly-recap.md -o ~/.claude/commands/weekly-recap.md && \
curl -sL https://raw.githubusercontent.com/sol-dnn/claude-quant-skills/master/meeting-notes-action-plan.md -o ~/.claude/commands/meeting-notes-action-plan.md && \
curl -sL https://raw.githubusercontent.com/sol-dnn/claude-quant-skills/master/research-output-review.md -o ~/.claude/commands/research-output-review.md && \
curl -sL https://raw.githubusercontent.com/sol-dnn/claude-quant-skills/master/quant-research-checklist.md -o ~/.claude/commands/quant-research-checklist.md
```

### Option 2 — manual copy-paste (if curl is blocked)

1. Create the folder: `mkdir -p ~/.claude/commands`
2. For each file in this repo: open it, click **Raw**, copy the content
3. Create the file on your machine and paste: `nano ~/.claude/commands/weekly-recap.md`
4. Repeat for the 4 files

## Available commands

| Command | When to use |
|---|---|
| `/weekly-recap` | Friday — paste your rough week notes, get a clean email for your mentor or PM |
| `/meeting-notes-action-plan` | After a call — paste rough notes, get decisions + action items |
| `/research-output-review` | Before showing a notebook — get critical fixes + what your manager will ask |
| `/quant-research-checklist` | When a backtest looks too good — systematic leakage and robustness check |

## How to use

Type `/command-name` followed by your notes directly in Claude Code (terminal or VSCode extension):

```
/weekly-recap recipient: Marc (quant mentor). Cette semaine j'ai testé le signal momentum sur 6 mois, sharpe ~0.9 mais pas sûr du rebalancing daily vs weekly.
```

```
/quant-research-checklist Signal close-to-close momentum 20j sur US equities 2015-2024. Ridge regression. Sharpe 1.4 in-sample. Pas encore de transaction costs.
```

Everything after the command name is passed as your input (`$ARGUMENTS`).
