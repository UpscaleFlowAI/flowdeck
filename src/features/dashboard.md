# Unified Dashboard

## Overview

The Unified Dashboard is the core view of FlowDeck and the first thing users see after connecting at least one automation platform. It renders a single, continuously-updating table of every workflow across every connected workspace, regardless of whether that workflow lives in n8n, Make, or Zapier. The design goal is density without clutter: an agency operator managing 15 client workspaces with 300+ total workflows should be able to scan the dashboard in under 30 seconds and know exactly what needs attention.

## Data Model and Display

Each row in the dashboard represents a single workflow and displays six columns: workflow name, source platform (with a platform icon badge), parent workspace or client group, last execution timestamp, execution duration, and a status badge (passing, failing, or inactive). The status badge uses both color and an icon so the dashboard remains usable for colorblind operators. Rows are sortable by any column and filterable by a free-text search that matches on workflow name, as well as dropdown filters for platform and status. When an agency connects multiple workspaces, the dashboard supports a grouping mode where workflows are organized under collapsible client headers — this keeps the view manageable at scale and lets operators focus on a single client's health when needed.

## Refresh and Performance

The dashboard polls each connected platform's API on a fixed interval: every 90 seconds for paid-tier workspaces and every 5 minutes for free-tier. Polling happens server-side and results are cached, so loading the dashboard in a browser always returns near-instant results rather than waiting for live API calls to resolve. The polling scheduler is staggered across workspaces to avoid burst traffic and to stay within each platform's rate limits. When a new execution result arrives that changes a workflow's status — especially a transition from passing to failing — the dashboard highlights the affected row with a subtle pulse animation so operators notice the change even if they're not actively scanning.
