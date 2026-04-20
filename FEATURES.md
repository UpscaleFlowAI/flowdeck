# Features

FlowDeck ships three core capabilities designed to keep automation professionals in control without adding another complex tool to their stack.

---

## Unified Dashboard

The dashboard pulls live status data from every connected automation platform and renders it in a single, sortable table. Each row shows the workflow name, its parent platform, last execution time, run duration, and a clear pass/fail/inactive badge. Agencies managing dozens of client workspaces can group workflows by client and collapse sections they don't need to watch, reducing visual noise to only what matters right now. The view refreshes automatically — every 90 seconds on paid tiers, every 5 minutes on the free plan — so the data you see is never stale enough to miss a problem.

---

## Failure Alerts

When a workflow execution fails, FlowDeck detects the failure on its next polling cycle and fires a notification through your configured channels. Currently supported channels are email and Slack (via incoming webhook). Each alert includes the workflow name, the platform it runs on, the timestamp of the failure, and a direct deep-link back to the execution log on the original platform so you can diagnose the issue without hunting through tabs. Alert rules are configurable per workspace: you can mute noisy workflows, set quiet hours, or escalate repeated failures to a secondary contact.

---

## Multi-Platform Integrations

FlowDeck connects to n8n, Make, and Zapier using each platform's official API. Setup takes under two minutes per platform — paste an API key or OAuth token, select which workspaces to monitor, and FlowDeck begins pulling execution data immediately. The integration layer normalizes status codes and execution metadata across platforms so that a "failed" Zap and a "crashed" n8n workflow show up with the same red badge and the same data structure. This normalization is what makes the unified dashboard and cross-platform alerting possible without you learning three different error taxonomies.

---

## Direct WhatsApp Support

Every FlowDeck page now includes a direct WhatsApp contact button so you can reach the team from your phone in one tap. The button opens a pre-filled WhatsApp conversation with our support line, letting agency operators skip email queues and get a real human on a connection issue, a billing question, or a platform integration quirk. Response times on WhatsApp target under an hour during weekday business hours, with after-hours messages queued for next-day follow-up.
