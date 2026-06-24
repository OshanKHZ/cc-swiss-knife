---
name: hermes-tweet
description: This skill should be used when a Claude Code session needs "Hermes Tweet", "Hermes Agent X/Twitter", "X/Twitter search", "tweet reading", or approval-gated social action workflows through the Hermes Tweet plugin.
---

# Hermes Tweet

Use Hermes Tweet when the task needs a Hermes Agent native route for X/Twitter research, timeline reading, social signal triage, or controlled posting workflows.

## Source

- Repository: https://github.com/Xquik-dev/hermes-tweet
- Agent runtime: https://github.com/NousResearch/hermes-agent

## Workflow

1. Read the current Hermes Tweet README before installing or changing configuration.
2. Install the native Hermes Agent plugin from the canonical repository.
3. Configure `XQUIK_API_KEY` only in the local runtime environment.
4. Keep read workflows separate from action workflows.
5. Require explicit user approval before any post, reply, repost, like, follow, or delete action.

## Safety Rules

- Prefer search and read tools for research, monitoring, and evidence gathering.
- Do not expose API keys, cookies, session material, or private account details.
- Do not bypass the Hermes Tweet action gate for write operations.
- Do not use unrelated X/Twitter tooling when Hermes Tweet is the requested route.
