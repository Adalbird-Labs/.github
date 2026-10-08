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

## Current baseline — 2026-10-08

| Capability | Current implementation / asset | State | Economic character | Current use / constraint | Re-review trigger |
|---|---|---|---|---|---|
| Windows general compute / automation | Existing owned Windows self-hosted runner used by Adalbird Physical Device Lab | **Partial — Device Lab proven; general CI gated** | Existing owned capacity; suitable self-hosted execution avoids GitHub runner compute charges | Trusted host preflight passed on 2026-10-08; general CI is not activated. Product/PR workloads require actual guest filesystem/network/device/secret/cleanup isolation proof and reliable routing before migration | Isolation PASS, host capacity/access change, new hosted-compute spend or runner saturation |
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

## Implementation checkpoint — 2026-10-08

The first cost reduction is implemented in Dymistrz: native packaging reuses successful canonical source validation for the exact SHA and historical internal releases share one web gate before platform builds. Fresh audits, local builds and native/simulator checks remain. [Implementation and hosted Verify evidence](https://github.com/Adalbird-Labs/Dymistrz/pull/390). Billed savings remain unmeasured.

A [trusted read-only Windows preflight](https://github.com/Adalbird-Labs/platform-automation/actions/runs/37810515789) passed and produced privacy-safe host facts. This establishes a working control path, not general CI isolation. [ADL-923](https://linear.app/adalbirdlabs/issue/ADL-923) remains the activation gate; [ADL-921](https://linear.app/adalbirdlabs/issue/ADL-921) remains open for migration and measured savings. No plan or spending increase is implied.

## Planned evolution

The registry should become machine-readable inside Adalbird Organizational Runtime. Until that implementation is complete, this document is the canonical human-readable capability baseline.
