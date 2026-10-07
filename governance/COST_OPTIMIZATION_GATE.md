# Adalbird Labs — Cost Optimization Gate

**Status:** Canonical / Cross-project  
**Owner:** CFO + CTO; CPO joins where product need/value is material  
**Effective:** 2026-10-07  
**Applies to:** company, platform, product, architecture, provider, infrastructure and portfolio decisions

## Purpose

Prevent cost optimization from depending on somebody noticing an opportunity manually.

Every material decision receives a proportional cost lint before approval or implementation. The lint is lightweight when cost impact is clearly immaterial and deeper when the decision introduces, expands, duplicates or locks in a capability, provider or recurring operating cost.

This gate never authorizes expenditure. The Founder-only Spend Golden Rule remains absolute.

## Mandatory decision sequence

Before buying or expanding a capability, evaluate in this order:

1. **Eliminate** — can the need be removed, simplified or deferred?
2. **Reuse** — can an existing Adalbird Labs capability already satisfy it?
3. **Share** — can one shared cross-product capability serve multiple products?
4. **Self-host** — can existing owned capacity deliver the need safely at lower total cost?
5. **Buy** — use an external paid capability only when the preceding options are inferior on total value/risk.

The cheapest sticker price does not automatically win. Reliability, founder time, maintenance, security, delivery speed, scalability and opportunity cost belong in TCO.

## Cost lint fields

For every material decision, record enough evidence to answer:

- **Cost impact:** none / one-time / recurring / usage-based / uncertain.
- **12-month TCO:** amount or bounded range where meaningful; include maintenance/founder-time effects when material.
- **Existing capability available?:** yes / partial / no / unknown.
- **Alternatives considered:** at minimum the applicable Eliminate / Reuse / Share / Self-host / Buy options.
- **Recommended option and why.**
- **Scope affected:** company / platform / named products.
- **Expected utilization or demand signal** where capacity economics matter.
- **Re-review trigger:** concrete event that should reopen the decision.

A zero-cost or clearly immaterial decision may PASS with a short lint. Do not manufacture analysis or bureaucracy where no material cost/capability consequence exists.

## Joint CFO + CTO ownership

CFO owns:
- spend visibility, recurring-cost exposure, TCO framing and capital efficiency;
- detecting provider-cost growth, low-utilization paid assets and renewal risk;
- measuring realized savings after optimization.

CTO owns:
- architecture/capability alternatives, reuse, shared-platform options and self-host feasibility;
- operational/security/reliability cost of each option;
- identifying when new owned capacity can replace purchased compute/services.

CPO joins when the decision depends on whether the capability should exist at all, whether demand justifies it, or whether product value is lower than the cost to serve.

No function may treat its local result as complete when another function holds evidence that can materially change the economic decision.

## Capability Registry

The canonical capability inventory is `governance/CAPABILITY_REGISTRY.md`.

Before recommending a new paid capability, the decision owner must consult the registry. If the registry is incomplete or stale for a material decision, refresh the relevant entry rather than assuming the capability is unavailable.

Each material new capability must trigger a **reverse substitution scan**:

> Which existing costs, providers, duplicated implementations or manual work can this new capability now reduce or eliminate?

This scan is mandatory even when the new capability itself was created for a different purpose.

## Automatic reopen triggers

A cost decision must be reconsidered when any of the following materially occurs:

- a new reusable/shared/owned capability becomes available;
- provider price, terms or charging model changes;
- usage reaches **80%** of a budget/quota/capacity threshold;
- a paid capability remains materially underused;
- the same capability is implemented or purchased by **3+ products**;
- a renewal window opens;
- meaningful scale-up or scale-down changes unit economics;
- a safer/cheaper self-host or provider option becomes credible;
- a product's value/usage falls enough to challenge its cost-to-serve.

These are review triggers, not automatic permission to mutate production or spend.

## Cost Opportunity Scanner

At least weekly, Adalbird Labs runs a portfolio-level scan for material opportunities across current costs and capabilities.

The scanner should produce only actionable, evidence-backed opportunities. Each candidate includes:

- current cost/problem;
- existing capability or alternative;
- expected saving/range where supportable;
- implementation effort/risk;
- affected products;
- recommendation;
- evidence needed to verify the saving.

No-op is a valid result. Do not create busywork to satisfy cadence.

## Closed-loop savings evidence

Optimization is not complete when a recommendation is written.

Use:

**Detect → quantify → recommend → implement → measure → verify → learn**

Where a change claims savings, measure before/after when possible. Portfolio learning must be propagated so later products inherit the cheaper pattern rather than rediscovering it.

## Decision outcomes

A Cost Optimization Gate result is one of:

- **PASS — no material cost issue**
- **PASS — selected option is economically preferred**
- **REVIEW — material uncertainty requires CFO/CTO/CPO evidence**
- **FOUNDER DECISION — spend or another Founder-reserved authority is required**
- **BLOCK — decision lacks required economic/capability evidence**

Only the last two states should normally create a founder dependency.

## Anti-patterns

Do not:
- equate cost control with simply lowering budgets;
- self-host by default when maintenance/security/reliability TCO is worse;
- buy a new service because it is convenient without checking existing capabilities;
- keep a paid tool merely because sunk cost already exists;
- optimize cents while consuming disproportionate founder time;
- record a saving that was not measured or reasonably evidenced;
- use the gate to weaken required safety, security, compliance or release controls.
