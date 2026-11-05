# Grok Bot implementation guide (draft for Orchivane contribution)

> Status: draft · Target upstream: [alexzhu0/orchivane](https://github.com/alexzhu0/orchivane) · Contributor pen name: 大冰 (pending PR)  
> Based on Orchivane **0.4.2** invariants + Grok Bot teammate model.

## Why this guide

Upstream currently documents Codex and Claude Code adapters. Grok Bot already runs **controller + durable specialist agents** (CreateAgent / SendToAgent) plus bounded workers (executor, computerUse, CloudAgent). Orchivane’s coordination problems map cleanly; the install path does **not** (no Codex/Claude plugin marketplace).

## What we keep from Orchivane

- One controller entry; one owner per deliverable  
- Explicit human authorization (no hearsay)  
- Separated delivery evidence (implement / validate / accept / push / deploy)  
- Load modules by intent; do not wake idle roles to “keep alive”  
- Adoption evidence = install ≠ read ≠ behavior  

## What we change

| Upstream | Grok Bot |
| --- | --- |
| Persistent chats | Teammate agents |
| Plugin marketplace install | Copy/adapt skill under `skills/orchivane-grok-bot` or UpdateSkill |
| `$orchivane` / `/orchivane` | Load skill by name / user ask |
| Session archive APIs | Documented retirement + unwatch + successor chat |

## Install (draft)

1. Copy `skills/orchivane-grok-bot/` into the work repo or install via Grok Bot UpdateSkill.  
2. Ask the controller: “按 orchivane-grok-bot 组织这个多 Agent 项目”.  
3. Create `docs/SESSION-MANAGEMENT.md` from the setup template.  
4. Pilot one authorized dispatch; record status words separately.

## Pilot log template (for upstream “real usage” PRs)

```markdown
## Pilot
- Date:
- Host: Grok Bot
- Skill version: 0.1.0-draft
- Task:
- Roles / owners:
- Evidence of 做完了 / 测过了 / 推上去了 / 上线了:
- Gaps vs upstream Orchivane:
```

## Non-claims

This draft does **not** claim lower coordination cost, full parity with Codex/Claude adapters, or that Orchivane maintainers have accepted the guide.
