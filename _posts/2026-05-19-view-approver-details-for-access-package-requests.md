---
title: "View Approver Details for Access Package Requests is Generally Available"
date: 2026-05-19 00:00:00 +0800
categories:
  - Identity Governance
tags:
  - Microsoft Entra
  - Identity Governance
  - Entitlement Management
  - My Access
  - Access Reviews
  - Zero Trust
description: "When someone submits an access package request, they can now see who their approver is while the request is pending in My Access."
header:
  og_image: /assets/images/view-approver-details-for-access-package-requests.png
  teaser: /assets/images/view-approver-details-for-access-package-requests.png
---
![View Approver Details for Access Package Requests](/assets/images/view-approver-details-for-access-package-requests.png "View Approver Details for Access Package Requests")
<br><br>
Access delays are often communication problems, not policy problems. A request sits pending, nobody knows who's responsible, and the requestor opens a ticket just to find out. **View Approver Details for Access Package Requests is now Generally Available**, fixing a surprisingly common friction point in entitlement management.

## What the feature does

When someone submits an access package request, they can now **see who their approver is** while the request is pending in My Access. Instead of a blind wait, the requestor knows exactly who owns the decision.

Admins keep control: visibility can be set at the **tenant level** or tailored for **specific access packages**, so you decide where this transparency applies.

## Why it matters

- **Reduce approval delays** by showing requestors exactly who owns the pending decision.
- **Cut avoidable support tickets** created just to chase down an approver.
- **Control visibility centrally** while tailoring behavior for specific access packages when needed.

## How to enable it

1. Go to **Identity Governance > Entitlement management > Control configurations** in the Entra admin center.
2. **Enable the tenant-wide setting** that shows approver details for pending access package requests.
3. **Override the behavior** in Advanced request settings on individual access packages when a different experience is needed.
4. **Validate in My Access** that requestors can see the approver name and email on pending requests.

## Where it fits

Entitlement management already does the hard part — routing requests, enforcing approvals, running reviews. But the requestor's experience has always had a blind spot: once you submit, you wait without knowing who's next in line. That ambiguity is where tickets get filed and momentum stalls.

Showing approver details removes the guesswork without adding another approval step or any extra admin overhead. It's a small change that makes the whole My Access experience feel more responsive.

## Conclusion

I like this release because it improves governance without adding screens or admin work. Better transparency usually means fewer delays, fewer tickets, and a much more usable My Access experience. Turn it on, set the right scope, and let requestors help move their own requests along.

## References:
- [View approver details in My Access](https://learn.microsoft.com/en-us/entra/id-governance/my-access-approver-details)
