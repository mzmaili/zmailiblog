---
title: "Explicit Forward Proxy for Microsoft Entra Internet Access"
date: 2026-05-12 00:00:00 +0800
categories:
  - Global Secure Access
tags:
  - Microsoft Entra
  - Global Secure Access
  - Internet Access
  - Secure Web Gateway
  - Conditional Access
description: "Explicit Forward Proxy gives you a client-less path to route browser traffic through Microsoft Entra Internet Access."
header:
  og_image: /assets/images/explicit-forward-proxy-for-internet-access.png
  teaser: /assets/images/explicit-forward-proxy-for-internet-access.png
---
![Explicit Forward Proxy for Internet Access](/assets/images/explicit-forward-proxy-for-internet-access.png "Explicit Forward Proxy for Microsoft Entra Internet Access")
<br><br>
Plenty of internet traffic still originates from places where installing the Global Secure Access client just isn't realistic — multi-session VDI, kiosks, Linux desktops, lightly managed endpoints, and BYOD that only needs a secured browser path. Those are exactly the scenarios where visibility and policy consistency tend to fall apart. **Explicit Forward Proxy for Microsoft Entra Internet Access**, now in **Public Preview**, closes that gap by securing browser traffic without a full client deployment.

## What the feature does

Explicit Forward Proxy gives you a client-less path to route browser traffic through Microsoft Entra Internet Access. Instead of relying on the Global Secure Access agent, you point browsers at a tenant-specific **PAC (proxy auto-config) file**, and their internet traffic flows through the service.

That means you can extend **Secure Web Gateway and AI Gateway** controls — including TLS inspection and policy enforcement — to endpoints that could never run the client. The control point moves to the browser configuration rather than the device agent.

## Why it matters

- **Cover hard-to-standardize endpoints** like VDI, kiosks, Linux, and BYOD that can't take the full client.
- **Extend consistent web and AI controls** to browser-only access instead of leaving those sessions unmanaged.
- **Reduce visibility gaps** in frontline, contractor, and shared-device scenarios where browser-only usage is the norm.

## How to enable it

Explicit Forward Proxy is in **Public Preview**, so validate it on a test endpoint group before broad rollout.

1. In the **Microsoft Entra admin center**, go to **Global Secure Access > Session management > Explicit Forward Proxy**.
2. Turn on **Internet Access** and copy the tenant **PAC file URL**.
3. Push that PAC configuration to **Microsoft Edge** with Intune, or add it through browser proxy settings.
4. **Trust the TLS inspection certificate** and align **Conditional Access** for the targeted users.

## Where it fits

This rounds out Microsoft Entra Internet Access for the messy reality of real environments. The client-based path is still the right answer for managed devices, but a single deployment model never covers everything. Explicit Forward Proxy gives you a second enforcement mode for the endpoints that fall outside agent-based management, so your Secure Web Gateway and AI Gateway policies apply consistently regardless of how the browser session originates. Because Conditional Access still applies, you keep identity-aware control over those sessions instead of treating them as an exception.

## Conclusion

If you manage endpoints that can't take the Global Secure Access client, this preview is worth testing right away. It extends the controls you already trust to the browser-only scenarios that are usually the hardest to secure — without forcing a client onto devices that were never going to accept one.

## References:
- [Configure explicit forward proxy for Internet Access](https://learn.microsoft.com/en-us/entra/global-secure-access/how-to-configure-explicit-forward-proxy)
