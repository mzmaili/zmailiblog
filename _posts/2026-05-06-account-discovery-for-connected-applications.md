---
title: "Account Discovery for Connected Applications in Microsoft Entra ID Governance"
date: 2026-05-06 00:00:00 +0800
categories:
  - Identity Governance
tags:
  - Microsoft Entra
  - ID Governance
  - Provisioning
  - Access Governance
  - Identity Security
description: "Account Discovery scans a connected application and surfaces the identities that already exist in it, sorted into clear categories."
header:
  og_image: /assets/images/account-discovery-for-connected-applications.png
  teaser: /assets/images/account-discovery-for-connected-applications.png
---
![Account Discovery for Connected Applications](/assets/images/account-discovery-for-connected-applications.png "Account Discovery for Connected Applications in Microsoft Entra ID Governance")
<br><br>
The hardest part of bringing an application into governance usually isn't wiring up the connector — it's answering a deceptively simple question: who already has access? Connected apps tend to accumulate a messy mix of assigned users, unassigned users, and local accounts created outside any formal lifecycle process. **Account Discovery for Connected Applications**, now in **Public Preview**, gives Microsoft Entra ID Governance admins that missing visibility directly inside the provisioning experience.

## What the feature does

Account Discovery scans a connected application and surfaces the identities that already exist in it, sorted into clear categories. Instead of starting provisioning blind, you get a structured view of **local accounts**, **unassigned users**, and **assigned users** before you operationalize anything.

The discovery runs from the same provisioning configuration you already use, and it relies on your **direct matching attribute** to correlate existing accounts with Entra identities. That correlation is what lets you decide, account by account, what to keep, clean up, or bring under managed lifecycle controls.

## Why it matters

- **Start onboarding from a clean baseline** instead of inheriting orphaned or unmanaged access without realizing it.
- **Cut manual reconciliation** that would otherwise eat hours of spreadsheet work and connector guesswork.
- **Make app onboarding predictable** by exposing access drift early, before provisioning rules are live.

## How to enable it

Account Discovery is in **Public Preview**, so validate it in a test or non-critical app before you rely on it for production onboarding decisions.

1. Open the **Microsoft Entra admin center** and go to **Identity > Applications > Enterprise applications**.
2. Select the target app and open **Provisioning**.
3. Confirm the provisioning credentials are configured and the **test connection** is healthy.
4. Make sure your **direct matching attribute** is set, then choose **Discover identities**.
5. Review the returned categories — local accounts, unassigned users, and assigned users — and use that view to clean up stale access or assign correlated users.

## Where it fits

This sits at the very front of the application onboarding lifecycle, before you flip provisioning into steady-state operation. If your governance program is expanding to cover more SaaS and line-of-business apps, the value compounds: every app you onboard with a clear access inventory is one fewer source of hidden, ungoverned access later. It pairs naturally with access reviews and lifecycle workflows, since the cleaner your starting state, the more meaningful those downstream controls become.

## Conclusion

Account Discovery turns an opaque, manual reconciliation problem into a structured step inside the provisioning flow. For governance teams, that's a practical win — you onboard apps faster and with far more confidence that you actually know who has access. Test it against a representative app first, then make it a standard part of how you bring new applications into governance.

## References:
- [Discover accounts for connected applications](https://learn.microsoft.com/en-us/entra/identity/app-provisioning/how-to-account-discovery)
