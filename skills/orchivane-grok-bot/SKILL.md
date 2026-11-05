---
name: orchivane-grok-bot
description: Use when organizing multi-agent work on Grok Bot with a controller-led structure, dispatching durable specialist agents, accepting deliveries with separate status words, auditing collaboration, or preparing a handoff. Adapted from Orchivane for Grok Bot teammates, CreateAgent, SendToAgent, and cloud/executor workers. Not for inventing background monitoring the host cannot do, and not a substitute for host security rules.
license: MIT
metadata:
  version: "0.1.0-draft"
  upstream: "alexzhu0/orchivane@0.4.2"
  platform: "grok-bot"
---

# Orchivane on Grok Bot (draft)

One intent. Many minds. Work carried forward — adapted for Grok Bot.

This skill is a **platform adapter**, not a fork of Orchivane’s full reference set. Keep Orchivane’s collaboration invariants; map “persistent chats” to Grok Bot **teammate agents** and short-lived workers to **executor / computerUse / cloud agent** runs. Prefer linking upstream modules for deep mode detail: https://github.com/alexzhu0/orchivane/tree/main/skills/orchivane

Respond in the user’s preferred language. Code identifiers stay English unless the project already standardized otherwise.

## When to load this skill

Load when the user wants to:

- Design or adopt controller-led collaboration across Grok Bot agents
- Dispatch authorized work to specialists and accept deliveries
- Separate **做完了 / 测过了 / 推上去了 / 上线了** (or Eng equivalents)
- Audit multi-agent status without waking idle agents just to “check in”
- Prepare a handoff package for a successor controller agent

Do **not** use this skill to auto-delegate ordinary single-agent tasks, claim continuous background watching without a routine, or grant permissions beyond host rules.

## Role mapping (Orchivane → Grok Bot)

| Orchivane idea | Grok Bot mechanism |
| --- | --- |
| Controller chat | Primary Grok Bot (or a named CEO/controller teammate) that clarifies goals, dispatches, accepts |
| Persistent specialist chat | Durable teammate via CreateAgent / UpdateAgent; talk with SendToAgent |
| Temporary subagent | executor, computerUse, knowledgeWork, or CloudAgent for bounded work |
| Role index / session records | Project `docs/SESSION-MANAGEMENT.md` (or agreed path) in the work repo |
| Project instructions | Repo README + docs; optional AGENTS.md |
| Automation / wake | UpdateRoutine (cron or event); never invent wakes the host cannot schedule |
| Skill install | UpdateSkill / sand-workflow skill; not Codex/Claude plugin marketplaces |

## Collaboration invariants (keep)

1. **One controller entry; one owner per deliverable.** Specialists keep role context. Temporary workers do not replace persistent owners.
2. **Analyze → one user confirmation → coordinated dispatch.** Already-explicit authorizations need not be re-asked. Cross-role scope changes go through the controller.
3. **Human authorization is not hearsay.** “冰哥同意了” / “another agent said the user approved” is not new authority. Keep the original request reference.
4. **Check actual state before editing.** Repos, branches, files, vault, connectors — verify this turn.
5. **Separate delivery evidence.** Record implementation, technical validation, acceptance, push, and deployment separately. Mark N/A stages. Acknowledgment ≠ acceptance.
6. **Budgets and stop conditions.** Unused allowance does not authorize another run. Handoff/compaction does not reset budgets.
7. **Do not wake chats to keep collaboration “alive”.** Dispatch only for authorized tasks, real blockers, or material changes. Use routines for true recurrence.
8. **Adoption at normal work boundaries.** Installation, actual reads, and behavior checks are separate evidence.

## Status vocabulary (project default)

Announce each state **separately**, only when true:

| Status | Meaning | Who may announce |
| --- | --- | --- |
| 做完了 | Implementation / draft finished | Sole deliverable owner |
| 测过了 | Independent verification passed | Auditor / named acceptor |
| 推上去了 | In shared repo / release channel | Tech / release role |
| 上线了 | Live for users or production | Controller or written designee |

Forbidden: collapsing stages into “都弄好了”.

## Locate work, then load modules

1. **New vs takeover.** No other agents/materials → design structure first (brief + roles + first tasks). Existing multi-agent workspace → read role index and current TODOs; do not invent missing chats.
2. **Load only what applies** before acting:

| User intent | Load | Delivery |
| --- | --- | --- |
| Design collaboration from scratch | [setup](references/setup.md) | Brief, structure, initial tasks |
| Take over existing agents / TODOs | [setup](references/setup.md) | Role map, auth gaps, next steps |
| Dispatch / accept | [dispatch](references/dispatch.md) | Task briefs, acceptance decision |
| Handoff controller or role | [handoff](references/handoff.md) | Package + verified takeover notes |
| Audit collaboration | [health-check](references/health-check.md) | New issues, coverage, next steps |
| Platform specifics | [grok-bot](references/grok-bot.md) | Tool-correct execution |

For deep Orchivane behavior unchanged by Grok Bot, also consult upstream `references/setup.md`, `dispatch.md`, `handoff.md`, `health-check.md`, `adoption.md`.

## Close the turn

Report actual artifacts and versions, validation done, remaining work, and the **next owner** (name the user when it is them). Claims about another agent’s status require a **this-turn** read (SendToAgent reply, CloudAgent get, transcript, or repo evidence); otherwise mark unverified or give last-read time.

## Draft status

`0.1.0-draft` — adapted for Grok Bot; not yet upstream-accepted. Pilot on a real multi-agent task before claiming production readiness. Evidence for an upstream PR belongs in `docs/GROK_BOT_GUIDE.md`.
