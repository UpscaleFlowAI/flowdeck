# FlowDeck

**One dashboard for all your automations.**

FlowDeck gives automation agencies and solo builders a single pane of glass to monitor the health of their n8n, Make, and Zapier workflows. No more tab-switching between three platforms to figure out what broke at 2 AM.

![FlowDeck Dashboard](https://placeholder.flowdeck.dev/screenshot-dashboard.png)

## Why FlowDeck?

- **Unified monitoring** — See every workflow across every platform in one view
- **Instant failure alerts** — Get notified the moment a workflow fails, not when a client complains.
- **Built for agencies** — Multi-workspace support so you can manage dozens of clients without losing your mind

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

## FAQ

**Does FlowDeck have access to my workflow data or customer information?**
No. FlowDeck only reads execution metadata — status, timing, and workflow names. It never touches your workflow payloads, customer data, or credentials. It's read-only by design.

**Can I connect multiple accounts from the same platform?**
Yes. You can connect as many workspaces as your plan allows. An agency managing 10 clients on Zapier and 5 on Make can monitor all of them from one FlowDeck dashboard.

**What happens if one of my platform API keys expires?**
FlowDeck detects the broken connection and marks that workspace as "disconnected" in your dashboard. You'll get a one-time alert so you can re-authenticate. It never silently stops monitoring.

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
