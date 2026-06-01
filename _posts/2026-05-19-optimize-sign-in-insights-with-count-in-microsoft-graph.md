---
title: "Optimize Sign-In Insights with Count in Microsoft Graph"
date: 2026-05-19 00:00:00 +0800
categories:
  - Identity Security
tags:
  - Microsoft Entra
  - Microsoft Graph
  - APIs
  - Security Analytics
  - Sign-In Logs
description: "The sign-in logs API (/auditLogs/signIns) now honors the OData $$count query parameter."
header:
  og_image: /assets/images/optimize-sign-in-insights-with-count-in-microsoft-graph.png
  teaser: /assets/images/optimize-sign-in-insights-with-count-in-microsoft-graph.png
---
![Optimize Sign-In Insights with Count in Microsoft Graph](/assets/images/optimize-sign-in-insights-with-count-in-microsoft-graph.png "Optimize Sign-In Insights with Count in Microsoft Graph")
<br><br>
If you build on Microsoft Entra sign-in data, this is a quietly important update. Microsoft Graph now supports **`$count`** in sign-in API requests, so your queries can return the total number of matching records alongside the data set you actually need. It sounds minor, but anyone who has built dashboards or detection pipelines on sign-in logs knows how much friction this removes.

## What the feature does

The sign-in logs API (`/auditLogs/signIns`) now honors the OData **`$count`** query parameter. With it, a request can return the **total count of matching records** without you having to page through the entire result set just to know how big it is.

Count works alongside the rest of the OData toolbox — **`$filter`**, **`$select`**, **`$orderby`**, **`$top`**, and **`$expand`** — so you can shape both the data and its size in a single, intentional request.

## Why it matters

- **Design dashboards more easily** when you can show totals without retrieving every record behind them.
- **Make background jobs more efficient** by knowing result sizes up front and avoiding unnecessary processing.
- **Keep apps lean** when they only need selected properties or a filtered slice of sign-in data.

## How to enable it

Count support is in **Public Preview**, so validate your query patterns and result totals before wiring them into production reporting.

1. Query **`/auditLogs/signIns`** with **`$count=true`**.
2. Add **`$filter`** to narrow by time range, application, or status.
3. Use **`$select`** and **`$orderby`** to trim and sort the payload.
4. Pair it with **`$top`** or **`$expand`** as needed for the specific reporting or investigation scenario.

## Where it fits

This is a developer and analytics quality-of-life improvement that pays off across the board. Operational dashboards get accurate totals without expensive full pulls. Detection and reporting jobs can size their work before they start. And any app consuming sign-in data can be more precise about what it asks for. Because count composes with the existing OData parameters, you don't have to rethink your queries — you just get a more efficient way to express what you already wanted.

## Conclusion

If you own Entra analytics, detections, or operational dashboards, this is an easy one to adopt right away. Count-aware queries let you ask for exactly what you need — the right slice of data and its total — in a single request. Test your filters and totals against known data sets, then fold the pattern into your existing pipelines.

## References:
- [List signIns – Microsoft Graph API](https://learn.microsoft.com/en-us/graph/api/signin-list?view=graph-rest-1.0)
