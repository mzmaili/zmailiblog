---
title: "Network Content Filtering by File Type in Global Secure Access is Generally Available"
date: 2026-05-09 00:00:00 +0800
categories:
  - Global Secure Access
tags:
  - Microsoft Entra
  - Global Secure Access
  - Data Loss Prevention
  - SaaS Security
  - AI Security
  - Zero Trust
description: "Content filtering inspects and controls file movement at the network layer based on file type."
header:
  og_image: /assets/images/network-content-filtering-by-file-type-global-secure-access.png
  teaser: /assets/images/network-content-filtering-by-file-type-global-secure-access.png
---
![Network Content Filtering by File Type in Global Secure Access](/assets/images/network-content-filtering-by-file-type-global-secure-access.png "Network Content Filtering by File Type in Global Secure Access")
<br><br>
A lot of modern data loss looks completely ordinary. Someone uploads a spreadsheet to a generative AI tool, drags a PDF into personal mail, or pushes a contract to an unmanaged SaaS app. **Network Content Filtering by File Type in Microsoft Global Secure Access is now Generally Available**, giving you a direct way to control that traffic before the file ever leaves the network path.

## What the feature does

Content filtering inspects and controls **file movement at the network layer** based on file type. Because enforcement happens in Global Secure Access, it works across browsers, desktop apps, add-ins, and API-driven transfers — not just one sanctioned application or one endpoint agent.

That coverage matters, because shadow AI and unsanctioned SaaS usage are exactly where files tend to slip past point controls. If the traffic flows through Global Secure Access, the policy applies.

## Why it matters

- **Block sensitive documents, spreadsheets, PDFs, and archives** before they leave managed endpoints.
- **Extend DLP enforcement to network traffic**, instead of depending on a single app or a single endpoint agent.
- **Apply identity-aware policy** to risky uploads headed for AI tools and unmanaged cloud services.

## How to enable it

1. **Enable the Internet Access traffic forwarding profile** for the users or groups you want to protect.
2. **Turn on TLS inspection** so encrypted uploads can be evaluated in transit.
3. **Create a content policy** in Global Secure Access and choose the file MIME types and actions you want enforced.
4. **Link the policy to a security or baseline profile**, then validate with controlled upload tests.

## Where it fits

Security teams keep getting the same question: how do we let people work fast without letting sensitive files wander off? Endpoint DLP and app-native controls each cover part of the picture, but they leave gaps — unmanaged browsers, niche apps, scripted transfers. Filtering at the network layer closes those gaps with a single enforcement point that doesn't care which client moved the file.

This pairs naturally with the rest of the Global Secure Access stack, so file-type filtering becomes another rule in the same identity-aware policy plane you already run.

## Conclusion

This gives security teams a cleaner answer to a very common problem. Instead of trusting that every app and every endpoint enforces the same rules, you decide what file types can leave — and you enforce that at the network layer, where it belongs.

## References:
- [Network content filtering in Global Secure Access](https://learn.microsoft.com/en-us/entra/global-secure-access/how-to-network-content-filtering)
