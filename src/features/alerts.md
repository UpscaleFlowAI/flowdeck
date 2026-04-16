# Failure Alerts

## Overview

The Failure Alerts system is FlowDeck's proactive monitoring layer. Rather than requiring operators to keep the dashboard open at all times, it watches for workflow failures in the background and pushes notifications through configured channels the moment something goes wrong. The goal is simple: you should find out about a broken Zap before your client does. Alerts are designed to be actionable — each notification contains enough context to start diagnosing the problem immediately, without logging in to the source platform first.

## Notification Channels and Payload

FlowDeck currently supports two notification channels: email and Slack via incoming webhook. When a workflow execution fails, the alert payload includes the workflow name, the platform it runs on, the workspace it belongs to, the timestamp of the failed execution, and a direct deep-link URL that opens the execution log on the original platform. This deep-link is the most important piece — it turns a notification into a one-click path to diagnosis. For Slack notifications, the payload is formatted as a rich Block Kit message with the workflow name as the header, metadata in a compact fields layout, and the deep-link as a prominent button. Email alerts follow a clean plain-text format that renders well on mobile.

## Alert Rules and Configuration

Alert behavior is configurable per workspace. Operators can mute specific workflows that are known to fail frequently during development or testing, preventing alert fatigue. Quiet hours can be set per workspace so that non-critical failures during off-hours are batched into a morning summary instead of firing individually. For high-priority workflows, operators can configure escalation rules: if a workflow fails three times within a rolling 24-hour window, FlowDeck sends an additional alert to a secondary contact (a team lead or backup on-call person). All alert configuration lives in a dedicated settings panel — no YAML files, no environment variables, just toggles and dropdowns.
