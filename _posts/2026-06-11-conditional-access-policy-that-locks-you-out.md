---
title: "The Conditional Access Policy That Locks You Out"
date: 2026-06-11 00:00:00 -0500
categories:
  - Conditional Access
tags:
  - Microsoft Entra
  - Conditional Access
  - Identity Security
  - Zero Trust
  - Break-glass accounts
excerpt: "The fastest way to take down your own admins isn't a breach — it's a Conditional Access policy with no exclusions, flipped straight to On."
header:
  og_image: /assets/images/conditional-access-policy-that-locks-you-out-hero.png
  teaser: /assets/images/conditional-access-policy-that-locks-you-out-hero.png
---

![Wide dark banner reading The Conditional Access Policy That Locks You Out, with break-glass, report-only, What If, and staged rollout chips](/assets/images/conditional-access-policy-that-locks-you-out-hero.png "Conditional Access is one of the strongest controls in Entra — and one of the easiest to point at yourself.")
<br><br>

The fastest way to take down your own admins isn't a breach. It's a Conditional Access policy with no exclusions, flipped straight to "On." I've watched it happen more than once, and the pattern is always the same: the technology was right, the rollout discipline was missing.

## What goes wrong

Here's the scenario. A team decides to tighten access — require a compliant device, block legacy authentication, enforce stronger MFA. All reasonable controls. They scope the policy to "All users" and "All cloud apps," and they enable it late on a Friday afternoon because that's when change windows are quiet.

By Monday, the admins who manage Entra can't sign in. Their workstations aren't enrolled yet, or their auth method doesn't satisfy the new grant control, and the policy that's supposed to protect the tenant is now blocking the exact people who could fix it. There's no exclusion, no break-glass path, and no quick rollback — because to roll it back, you'd need to sign in. So you open a support case to recover your own tenant and wait.

The control did precisely what it was told. The problem is that nobody told it to spare the operators.

## Why it matters

Conditional Access sits in the authentication path for every sign-in it touches. That's what makes it powerful — and that's exactly why a scoping mistake doesn't stay small. A typo in a group filter or a single missing exclusion doesn't degrade gracefully; it becomes a tenant-wide lockout in minutes.

Most identity outages I've seen aren't caused by a clever attacker. They're self-inflicted, caused by a good policy deployed without a safety net. The fix isn't more caution in the abstract — it's a repeatable rollout process you run every single time, no exceptions for "this one's simple."

![Summary card: Key takeaways and action steps for rolling out a Conditional Access policy safely](/assets/images/conditional-access-policy-that-locks-you-out-card.png "Break-glass first, report-only second, simulate, then stage the rollout.")

## The rollout discipline that works

Five practices. Run them in order, every time you ship a Conditional Access policy.

### 1. Break-glass accounts come first

Before you build a single restrictive policy, create two or more cloud-only emergency access accounts and exclude them from every Conditional Access policy. Microsoft's guidance is explicit here: these accounts exist for the "break glass" moments when your normal admin accounts can't be used — a federation outage, an MFA service disruption, or the last Global Administrator walking out the door.

Make them cloud-only (`*.onmicrosoft.com`, not federated), give them Global Administrator, store the credentials offline in a physically secured location, split across people, and monitor their sign-ins closely since they should almost never be used. This is the seatbelt. You put it on before you drive, not after the crash.

### 2. Report-only mode is not optional

Report-only mode lets a policy evaluate during real sign-ins without actually enforcing the controls. The results land in the **Conditional Access** and **Report-only** tabs of the sign-in log, and if you've got an Azure Monitor subscription, the Conditional Access insights workbook aggregates the impact for you.

Run every new policy in report-only first and read those logs. You'll see exactly who *would have* been blocked — before anyone actually is. One caution worth knowing: report-only policies that require a compliant device can still prompt macOS, iOS, and Android users for a device certificate during evaluation, so exclude those platforms from device-compliance policies while you're testing.

### 3. Use the What If tool

Report-only tells you what's happening across live traffic. The **What If** tool lets you simulate a specific sign-in on demand — pick a user, an app, and a set of conditions, and it generates a report of which policies would apply and what the result would be. You'll find it under **Entra ID > Conditional Access > Policies > What If**.

Five minutes here catches the scoping mistake that an outage would otherwise teach you. One thing to keep in mind: What If only evaluates policies that are enabled or in report-only mode, and it doesn't account for service dependencies — testing Teams won't pull in the Exchange Online policy that Teams depends on. Use it as a fast sanity check, not a complete substitute for staged rollout.

### 4. Stage the rollout

"All users" on day one is how one typo becomes a tenant-wide incident. Instead, ring it: a small pilot group of willing testers first, then a broader ring, then the rest of the org. Each ring is a chance to catch the edge case — the service account, the kiosk, the contractor on an unmanaged device — before it hits everyone. If something breaks at the pilot ring, you've got a 20-person problem, not a 20,000-person one.

### 5. Mind the gaps you can't see

Two quiet truths. First, "All cloud apps" doesn't literally cover everything — some surfaces and resource access paths sit outside that target, so don't assume one broad policy closes every door. Second, exclusions accumulate. Every "just for now" exception you add to unblock a project tends to stay forever, and over time your policy set drifts from what you think it enforces. Review your exclusions and assignments on a schedule, not after an audit finding makes it urgent.

## Bottom line

Conditional Access is one of the strongest controls in Microsoft Entra ID — and one of the easiest to point straight at yourself. The difference between a security win and a self-inflicted outage isn't the policy logic; it's the discipline around shipping it. Break-glass, report-only, What If, staged rollout. Every time, no shortcuts. The five minutes you spend simulating is always cheaper than the support case that recovers your tenant.

## For more information

- [Conditional Access report-only mode and policy insights](https://learn.microsoft.com/en-us/entra/identity/conditional-access/concept-conditional-access-report-only)
- [Manage emergency access (break-glass) admin accounts](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/security-emergency-access)
- [The Conditional Access What If tool](https://learn.microsoft.com/en-us/entra/identity/conditional-access/what-if-tool)
