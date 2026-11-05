# Grok Bot host adapter

## Tools (conceptual)

- **Teammates:** CreateAgent, UpdateAgent, SendToAgent, ListSections  
- **Bounded workers:** Task (executor / computerUse / knowledgeWork), CloudAgent for repos  
- **Durable recipes:** UpdateSkill; invoke via Skill / sand-workflow  
- **Recurrence:** UpdateRoutine — only real schedules/events  
- **Source control:** cursor-github / cursor-origin; never clone for investigation  

## Differences vs Codex / Claude Code

| Topic | Codex / Claude Code | Grok Bot |
| --- | --- | --- |
| Persistent specialists | Extra chats/sessions | Separate teammate agents |
| Plugin install | marketplace / plugin CLI | Skill files + UpdateSkill |
| `$orchivane` trigger | Host skill syntax | Ask to load orchivane-grok-bot / @ skill |
| Native session tools | Create/message/archive chats | SendToAgent + optional new agents |
| Background | Limited native | Routines + watched cloud agents |

## Safety

Host security, Auto-review, vault, and send-on-behalf rules always win over this skill. This skill grants no extra permissions.

## Pilot suggestion

Use Codex 第 6 版 gate templates or a small REA dispatch as the first real pilot; keep logs for upstream contribution evidence.
