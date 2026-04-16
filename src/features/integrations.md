# Multi-Platform Integrations

## Overview

FlowDeck's integration layer is what makes the unified dashboard possible. It connects to n8n, Make, and Zapier through each platform's official API, pulls workflow execution data on a recurring schedule, and normalizes that data into a common format that the rest of FlowDeck can consume. The integration system is designed to be low-friction: connecting a new platform takes under two minutes and requires nothing more than an API key or OAuth token. FlowDeck never writes data back to any platform and never accesses workflow payloads — it only reads execution metadata (status, timing, workflow identity).

## Platform-Specific Connectors

Each supported platform has a dedicated connector module that handles authentication, pagination, and error mapping. The n8n connector uses the n8n REST API and supports both cloud-hosted and self-hosted instances (self-hosted users provide their instance URL during setup). The Make connector authenticates via API key and pulls scenario execution history from the Make API. The Zapier connector uses the Zapier Partner API and requires an OAuth flow for authentication. Despite the differences in auth mechanisms and API shapes, all three connectors output the same normalized data structure: workflow ID, workflow name, execution timestamp, duration in milliseconds, and a status enum of `passing`, `failing`, or `inactive`. This normalization is the key architectural decision — it means the dashboard, alert system, and any future features can treat all workflows identically regardless of origin.

## Reliability and Rate Limiting

Each connector implements retry logic with exponential backoff for transient API failures (timeouts, 5xx responses, rate limit hits). Rate limit budgets are tracked per-platform and per-workspace so that one noisy workspace can't exhaust the API quota for all users. If a connector encounters a persistent authentication failure — such as a revoked API key — it marks the workspace as "disconnected" in the dashboard and sends a one-time alert to the workspace owner so they can re-authenticate. The system never silently stops polling; there's always a visible indicator when data freshness is degraded.
