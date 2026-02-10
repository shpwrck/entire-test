# Entire CLI

Git-integrated tool that captures AI agent sessions on every push, creating a searchable record of your development history.

## Install

```sh
# Homebrew
brew tap entireio/tap && brew install entireio/tap/entire

# Go
go install github.com/entireio/cli/cmd/entire@latest
```

## Quick Start

```sh
entire enable   # Set up in your repo
entire status   # View current session
entire rewind   # Restore a previous checkpoint
entire resume   # Access past sessions
entire disable  # Remove hooks (keeps history)
```

## How It Works

Entire tracks your AI agent interactions (Claude Code, Gemini CLI) — prompts, responses, modified files — and stores them on a separate `entire/checkpoints/v1` branch. Two capture strategies are available: **manual-commit** (checkpoint on commit) and **auto-commit** (checkpoint after each agent response).

## Configuration

Settings are stored in `.entire/settings.json` (shared) and `.entire/settings.local.json` (local overrides).

For more details, see the [full README](https://github.com/entireio/cli).
