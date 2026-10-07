# Adalbird Labs — Capability Registry

**Status:** Canonical / Cross-project  
**Owner:** CTO, with CFO cost fields and CPO product-value input where material  
**Effective:** 2026-10-07

## Purpose

Maintain a compact inventory of capabilities Adalbird Labs already owns or can directly use so new decisions can test reuse/share/self-host alternatives before buying more capacity.

This is a decision aid, not an asset inventory. Provider-specific access/authority remains governed by the Systems & Direct-Access Registry and the Founder-only Spend Golden Rule.

## Registry rules

- Refresh an entry when a material decision depends on it.
- Record capability, not just vendor name.
- Distinguish **available**, **partial**, **planned** and **unavailable**.
- Record economic character: sunk/owned, included, free-tier, recurring or usage-based.
- A new capability triggers a reverse substitution scan against current spend and duplicated work.
- Never treat an unverified assumption as available capacity.

## Current baseline — 2026-10-07

| Capability | Current implementation / asset | State | Economic character | Current use / constraint | Re-review trigger |
|---|---|---|---|---|---|
| Windows general compute / automation | Existing Windows self-hosted GitHub runner used by Adalbird Physical Device Lab | **Available / expand use** | Existing owned capacity; marginal GitHub runner charge avoided when self-hosted execution is suitable | Proven for broker/device work; broader CI migration must preserve isolation, reliability and required checks | Any new hosted-compute spend, runner saturation, reliability degradation |
| Android physical regression | S10 baseline through Adalbird Physical Device Lab; S25 opportunistic | **Available** | Existing owned devices | Broker-mediated, sequential-first, allowlisted execution | New Android coverage need, capacity bottleneck |
| iOS/macOS current release compute | Current supported Mac/Xcode host | **Unavailable** | Would require a supported macOS host unless an existing supported asset is found | Legacy MacBook Air can support PoC/admin uses but is not the canonical current-Xcode release host | Supported Mac asset becomes available or Founder authorizes acquisition |
| iOS physical-device automation | Dedicated supported iPhone + Mac host | **Planned / unavailable** | Hardware acquisition may be required | Manual iPhone testing is possible; autonomous Apple Device Lab not established | New iOS product/release demand or hardware becomes available |
| Git repository / PR / rules / CI control plane | GitHub Team | **Available** | USD 48/year current paid period; provider-hosted Actions has included + usage-based compute | Private repos, rulesets/protection and CI orchestration are operational | Renewal, feature change, cheaper equivalent without losing required controls |
| GitHub-hosted CI compute | GitHub-hosted Actions | **Available but cost-sensitive** | Included allowance plus founder-capped usage spend | Keep as fallback/clean environment/specialized workloads; migrate suitable steady workloads to owned runners | 80% usage threshold, new owned runner capacity, renewal |
| Web hosting | Render free-plan services where currently configured | **Available / product-scoped** | Free-tier at current evidenced state | Free tier can change or hit limits | Pricing/usage/availability change |
| Backend/auth/data | Supabase free-plan organization/project where currently configured | **Available / product-scoped** | Free-tier at current evidenced state | Product architecture, limits and compliance still matter | Pricing/usage/availability change; third product needs same platform capability |
| Company file collaboration | Google Drive company identity / Shared Drive | **Available** | Existing Workspace commitment | Company identity must be selected explicitly | Plan/usage/renewal change |
| Company email | Gmail / Google Workspace company identity | **Available** | Existing Workspace commitment | Operational email; admin functions may require provider UI | Plan/usage/renewal change |
| Scheduled AI execution | ChatGPT Automations | **Available** | Existing ChatGPT capability; no spend authority implied | Use for genuine recurring/conditional work only | Product capability/plan change |
| Organizational control plane | Adalbird Organizational Runtime + Linear + GitHub | **Available, bounded** | Existing platform capability | Shadow/read-only and bounded-autonomy gates apply | Autonomy gates or source-of-truth model changes |

## First reverse-substitution finding

**Signal:** Adalbird Labs already owns a functioning Windows self-hosted runner while GitHub-hosted Actions compute has previously exhausted included minutes and consumed founder-authorized overage budget.

**Opportunity:** migrate the subset of Verify/tooling/Android workloads that can run safely and deterministically on owned Windows capacity, preserving GitHub Team as the repository/rules/control plane and GitHub-hosted runners as fallback/specialized capacity.

**Gate:** migration must prove equivalent required-check integrity, isolation, reliability and recovery before broad rollout. No budget increase is authorized by this finding.

## Planned evolution

The registry should become machine-readable inside Adalbird Organizational Runtime. Until that implementation is complete, this document is the canonical human-readable capability baseline.
