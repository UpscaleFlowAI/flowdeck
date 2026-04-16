# FlowDeck

**One dashboard for all your automations.**

FlowDeck gives automation agencies and solo builders a single pane of glass to monitor the health of their n8n, Make, and Zapier workflows. No more tab-switching between three platforms to figure out what broke at 2 AM.

![FlowDeck Dashboard](https://placeholder.flowdeck.dev/screenshot-dashboard.png)

## Why FlowDeck?

- **Unified monitoring** — See every workflow across every platform in one view
- **Instant failure alerts** — Get notified the moment a workflow fails, not when a client complains
- **Built for agencies** — Multi-workspace support so you can manage dozens of clients without losing your mind

## Pricing

| Plan | Price | Polling Interval | Workspaces |
|------|-------|-----------------|------------|
| Free | $0/mo | Every 5 minutes | 1 |
| Pro | $29/mo | Every 90 seconds | 10 |
| Agency | $79/mo | Every 90 seconds | Unlimited |

All plans include email and Slack alerts. Agency plan adds priority support and custom webhook integrations.

## Quick Start

```bash
# Clone the repo
git clone https://github.com/your-org/flowdeck.git
cd flowdeck

# Open the landing page locally
open index.html
```

> FlowDeck is currently in early access (v0.3.0). The dashboard is read-only and connects via platform APIs. No write access to your workflows — ever.

## Current Integrations

| Platform | Status       |
|----------|-------------|
| n8n      | Supported   |
| Make     | Supported   |
| Zapier   | Supported   |

## Project Structure

```
flowdeck/
├── index.html              # Landing page
├── src/features/           # Feature specifications
│   ├── dashboard.md
│   ├── alerts.md
│   └── integrations.md
├── docs/
│   └── MARKETING_BRIEF.md  # Brand voice & content guidelines
├── FEATURES.md             # Feature overview
├── CHANGELOG.md            # Release history
└── .github/
    └── NEW_FEATURE_TEMPLATE.md
```

## Contributing

We welcome contributions from the community. Before opening a PR:

1. Check the open issues for something you'd like to tackle
2. Follow the feature spec template in `.github/NEW_FEATURE_TEMPLATE.md`
3. Keep PRs focused — one feature or fix per PR
4. Write clear commit messages (`feat:`, `fix:`, `docs:` prefixes)

## License

MIT — see [LICENSE](LICENSE) for details.

## Links

- [Documentation](https://docs.flowdeck.dev) (coming soon)
- [Roadmap](https://github.com/your-org/flowdeck/projects/1)
- [Discord Community](https://discord.gg/flowdeck)
