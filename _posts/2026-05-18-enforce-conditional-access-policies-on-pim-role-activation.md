---
title: "Enforce Conditional Access on PIM Role Activation"
date: 2026-05-18 00:00:00 +0800
categories:
  - Privileged Access
tags:
  - Microsoft Entra
  - PIM
  - Conditional Access
  - Privileged Access
  - Just-in-Time
  - Zero Trust
description: "When a user activates an eligible privileged role in Privileged Identity Management (PIM), you can now require Conditional Access controls right at that activation event — not just at the original sign-in."
header:
  og_image: /assets/images/enforce-conditional-access-policies-on-pim-role-activation.png
  teaser: /assets/images/enforce-conditional-access-policies-on-pim-role-activation.png
---
![Enforce Conditional Access policies on PIM role activation](/assets/images/enforce-conditional-access-policies-on-pim-role-activation.png "Enforce Conditional Access on PIM Role Activation")
<br><br>
Privileged access should never ride on stale trust. A user who signed in hours ago and now wants to step into an admin role is a different risk than they were at sign-in. **Enforce Conditional Access Policies on PIM Role Activation** lets Microsoft Entra apply current Conditional Access controls at the exact moment of elevation.

## What the feature does

When a user activates an eligible privileged role in **Privileged Identity Management (PIM)**, you can now require **Conditional Access** controls right at that activation event — not just at the original sign-in.

You do this through a Conditional Access **authentication context** that the role binds to. At activation, Microsoft Entra evaluates current signals and can require MFA, a specific authentication strength, a compliant device, or other authentication-context requirements before the user steps into the role.

## Why it matters

- **Uses current signals at elevation**, so trust is re-evaluated when a user requests privileged access.
- **Requires stronger authentication or device trust** for the precise moment of role activation.
- **Strengthens just-in-time admin access** with a cleaner, well-placed Zero Trust control point.

## How to enable it

1. **Create the Conditional Access authentication context** and build a policy that enforces the controls you want for activation.
2. Go to **ID Governance > Privileged Identity Management > Microsoft Entra roles > Roles** and open the target role.
3. **Edit role settings** and require the Conditional Access authentication context on activation, along with any approval or duration rules.
4. **Test the activation flow** with an eligible admin to confirm the new controls are enforced at elevation time.

## Where it fits

This is Zero Trust expressed where it matters most for administrators: at the boundary between standing eligibility and active privilege. Tying Conditional Access to activation means elevation depends on the user's current posture — fresh MFA, a compliant device, the right authentication strength — rather than assumptions carried over from an earlier session.

## Conclusion

Current signals, just-in-time elevation, and less reliance on assumptions: that's how privileged access should behave. For any team tightening admin controls, enforcing Conditional Access at PIM activation is a clean, high-value improvement that closes a real gap in the elevation flow.

## References:
- [Configure Microsoft Entra role settings in PIM](https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/pim-how-to-change-default-settings)
