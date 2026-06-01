---
title: "Cloud Firewall with Remote Networks Goes GA in Global Secure Access"
date: 2026-05-14 00:00:00 +0800
categories:
  - Global Secure Access
tags:
  - Microsoft Entra
  - Global Secure Access
  - Cloud Firewall
  - Remote Networks
  - Branch Security
  - Zero Trust
description: "Once branch traffic reaches Global Secure Access through remote networks, Cloud Firewall lets you apply 5-tuple filtering — source IP, destination IP, port, and protocol — to that traffic from the cloud edge."
header:
  og_image: /assets/images/configure-gsa-with-cloud-firewall-and-remote-networks.png
  teaser: /assets/images/configure-gsa-with-cloud-firewall-and-remote-networks.png
---
![Configure GSA with Cloud Firewall and remote networks](/assets/images/configure-gsa-with-cloud-firewall-and-remote-networks.png "Cloud Firewall with Remote Networks Goes GA in Global Secure Access")
<br><br>
Even in a cloud-first architecture, branch traffic still needs old-school network control. The problem is that maintaining that control usually means rule sets scattered across appliances at every site. **Cloud Firewall with Remote Networks** in Global Secure Access pulls that filtering into Microsoft's cloud, so branch internet traffic gets firewall logic without turning every location into its own firewall project.

## What the feature does

Once branch traffic reaches Global Secure Access through **remote networks**, **Cloud Firewall** lets you apply **5-tuple filtering** — source IP, destination IP, port, and protocol — to that traffic from the cloud edge.

You define and manage the rules in one place rather than across separate branch appliances. Each rule carries a priority and an allow or block action, and the policy attaches to the baseline security profile for the remote network. The result is familiar firewall control delivered centrally.

## Why it matters

- **Apply familiar firewall logic to branch traffic** with source and destination IP, port, and protocol controls.
- **Centralize policy management** instead of maintaining rule sets on separate branch appliances.
- **Enforce branch policy from the cloud edge** using baseline security profiles, reducing local drift.

## How to enable it

1. **Create the remote network** and establish the IPsec and BGP connection from your branch CPE.
2. **Create a Cloud Firewall policy** in Global Secure Access with the default allow action.
3. **Add 5-tuple rules**, set unique priorities, and choose allow or block actions for matching traffic.
4. **Link the firewall policy to the baseline profile** for the remote network and review traffic outcomes.

## Where it fits

Zero Trust at the network layer means consistent, centrally governed policy rather than per-site improvisation. Moving branch firewall rules into Global Secure Access gives distributed organizations one control plane for traffic that used to depend on local hardware. You keep the network precision admins expect while shedding the operational sprawl of managing it site by site.

## Conclusion

For distributed organizations, this is a practical step toward cleaner operations. You centralize branch policy, cut local drift, and still get the 5-tuple precision of a real firewall — just delivered from the cloud instead of a rack in every closet.

## References:
- [Configure Cloud Firewall in Global Secure Access](https://learn.microsoft.com/en-us/entra/global-secure-access/how-to-configure-cloud-firewall)
