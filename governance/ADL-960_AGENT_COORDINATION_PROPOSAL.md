# ADL-960 — ChatGPT / Claude coordination (proposal for canonical v1.37)

> **Status: PROPOSED, NOT ACTIVE.** This document records the founder decision from ADL-958 and outlines the required changes to `governance/CHATGPT_OPERATING_RULES.md`. The canonical v1.36 file remains authoritative until it is updated. Do not use this proposal to grant expanded execution, merge or spending authority.

## Decision evidence and responsibilities

- Linear is the operational source of truth for issues, states, blockers and decisions; GitHub is the source of truth for code and PR evidence.
- The founder-approved single-select Linear label group **Agent** has values **Claude** and **ChatGPT**. An issue has at most one active AI operator. Agent labels are not substitutes for fresh issue and comment checks.
- **Claude:** code/branch/PR execution in Grzybolaz, Dymistrz and platform-automation only when a task is eligible and explicitly claimed. The four new `CLAUDE.md` PRs belong exclusively to Claude on ADL-958; website and other production-impacting merges require the founder's separate authorization.
- **ChatGPT:** CPO, CRO, CFO, product management, portfolio planning, governance and scoped company/cross-product work. ADL-960 is ChatGPT-owned, with no edits to Claude's PRs.
- Default source language is English for repository guidance and Polish for founder communication; `dalej` means the same safe continuation for both agents.
- No AI may authorize any expenditure or financial commitment of PLN 0.01 or above, and no new live execution authority is created.

## Claim/skip/handoff protocol to add to the canonical rules

1. Before an action, read the current issue **and latest comments**, execution horizon, due gates, blockers, WIP and Agent label. Work only when all gates allow it.
2. Before a write, publish a `[Claude] Claiming: <plan, branch>` or `[ChatGPT] Claiming: <plan, branch>` comment, set the matching Agent label and status, and re-read to confirm one current owner. Do not remove unrelated labels.
3. The other operator must **HARD SKIP** a task with an active competing Agent label or claim, including when the task is NOW/AI Autonomous. Only bounded coordination comments may be written; no issue state/label/priority/assignee changes or overlapping branch/PR.
4. Race, stale revision, conflicting owner markers or ambiguous authority => **HOLD** and a concise coordination comment. Wojtek decides contested ownership or scope.
5. Use distinct branches and PRs, no changes to the other operator's work. Shared Android devices require the central broker with lease, provenance and trusted-safety gates.
6. Prefix messages with `[Claude]`, `[ChatGPT]`, `[Claude → ChatGPT]` or `[ChatGPT → Claude]`. Both connectors can appear in Linear under Wojtek's account; prefixes are coordination hints, not authenticated identities.
7. Collaboration is asynchronous: an issue comment cannot awaken an inactive Claude session. For a request, comment `[ChatGPT → Claude] ACTION REQUESTED`; Wojtek must then open a Claude session to read it. Acknowledgement is not proof of active execution.

## Canonical propagation plan

1. Increment `governance/CHATGPT_OPERATING_RULES.md` from v1.36 to v1.37 and add this multi-agent rule in the organizational model.
2. Add an entry for **Claude / Claude Code** in the **Systems & Direct-Access Registry**: separate active Claude session, Linear/GitHub as common evidence, no ChatGPT-native invocation, permissions scoped to the connected Claude account, no spending.
3. Add the hard-skip constraint for ChatGPT Runner and organizational discovery loops without changing their separate existing live-safety gates.
4. Record decision and evidence in Linear Company Decision Log and close ADL-960 only after canonical content is actually merged and verified.

## Boundaries

This proposal does not amend the canonical rules and must not be presented as an implemented hard-skip. It adds no live autonomy, payment authorization, permission escalation, production deploy, automatic Claude trigger, or right to merge the four ADL-958 PRs.
