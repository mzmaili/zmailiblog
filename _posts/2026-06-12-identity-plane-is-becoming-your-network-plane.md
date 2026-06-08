---
title: "Your Identity Plane Is Becoming Your Network Plane"
date: 2026-06-12 00:00:00 -0500
categories:
  - Global Secure Access
tags:
  - GlobalSecureAccess
  - SSE
  - SASE
  - ZeroTrust
  - ConditionalAccess
excerpt: "Universal Conditional Access and the Compliant Network Check fold identity and network into one policy decision — and that quietly changes your whole security architecture."
header:
  og_image: /assets/images/identity-plane-is-becoming-your-network-plane-hero.png
  teaser: /assets/images/identity-plane-is-becoming-your-network-plane-hero.png
---

![Banner reading Your Identity Plane Is Becoming Your Network Plane with Global Secure Access badge](/assets/images/identity-plane-is-becoming-your-network-plane-hero.png "Universal Conditional Access and the Compliant Network Check collapse identity and network into one policy plane")
<br><br>

For years, identity and network security ran on two different engines. Conditional Access decided who could authenticate to an app. Firewalls and VPNs decided what the network allowed. Two consoles, two teams, two sets of rules that never quite agreed — and a seam in the middle that attackers learned to live in. The quiet shift in Global Secure Access isn't a single new feature. It's that your network is becoming something Conditional Access can actually *see* and reason about.

## What actually changed

Global Secure Access (GSA) is Microsoft's Security Service Edge — Microsoft Entra Internet Access and Microsoft Entra Private Access, delivered from Microsoft's global wide-area network. On its own, that's "another SSE." The interesting part is what sits on top of it: **Universal Conditional Access**.

Normally Conditional Access governs cloud apps and actions. With GSA, you can point the *same* policy engine at network **traffic profiles** — the Microsoft traffic profile, private resources, and internet access — not just applications. So the controls you already know (require MFA, require a compliant device, block on sign-in risk) can now be enforced against network paths. One especially useful side effect: legacy apps that don't support modern authentication can finally be protected behind a traffic profile.

The second piece is the **Compliant Network Check**. It introduces the idea of a "compliant network" into Conditional Access — meaning the user is connected through *your tenant's* Global Secure Access service. You can then write a policy that says, in plain terms: only grant access if the session is flowing through our Secure Access edge. No IP allow-lists to maintain, no hairpinning traffic through a VPN just to anchor a source IP.

![Summary card listing the takeaways and action steps for consolidating identity and network policy](/assets/images/identity-plane-is-becoming-your-network-plane-card.png "The takeaways: one policy plane, fewer seams, and a single high-value app to start with")

## Why this matters strategically

Step back from the toggles and the shift is architectural.

**It closes the "right token, wrong network" gap.** Compliant network enforcement is designed to reduce token theft and replay. If an adversary steals a session token and tries to replay it from a device that *isn't* on your compliant network, Microsoft Entra ID denies the request at authentication time. For apps that support Continuous Access Evaluation — like Microsoft Graph — a stolen access token replayed from outside your compliant network gets rejected in near-real time, instead of staying valid for its full 60–90 minute lifetime. Valid credentials, valid MFA, wrong path — blocked.

**It consolidates the control plane.** One Conditional Access policy plane covering both identity and network means fewer consoles for your team and fewer seams for an attacker to slip between. The compliant network is tenant-specific by design: a policy in contoso.com can only be satisfied by contoso.com's GSA users. Someone from another tenant can't pass it, no matter what they present.

**It changes the buying conversation.** This is the part executives should sit with. SSE/SASE stops being a separate network purchase with its own vendor, console, and team — and becomes an extension of the identity platform you already run. Your identity control plane is quietly becoming your network control plane too. That reframes budget, ownership, and the org chart, not just the policy editor.

## How to start — pick one app

Here's what I'd do: don't rip and replace anything. Prove the pattern on a single, high-value private app first.

1. **Pick one app.** Choose a private, line-of-business app that matters but isn't your entire revenue stream — something where a blast radius is survivable while you learn.
2. **Put it behind Global Secure Access.** Onboard it through Microsoft Entra Private Access so traffic flows through the Secure Access edge.
3. **Turn on the signal.** In the Microsoft Entra admin center, go to **Global Secure Access > Settings > Session management > Adaptive access** and enable **Conditional Access Signaling for Microsoft Entra ID**. Then confirm you have a named location called **All Compliant Network locations** under **Conditional Access > Named locations**.
4. **Write the policy.** Create a Conditional Access policy that includes **Any location**, excludes **All Compliant Network locations**, and sets the grant control to **Block access**. Exclude your break-glass accounts, and — if you use Intune — exclude the Intune enrollment apps to avoid a circular dependency.

One caution worth repeating: if you build policies on the compliant network check and later disable GSA signaling, you can lock your own users out. Delete the dependent policies *before* you turn the signal off.

Start narrow, watch the sign-in logs, then widen the blast radius once you trust the behavior. You'll feel pretty quickly how much simpler "identity + network in one decision" is than stitching two stacks together.

## Bottom line

The headline isn't the feature — it's the consolidation. Universal Conditional Access plus the Compliant Network Check turn network posture into just another signal your identity policy engine can evaluate. That's a smaller console footprint, a closed replay gap, and a fundamentally different way to buy and own secure access. You don't need a migration project to feel it. You need one app and one policy.

## For more information

- [Learn about Universal Conditional Access through Global Secure Access](https://learn.microsoft.com/en-us/entra/global-secure-access/concept-universal-conditional-access)
- [Enable Compliant Network Check with Conditional Access](https://learn.microsoft.com/en-us/entra/global-secure-access/how-to-compliant-network)
- [What is Global Secure Access?](https://learn.microsoft.com/en-us/entra/global-secure-access/overview-what-is-global-secure-access)
