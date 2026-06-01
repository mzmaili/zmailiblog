---
title: "CBA Now Sits Higher in System-Preferred MFA on iOS"
date: 2026-05-05 00:00:00 +0800
categories:
  - Authentication
tags:
  - Microsoft Entra
  - Certificate-Based Authentication
  - System-Preferred MFA
  - iOS Security
  - Phishing-Resistant
  - Zero Trust
description: "System-preferred multifactor authentication looks at the methods a user has registered and presents the most secure one first."
header:
  og_image: /assets/images/cba-elevated-in-system-preferred-mfa-list-on-ios.png
  teaser: /assets/images/cba-elevated-in-system-preferred-mfa-list-on-ios.png
---
![CBA elevated in system-preferred MFA list on iOS](/assets/images/cba-elevated-in-system-preferred-mfa-list-on-ios.png "CBA Now Sits Higher in System-Preferred MFA on iOS")
<br><br>
Strong authentication only helps if the platform actually steers people toward it. Users tend to pick whatever is fastest at the prompt, and on iOS certificate flows used to feel less predictable than they should. **CBA Elevated in System-Preferred MFA List on iOS** changes the default nudge, and that small ordering shift has a real effect on what people choose at sign-in.

## What the feature does

System-preferred multifactor authentication looks at the methods a user has registered and presents the most secure one first. With this update, Microsoft Entra places **certificate-based authentication (CBA)** in the third position of the system-preferred order, ahead of weaker options.

The change is significant on iOS specifically. With the earlier iOS sign-in issues addressed, CBA now operates cleanly as a supported second factor and gets surfaced as a preferred choice. Users can still select another allowed method if your policy permits it — the platform simply leads with the phishing-resistant option instead of leaving it buried in the list.

## Why it matters

- **Guides users to a phishing-resistant factor by default**, instead of letting them drift toward the easiest method in the moment.
- **Brings predictable CBA behavior to iOS**, the platform where certificate flows previously felt inconsistent.
- **Strengthens sign-in without adding friction**, because the user workflow stays the same — only the ordering improves.

## How to enable it

1. **Confirm iOS users are enabled for Microsoft Entra CBA** and have usable certificates provisioned to their devices.
2. In the **Microsoft Entra admin center**, go to **Entra ID > Authentication methods > Settings**.
3. Turn on **System-preferred authentication** for the right group or for all users.
4. **Validate the sign-in flow on iOS** and confirm CBA is offered in the expected order.

## Where it fits

Zero Trust assumes the strongest available control should be the path of least resistance, not the exception. By promoting CBA in the system-preferred order, Microsoft Entra closes the gap between what your policy allows and what users actually do at the prompt. On mobile — where attackers still expect weaker methods to survive — leading with a phishing-resistant factor quietly raises the floor for every sign-in.

## Conclusion

Better method ordering sounds like an operational detail, but it directly shapes user behavior at the moment that matters most. If you're already running CBA, turning on system-preferred authentication is a low-effort way to make the secure choice the obvious one on iOS.

## References:
- [System-preferred multifactor authentication](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-system-preferred-multifactor-authentication)
