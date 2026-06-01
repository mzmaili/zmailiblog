---
title: "Privileged Identity Response for SOCs in Microsoft Defender"
date: 2026-05-23 00:00:00 +0800
categories:
  - Identity Security
tags:
  - Microsoft Entra
  - Microsoft Defender
  - SOC
  - Incident Response
  - Privileged Access
description: "This brings identity containment actions into the tools SOC analysts already work in."
header:
  og_image: /assets/images/privileged-identity-response-for-socs.png
  teaser: /assets/images/privileged-identity-response-for-socs.png
---
![Privileged Identity Response for SOCs](/assets/images/privileged-identity-response-for-socs.png "Privileged Identity Response for SOCs in Microsoft Defender")
<br><br>
When an account is compromised, every minute spent escalating to an IAM admin is a minute the attacker keeps working. **Privileged Identity Response for SOCs**, now in **Public Preview**, extends the **Entra Security Operator** path so SOC analysts can take identity response actions directly from the Microsoft Defender RBAC experience — without handing them broad Entra admin roles in the middle of an incident.

## What the feature does

This brings identity containment actions into the tools SOC analysts already work in. From the **Microsoft Defender** experience, analysts can:

- **Disable a user**
- **Revoke active sessions**
- **Mark an account as compromised**
- **Force a password reset**
- **Remove an authentication method**

Permissions are granted through **Microsoft Defender unified RBAC**, mapped to the Entra Security Operator capabilities. Analysts get exactly the response actions they need — and nothing more — scoped to the incident workflow rather than the broader identity admin surface.

## Why it matters

- **Faster containment** because analysts act inside the incident, instead of escalating and waiting on an IAM admin.
- **Least privilege intact** since response actions are scoped through Defender RBAC rather than broad Entra roles.
- **Cleaner separation of duties** that keeps defenders effective without expanding the standing admin footprint.

## How to enable it

This capability is in **Public Preview**, so pilot it with a scoped set of analysts and roles before relying on it for live incident response.

1. Go to the **Microsoft Defender portal** and open **System > Permissions**.
2. Activate or review **Microsoft Defender unified RBAC** for the workloads in scope.
3. Map or create **role assignments** for SOC analysts in the Defender RBAC experience.
4. Use the new **identity response actions** during investigations to contain impacted accounts directly from the incident workflow.

## Where it fits

This is the kind of control that reflects how SOCs actually operate. Defenders live in Defender; identity admins live in Entra. Forcing a handoff between the two during an active incident adds latency exactly when speed matters most. By scoping identity response actions through Defender RBAC, you give analysts fast containment power while keeping the principle of least privilege intact — no one walks away with standing Entra admin rights just to disable a compromised account. It's separation of duties done in a way that helps responders rather than slowing them down.

## Conclusion

Privileged Identity Response removes friction precisely where every minute counts. Analysts contain threats from the incident workflow they already use, and the organization avoids handing out broad identity roles to do it. Pilot it with a defined set of analysts and role assignments, validate the actions against your response runbooks, then expand coverage as you build confidence.

## References:
- [Microsoft Defender unified role-based access control (RBAC)](https://learn.microsoft.com/en-us/defender-xdr/manage-rbac)
