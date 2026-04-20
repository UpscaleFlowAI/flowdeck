# Changelog

All notable changes to FlowDeck will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/), and this project adheres to [Semantic Versioning](https://semver.org/).

---

## [0.4.1] — 2026-04-20

### Added
- WhatsApp contact button on the landing page, linking directly to the FlowDeck support line for one-tap access from mobile

---

## [0.4.0] — 2026-04-16

### Added
- AI Workflow Summarizer: ask natural-language questions about your workflow history and get instant one-paragraph answers
- Cross-platform query support — summarizer pulls data from n8n, Make, and Zapier in a single response
- Query scoping by client workspace, so you can ask about one client or your entire portfolio
- Pattern detection that surfaces recurring failure trends (e.g., "this Zap fails every Monday morning")

---

## [0.3.0] — 2026-03-28

### Added
- Multi-workspace support: connect and monitor workflows across multiple client accounts from one dashboard
- Workflow grouping by client, letting agencies organize their monitoring view by customer
- CSV export for workflow health reports, covering the last 30 days of execution data

### Changed
- Redesigned the status indicator pills to use color + icon (accessible for colorblind users)
- Improved API polling interval from 5 minutes to 90 seconds for paid-tier workspaces

---

## [0.2.0] — 2026-02-14

### Added
- Real-time failure alerts via email and Slack webhook
- Make (formerly Integromat) integration — connect any Make workspace using an API key
- Dashboard now shows execution duration alongside pass/fail status

### Fixed
- Zapier connection timeout on workspaces with 200+ Zaps
- Duplicate workflow entries appearing when an n8n instance was restarted

---

## [0.1.0] — 2026-01-10

### Added
- Initial release of FlowDeck
- Unified dashboard showing workflow name, last run status, and last run timestamp
- n8n integration via REST API
- Zapier integration via Zapier Partner API
- Basic filtering: search by workflow name, filter by status (active / error / inactive)
