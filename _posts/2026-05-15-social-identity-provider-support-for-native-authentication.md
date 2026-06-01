---
title: "Social Identity Provider Support for Native Authentication is Generally Available"
date: 2026-05-15 00:00:00 +0800
categories:
  - External ID
tags:
  - Microsoft Entra
  - External ID
  - Native Authentication
  - Customer Identity
  - OpenID Connect
  - Social Sign-In
description: "Native authentication lets you keep the primary sign-in and sign-up experience rooted in your own app UI."
header:
  og_image: /assets/images/social-identity-provider-support-for-native-authentication.png
  teaser: /assets/images/social-identity-provider-support-for-native-authentication.png
---
![Social Identity Provider Support for Native Authentication](/assets/images/social-identity-provider-support-for-native-authentication.png "Social Identity Provider Support for Native Authentication")
<br><br>
If you build customer-facing apps, you know the tension: users expect to sign in with the accounts they already have, but you don't want to hand the whole experience over to a redirect that breaks your app's look and feel. **Social Identity Provider Support for Native Authentication is now Generally Available** in Microsoft Entra External ID, and it threads that needle.

## What the feature does

Native authentication lets you keep the primary sign-in and sign-up experience **rooted in your own app UI**. With this release, those native journeys can now include **social identity providers** — Apple, Facebook, Google, and custom OpenID Connect providers.

The social step itself runs in a secure, browser-delegated web-view flow. So users stay in your familiar app experience for the core journey, and the social handoff happens through a standards-based, secure path rather than a bolted-on detour.

## Why it matters

- **Keep an app-first UX** while still offering the consumer sign-in options users expect.
- **Add social providers without building a disconnected identity journey** alongside your native flow.
- **Stay on standards-based identity** with OpenID Connect support for custom providers.

## How to enable it

1. **Enable native authentication** for the app registration in Microsoft Entra.
2. **Configure the social identity providers** you want in External ID.
3. **Add the redirect URI and social sign-in buttons** in your app using the Native Auth SDK pattern.
4. **Pass the right domain hints** and test sign-up and sign-in flows end to end.

## Where it fits

Customer onboarding lives and dies by friction. Every extra redirect, every jarring context switch, costs you conversions at the exact moment you're trying to win a new user. Native authentication already gave developers a way to keep that journey inside the app; adding social providers means you no longer have to choose between a clean native flow and popular consumer sign-in.

For teams building on External ID, this is the missing piece that lets you offer Apple, Google, and Facebook sign-in without fragmenting the experience or giving up policy control.

## Conclusion

This gives teams a cleaner path to customer onboarding without sacrificing control. It's a smart balance: app-first UX, standards-based identity, and a social sign-in flow users already understand — all in the same journey.

## References:
- [Tutorial: Add social sign-in to a native authentication React single-page app](https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-single-page-app-react-social-sign-in)
