---
title: "Federate External Tenants Using OIDC in Microsoft Entra External ID"
date: 2026-05-15 00:00:00 +0800
categories:
  - External ID
tags:
  - Microsoft Entra
  - External ID
  - OIDC
  - Federation
  - Identity Security
description: "This adds OpenID Connect (OIDC) federation between a workforce Microsoft Entra ID tenant and a Microsoft Entra External ID tenant."
header:
  og_image: /assets/images/federate-external-tenants-using-oidc.png
  teaser: /assets/images/federate-external-tenants-using-oidc.png
---
![Federate External Tenants Using OIDC](/assets/images/federate-external-tenants-using-oidc.png "Federate External Tenants Using OIDC in Microsoft Entra External ID")
<br><br>
Connecting workforce identity to customer-facing applications has long meant duplicate accounts — and duplicate accounts mean extra lifecycle work, inconsistent policy coverage, and a confusing sign-in path. **OIDC federation between a workforce tenant and an External ID tenant**, now in **Public Preview**, removes that duplication. Users can sign in to Microsoft Entra External ID applications with the identities they already use in their home Entra tenant.

## What the feature does

This adds **OpenID Connect (OIDC) federation** between a workforce Microsoft Entra ID tenant and a Microsoft Entra External ID tenant. You register an application in the workforce tenant as the identity provider, then configure the External ID tenant to trust it as an OIDC identity provider.

At sign-in, the user authenticates against their **home workforce tenant**, and the External ID application **trusts the resulting identity assertion**. No separate credential, no shadow account — just the identity the user already has.

## Why it matters

- **Eliminate duplicate accounts** and the lifecycle overhead that comes with maintaining them.
- **Keep policy consistent** by letting the home tenant's identity controls drive authentication.
- **Simplify the sign-in journey** so workforce users reach External ID apps without a second set of credentials.

## How to enable it

OIDC federation for External ID is in **Public Preview**, so test the end-to-end flow in a non-production user flow before relying on it.

1. **Register an application** in the workforce Entra ID tenant and add the required federation redirect URIs.
2. **Create a client secret** and capture the **client ID** and **tenant ID**.
3. In the **External ID tenant**, add a new **OpenID Connect identity provider** using the Entra-specific well-known endpoint and issuer URI.
4. Add that identity provider to the **user flow**, then run the flow and test sign-in with a workforce account.

## Where it fits

This is a clean bridge between two worlds that organizations increasingly need to connect: internal workforce identity and external-facing application experiences. If you're building customer or partner apps on External ID but also need your own employees to access them, federation lets you reuse the workforce identity instead of provisioning parallel accounts. That keeps your authoritative source of identity in one place and lets the External ID app focus on the external experience while trusting the home tenant for authentication.

## Conclusion

If you've been looking for a cleaner way to connect workforce identity with External ID apps, this preview is worth exploring. It cuts duplicate accounts, keeps your identity controls consistent, and gives users a simpler path in — all by trusting the identity they already have. Validate the user flow end to end, then plan your rollout from there.

## References:
- [Set up Microsoft Entra ID federation with External ID](https://learn.microsoft.com/en-us/entra/external-id/customers/how-to-entra-id-federation-customers)
