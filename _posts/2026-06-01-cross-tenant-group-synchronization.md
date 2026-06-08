---
title: "Cross-Tenant Group Synchronization"
date: 2026-06-01 00:00:00 -0500
categories:
  - Identity Governance
tags:
  - Microsoft Entra ID
  - Identity Governance
  - Cross-tenant Access
  - Group Management
  - Provisioning
excerpt: "Cross-tenant group synchronization is generally available for synchronizing security groups and memberships across Entra tenants."
header:
  og_image: /assets/images/cross-tenant-group-synchronization-hero.png
  teaser: /assets/images/cross-tenant-group-synchronization-hero.png
---

![Security groups synchronized across multiple tenants](/assets/images/cross-tenant-group-synchronization-hero.png "Cross-Tenant Group Synchronization")
<br><br>

Multi-tenant environments are normal now. Subsidiaries, mergers, regional tenants, regulated business units, and partner operations all create the same identity problem: access needs to cross tenant boundaries, but group management often gets duplicated and messy.

Cross-tenant group synchronization is now generally available. It extends Microsoft Entra cross-tenant synchronization so organizations can synchronize security groups and memberships from a source tenant into one or more target tenants, supporting cleaner shared application access and authorization decisions.

## What it is

Cross-tenant synchronization already helps automate creating, updating, and deleting B2B collaboration users across tenants in an organization. With group synchronization, the same model can include security groups. A group managed in the source tenant can be made available in a target tenant so apps and resources there can use consistent group-based controls.

Microsoft’s documentation describes cross-tenant synchronization as a push process from the source tenant. Users and groups in scope are configured in the source tenant, attribute mapping is configured there, and the target tenant uses inbound cross-tenant synchronization settings to allow synchronization. Target tenant administrators can stop synchronization at any time.

The GA announcement notes that cross-tenant group synchronization requires Microsoft Entra ID Governance licensing. Existing licensing requirements for cross-tenant user synchronization remain unchanged.

## Why it matters

Without this, many organizations end up rebuilding the same groups in multiple tenants or relying on manual processes to keep access aligned. That is fragile. Membership drift becomes normal, deprovisioning depends on someone remembering every copy of a group, and authorization decisions vary by tenant.

Centralizing group ownership in a source tenant gives admins a clearer source of truth. Target tenants can still enforce their own policies, but they can base access on synchronized group objects and memberships instead of duplicate local constructs.

![Summary card for cross-tenant group synchronization](/assets/images/cross-tenant-group-synchronization-card.png "Generally available: Cross-Tenant Group Synchronization")

This is especially useful for shared applications, resource authorization, and governance scenarios where accountability needs to stay with one team even though access spans multiple tenants.

## How to enable it

Start by confirming licensing and scope. Cross-tenant group synchronization requires Microsoft Entra ID Governance or Microsoft Entra Suite licensing for the group sync capability. Then identify the source tenant that owns group membership and the target tenant or tenants where those groups need to be available.

In the target tenant, configure cross-tenant access settings for the partner/source tenant. The cross-tenant synchronization settings are inbound organizational settings and include controls to allow user synchronization and group synchronization into the tenant. The automatic redemption setting is also important for cross-tenant synchronization because it suppresses invitation and consent friction when configured correctly on both sides.

In the source tenant, configure cross-tenant synchronization. Assign the users and security groups in scope, review attribute mappings, and test provisioning into the target tenant. Because this uses the Microsoft Entra provisioning engine, treat it like any other provisioning rollout: start narrow, validate objects and memberships, check provisioning logs, and then expand.

A practical pilot might include one source security group, one target tenant, and one application that uses the synchronized group for access. Confirm that membership changes in the source tenant appear in the target tenant, that removed users are deprovisioned as expected, and that the target application evaluates the synchronized group correctly.

Also decide who owns ongoing operations. Source tenant admins manage membership. Target tenant admins control whether synchronization is allowed and can stop it. That split is healthy, but it needs to be documented.

## Bottom line

Cross-tenant group synchronization is not just a convenience feature. It reduces identity drift across tenants and gives organizations a cleaner way to apply group-based access in multi-tenant environments without copying the same administrative work everywhere.

For more information, see [What is cross-tenant synchronization in Microsoft Entra ID?](https://learn.microsoft.com/en-us/entra/identity/multi-tenant-organizations/cross-tenant-synchronization-overview).
