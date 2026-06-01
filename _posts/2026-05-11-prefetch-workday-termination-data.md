---
title: "Prefetch Workday Termination Data is Generally Available"
date: 2026-05-11 00:00:00 +0800
categories:
  - Identity Governance
tags:
  - Microsoft Entra
  - Workday
  - Provisioning
  - Identity Governance
  - Offboarding
  - Zero Trust
description: "The update lets admins enable termination lookahead so that termination data is prefetched earlier from Workday."
header:
  og_image: /assets/images/prefetch-workday-termination-data.png
  teaser: /assets/images/prefetch-workday-termination-data.png
---
![Prefetch Workday Termination Data](/assets/images/prefetch-workday-termination-data.png "Prefetch Workday Termination Data")
<br><br>
Offboarding delays are more than an HR annoyance — they're an identity risk. Every hour an account stays active past someone's last day is an hour of unnecessary exposure. **Prefetch Workday Termination Data is now Generally Available**, and it closes a real operational gap in the Microsoft Entra Workday connector.

## What the feature does

The update lets admins enable **termination lookahead** so that termination data is prefetched earlier from Workday. With those attributes available sooner, your deprovisioning logic can run closer to the worker's actual **local timeline** instead of trailing behind it.

This is squarely aimed at a timing problem. A connector tied to a single time zone can leave accounts active longer than expected for workers whose last day arrives much earlier locally.

## Why it matters

- **Disable accounts on time** by making termination attributes available before the local deprovisioning window.
- **Reduce exposure for global populations**, especially APAC and ANZ workers affected by Pacific Time scheduling.
- **Strengthen audit confidence** with offboarding that lines up with each worker's actual termination date.

## How to enable it

1. **Open the Workday-to-Entra ID or Workday-to-AD provisioning job** and stop provisioning temporarily.
2. In **Properties**, enable the **termination lookahead query** option.
3. **Update the mapping logic** for account disablement so it evaluates the termination attributes now exposed earlier in the feed.
4. **Apply the changes, restart provisioning**, and validate with a test termination in the affected region.

## Where it fits

If you support workers across multiple time zones, you've probably already felt this pain. A termination processed at midnight Pacific can mean an APAC worker keeps an active account well into their next day. Termination lookahead makes the data available sooner, so your disable logic acts when it should — not when the connector finally catches up.

It's a small configuration change with a direct line to your joiner-mover-leaver process and your access reviews.

## Conclusion

This is the kind of fix that improves security, operations, and audit confidence all at once. Cleaner offboarding timing reduces standing risk and removes a recurring exception your governance team has to explain. Enable it, test a termination in an affected region, and tighten one of the most important moments in the identity lifecycle.

## References:
- [Configure Workday termination lookahead](https://learn.microsoft.com/en-us/entra/identity/app-provisioning/configure-workday-termination-lookahead)
