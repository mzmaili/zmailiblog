---
title: "External User Access Comes to the GSA Windows Client"
date: 2026-05-21 00:00:00 +0800
categories:
  - Global Secure Access
tags:
  - Microsoft Entra
  - Global Secure Access
  - Private Access
  - External Identities
  - B2B Collaboration
  - Zero Trust
description: "External guests and external members can sign in with their home tenant identity, switch into the right resource tenant, and reach assigned private applications from the same Global Secure Access Windows client."
header:
  og_image: /assets/images/external-user-access-in-gsa-windows-client.png
  teaser: /assets/images/external-user-access-in-gsa-windows-client.png
---
![External user access in the GSA Windows client](/assets/images/external-user-access-in-gsa-windows-client.png "External User Access Comes to the GSA Windows Client")
<br><br>
Partner access usually breaks down at the handoff between identity and connectivity. You can invite a guest, but getting them to the right private app — without duplicating accounts or building a bespoke path for every partner — has always been the hard part. **External User Access in the GSA Windows Client** makes that handoff much cleaner.

## What the feature does

External guests and external members can sign in with their **home tenant identity**, switch into the right resource tenant, and reach assigned private applications from the same Global Secure Access Windows client.

The release works because the Windows client is tenant-aware. It automatically discovers the external tenant context, **routes only the private application traffic** that belongs to the resource tenant, and leaves the rest alone. Admins don't have to duplicate accounts or invent separate access paths for each partner relationship.

## Why it matters

- **Supports guest and member collaboration** without forcing external users into duplicate account patterns.
- **Routes only the resource tenant's private app traffic** instead of tunneling everything from the partner device.
- **Keeps visibility, policy, and cross-tenant security signals** in one operating model.

## How to enable it

1. **Add the external users to the resource tenant** as guests or members and assign the required private applications.
2. **Install the Global Secure Access Windows client** on the partner device and enable external user access through MDM or Group Policy.
3. **Include the external accounts** in the Private Access traffic forwarding profile for the resource tenant.
4. **Have the user switch to the resource tenant** in the client and validate access to the assigned private apps.

## Where it fits

Zero Trust for collaboration means external users get scoped, verified access to exactly what they need — and nothing more. Routing only the relevant private application traffic, while preserving cross-tenant signals, keeps partners inside your policy and visibility model instead of outside it. That's a far healthier operating model than duplicate accounts and one-off connectivity hacks.

## Conclusion

This is the kind of feature that removes friction without watering down control. For contractors, suppliers, and cross-tenant project teams, you get cleaner collaboration, stronger visibility, and one consistent way to grant external users the private apps they actually need.

## References:
- [External user access in Global Secure Access](https://learn.microsoft.com/en-us/entra/global-secure-access/concept-external-user-access)
