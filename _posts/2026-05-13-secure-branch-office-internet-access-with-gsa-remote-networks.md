---
title: "Secure Branch Office Internet Access with GSA Remote Networks is Generally Available"
date: 2026-05-13 00:00:00 +0800
categories:
  - Global Secure Access
tags:
  - Microsoft Entra
  - Global Secure Access
  - Remote Networks
  - Branch Office
  - SSE
  - Zero Trust
description: "Remote Networks connect an entire branch site to Global Secure Access through an IPsec tunnel established from the local router or firewall."
header:
  og_image: /assets/images/secure-branch-office-internet-access-with-gsa-remote-networks.png
  teaser: /assets/images/secure-branch-office-internet-access-with-gsa-remote-networks.png
---
![Secure Branch Office Internet Access with GSA Remote Networks](/assets/images/secure-branch-office-internet-access-with-gsa-remote-networks.png "Secure Branch Office Internet Access with GSA Remote Networks")
<br><br>
A lot of branch and remote-site traffic still comes from devices that will never run a client — printers, kiosks, IoT gear, shared workstations, and the line-of-business box humming in a closet somewhere. **Secure Branch Office Internet Access with GSA Remote Networks is now Generally Available**, bringing those locations into a Zero Trust network path using **IPsec tunnels** from the site CPE.

## What the feature does

Remote Networks connect an entire branch site to Global Secure Access through an IPsec tunnel established from the local router or firewall. No client software, no per-device agents — the site itself becomes the connection point.

Once the branch is connected, security services move to the **network layer**. You can apply web filtering, cloud firewall rules, and threat inspection centrally across both full internet and Microsoft 365 traffic.

## Why it matters

- **Protect branch traffic** without requiring endpoint clients on unmanaged or shared devices.
- **Apply centralized web filtering, firewall controls, and threat inspection** across remote sites.
- **Bring Microsoft 365 and internet access** into the same logging and policy plane.

## How to enable it

1. **Create the remote network** in the right region and enter your branch CPE and BGP details.
2. **Assign the traffic forwarding profiles** that should acquire internet or Microsoft 365 traffic from the site.
3. **Configure the branch router or firewall** with the Microsoft endpoint settings to establish the IPsec tunnel.
4. **Apply cloud firewall or web policies centrally** and verify branch traffic in logs and monitoring views.

## Where it fits

Branch security has always been awkward. Shipping appliances to every site is expensive and slow, and you still can't put an agent on a printer or a kiosk. Remote Networks sidesteps that entirely by securing the site connection rather than each device. For distributed enterprises with dozens or hundreds of locations, that's a far more scalable model — one architecture instead of a rack of boxes per site.

It also unifies your visibility. Branch traffic lands in the same logs and policy model as everything else in Global Secure Access, so you're not stitching together separate tools to understand what's happening at the edge.

## Conclusion

This makes branch protection much easier to scale: one architecture, one logging plane, and one policy model for managed and unmanaged devices alike. For any organization with a long list of sites and a longer list of devices that can't run a client, that's a strong outcome.

## References:
- [Create remote networks in Global Secure Access](https://learn.microsoft.com/en-us/entra/global-secure-access/how-to-create-remote-networks)
