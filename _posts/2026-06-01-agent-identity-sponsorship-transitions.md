---
title: "Agent Identity Sponsorship Transitions: Keep ownership from going stale"
date: 2026-06-01 00:00:00 -0500
categories:
  - Identity Governance
tags:
  - Microsoft Entra
  - Identity Governance
  - Agent Identity
  - Lifecycle Workflows
  - AI Governance
excerpt: "Agent Identity Sponsorship Transitions help lifecycle workflows notify and transfer ownership when an agent sponsor changes."
header:
  og_image: /assets/images/agent-identity-sponsorship-transitions-hero.png
  teaser: /assets/images/agent-identity-sponsorship-transitions-hero.png
---

![Agent Identity Sponsorship Transitions](/assets/images/agent-identity-sponsorship-transitions-hero.png "Agent Identity Sponsorship Transitions")
<br><br>

Agent identities are becoming part of the real identity estate. That means they need the same accountability model we expect for users, workload identities, applications, and privileged roles: someone has to own the access, review it, and answer for it when the context changes.

Agent Identity Sponsorship Transitions in Microsoft Entra ID Governance are now generally available. The feature adds sponsor-focused tasks to Lifecycle Workflows so agent ownership does not quietly go stale when the original human sponsor moves or leaves.

## What it is

Microsoft Entra agent identity governance uses sponsors to keep a human accountable for an agent identity’s lifecycle and access decisions. Sponsorship is especially important because agents can act across services, workflows, and business processes. If the sponsor leaves the organization, changes teams, or no longer owns the business process, the agent should not sit in a governance blind spot.

The generally available sponsorship transition tasks plug into Microsoft Entra Lifecycle Workflows. The Microsoft Learn article lists three sponsor-related tasks:

- Send email to manager about sponsorship changes.
- Send email to cosponsors about sponsor changes.
- Transfer agent identity sponsorships to manager.

These tasks are classified as mover and leaver tasks. That detail matters. You add them to mover or leaver workflow templates, not to every workflow type.

## Why it matters

A stale owner field is not just an administrative inconvenience. It creates an accountability problem. When an auditor, incident responder, or security architect asks who approves an agent’s access, “the sponsor left six months ago” is not an acceptable answer.

![Agent Identity Sponsorship Transitions summary card](/assets/images/agent-identity-sponsorship-transitions-card.png "Agent Identity Sponsorship Transitions summary")

The practical value here is continuity. Managers can be notified when sponsorship changes are about to happen. Cosponsors can be informed so they are not surprised by ownership transitions. In the most direct pattern, sponsorship can transfer to the original sponsor’s manager, giving governance teams a reasonable default owner instead of an orphaned agent identity.

Here is what I would watch for: do not treat manager transfer as a substitute for policy. It is a safety net. You still need clear ownership criteria for which agents should exist, which access packages they can use, who reviews them, and what happens when the business process ends.

## How to enable it

Start by confirming that your organization is using the Microsoft Entra capabilities required for agent identity governance. Microsoft Learn notes that Microsoft Entra Agent ID is available for all Microsoft Entra customers, while governance and security features for agents map to the relevant Entra licensing. For ID Governance for agents, Microsoft Entra ID P1 is listed. If agents integrate with Microsoft Agent 365, that integration requires Microsoft Agent 365 licensing for each user.

To configure sponsor workflow tasks:

1. Sign in to the Microsoft Entra admin center as at least a Lifecycle Workflows Administrator.
2. Go to **ID Governance** > **Lifecycle workflows** > **Workflows**.
3. Create a new workflow from a mover or leaver template, or edit an existing mover or leaver workflow.
4. On **Basics**, provide a display name and description, choose the trigger, and continue.
5. Configure the workflow scope so it catches the sponsor transitions you intend to govern.
6. On **Tasks**, add the sponsor task you need: notify the manager, notify cosponsors, transfer sponsorship to the manager, or a combination.
7. Review the workflow and select **Create**.

Be deliberate about scope. A workflow that is too narrow misses transitions. A workflow that is too broad creates noise and trains people to ignore notifications.

## Design guidance

I would separate notification and transfer decisions. Notifications are low-risk and useful for visibility. Transfer is more consequential because it changes who is accountable for the agent. For higher-risk agents, use transfer as a bridge and follow it with a review process so the new sponsor explicitly confirms ownership.

Also document the expected behavior for cosponsors. If a sponsor leaves, should a cosponsor become the primary owner, or should the manager inherit it? The feature gives you workflow tasks; your operating model should define the policy.

## Bottom line

Agent identities are only governable if ownership stays current. Sponsorship transitions make that easier by connecting agent ownership to lifecycle events you already manage. If your organization is building or adopting agents, configure this before you have a pile of agent identities with no accountable human behind them.

For more information, see [Agent identity sponsor tasks in Lifecycle Workflows](https://learn.microsoft.com/en-us/entra/id-governance/agent-sponsor-tasks).
