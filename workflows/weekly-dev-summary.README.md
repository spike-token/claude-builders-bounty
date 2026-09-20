# Weekly Dev Summary (n8n + Claude)

Importable n8n workflow: weekly cron → GitHub API (commits, closed issues, merged PRs) → Claude `claude-sonnet-4-20250514` narrative → Slack/Discord webhook.

## Setup (5 steps)

1. **Import:** n8n → Workflows → Import from file → `workflows/weekly-dev-summary.json`.
2. **Set env/vars:** `GITHUB_OWNER`, `GITHUB_REPO`, `GITHUB_TOKEN`, `ANTHROPIC_API_KEY`, `DELIVERY_WEBHOOK_URL` (Slack/Discord incoming webhook), `SUMMARY_LANG` (`EN` or `FR`).
3. **Schedule:** open `Weekly Cron` node, set to Friday 17:00 (cron `0 17 * * 5`).
4. **Test:** Execute Workflow → confirm `Deliver: webhook` returns 2xx and message appears in channel; save screenshot as `docs/weekly-summary-proof.png`.
5. **Activate:** toggle Active. No secrets are stored in the JSON (all via env/expressions).

## Notes
