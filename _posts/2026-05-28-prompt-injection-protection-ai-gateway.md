---
title: "Prompt Injection Protection in AI Gateway is Generally Available"
date: 2026-05-28 00:00:00 +0800
categories:
  - AI Security
tags:
  - Microsoft Entra
  - Global Secure Access
  - AI Gateway
  - Prompt Injection
  - AI Security
  - Zero Trust
description: "AI Gateway inspects prompt traffic in real time and blocks jailbreak and injection attempts before they reach the model."
header:
  og_image: /assets/images/prompt-injection-protection-ai-gateway.png
  teaser: /assets/images/prompt-injection-protection-ai-gateway.png
---
![Prompt Injection Protection in AI Gateway](/assets/images/prompt-injection-protection-ai-gateway.png "Prompt Injection Protection in AI Gateway")
<br><br>
Prompt injection is one of the first risks security teams run into once AI pilots turn into production workloads. Attackers craft inputs that trick a large language model into ignoring its instructions, leaking data, or taking actions it should never take. If every application team builds its own guardrails, you end up with inconsistent protection and policy drift that is almost impossible to audit.

**Prompt Injection Protection in Microsoft Entra's AI Gateway is now Generally Available**, giving you a single control plane at the network layer instead of a different workaround for every app.

## What the feature does

AI Gateway inspects prompt traffic in real time and blocks jailbreak and injection attempts **before they reach the model**. Because enforcement happens at the network layer through Global Secure Access, the protection is independent of which model, browser, or client your users chose. You get one consistent control without having to rewrite your applications.

This maps directly to **OWASP LLM01: Prompt Injection**, the top risk in the OWASP Top 10 for LLM applications.

## Why it matters

- **Block adversarial prompts and jailbreak attempts** before they reach enterprise AI models.
- **Keep enforcement consistent** across browsers, devices, and generative AI applications.
- **Reduce app-by-app guardrail engineering** as AI usage spreads quickly across the organization.
- **Centralize governance** so security architecture does not fracture as new AI tools are adopted.

## How to enable it

1. **Enable the Internet Access traffic forwarding profile** and assign the right users and groups.
2. **Configure TLS inspection** so prompt traffic can be inspected over encrypted sessions.
3. **Create a prompt policy**, add blocking rules, and choose the conversation schemes you want covered.
4. **Link the policy to a security profile**, apply Conditional Access where needed, and monitor results.

## Where it fits in a Zero Trust architecture

If your organization is already experimenting with internal copilots, external AI tools, or agent workflows, this is the kind of control that keeps your security model coherent. Moving prompt guardrails to the network layer means the control point is the same regardless of how AI is consumed — and centralized guardrails are far easier to operate, monitor, and trust than dozens of per-app implementations.

## Conclusion

Prompt Injection Protection turns a fragmented, app-by-app problem into a single enforcement point that sits in front of your AI traffic. For teams scaling AI adoption, it is a practical way to apply consistent guardrails without slowing down the business or rewriting applications.

## References:
- [Prompt injection protection in Global Secure Access](https://learn.microsoft.com/en-us/entra/global-secure-access/how-to-ai-prompt-injection-protection)
- [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
