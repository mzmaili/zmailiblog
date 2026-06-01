---
title: "Global Secure Access Client Arrives on iOS and iPadOS"
date: 2026-05-24 00:00:00 +0800
categories:
  - Global Secure Access
tags:
  - Microsoft Entra
  - Global Secure Access
  - iOS Security
  - iPadOS
  - Microsoft Defender for Endpoint
  - Zero Trust
description: "The Global Secure Access client experience now reaches iOS and iPadOS — without a separate GSA agent."
header:
  og_image: /assets/images/global-secure-access-client-on-ios-and-ipados.png
  teaser: /assets/images/global-secure-access-client-on-ios-and-ipados.png
---
![Global Secure Access client on iOS and iPadOS](/assets/images/global-secure-access-client-on-ios-and-ipados.png "Global Secure Access Client Arrives on iOS and iPadOS")
<br><br>
Mobile access is always where policy consistency gets tested. People live in Microsoft 365 on iPhones and iPads, and if your Zero Trust controls stop at the laptop, the gap shows up fast. The **Global Secure Access Client on iOS and iPadOS** closes that gap by extending secure routing to Apple mobile devices.

## What the feature does

The Global Secure Access client experience now reaches iOS and iPadOS — without a separate GSA agent. **Microsoft Defender for Endpoint on iOS** handles the traffic routing through a local VPN model, so you extend secure access using a client many estates already deploy.

With it in place, admins can route **Microsoft 365, Internet Access, and Private Access** traffic from iPhones and iPads through the same security architecture used everywhere else. No extra standalone client, no mobile-specific policy fork.

## Why it matters

- **Extends consistent network policy to iPhone and iPad traffic** instead of treating mobile as a special case.
- **Uses Microsoft Defender for Endpoint on iOS** rather than deploying another standalone client.
- **Routes Microsoft 365, Internet Access, and Private Access traffic** through the same security architecture.

## How to enable it

1. **Onboard your tenant to Global Secure Access** and configure the traffic forwarding profiles you need.
2. **Deploy Microsoft Defender for Endpoint on iOS and iPadOS** through Intune to your target users.
3. **Confirm devices are Microsoft Entra registered** and meet the iOS requirements for the service.
4. **Validate that device traffic is routing** through Global Secure Access and apply your existing policies.

## Where it fits

Zero Trust assumes controls follow the user across every device, not just the managed laptop. Routing mobile traffic through Global Secure Access — reusing Defender for Endpoint instead of adding another agent — keeps your policy direction consistent and avoids the mobile sprawl that usually creeps in. The phone becomes just another enforcement point in the same architecture.

## Conclusion

This makes mobile access look a lot more like the rest of your estate: same policy direction, less exception handling, and a much stronger story for secure work from anywhere. For organizations standardizing on Defender for Endpoint, it's a low-friction way to bring iOS and iPadOS into the fold.

## References:
- [Install the Global Secure Access client for iOS](https://learn.microsoft.com/en-us/entra/global-secure-access/how-to-install-ios-client)
