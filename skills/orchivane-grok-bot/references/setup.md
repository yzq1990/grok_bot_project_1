# Setup and records (Grok Bot)

## New project

1. Clarify goal, constraints, success criteria with the user.
2. Recommend whether to stay in one agent or split persistent teammates.
3. Propose role names, sole owners per deliverable, and first authorized tasks.
4. Write `docs/SESSION-MANAGEMENT.md` (or agreed path) with: controller id, specialists, owners, open TODOs, status vocabulary.
5. Create teammates only after explicit authorization for create/send actions that cost new agents.

## Takeover

1. Inventory existing Grok Bot teammates (titles/roles) and any role index in the repo.
2. Map each deliverable to exactly one owner; flag duplicates and orphans.
3. List open authorizations vs hearsay; do not widen scope.
4. Report next steps; do not dispatch until authorized.

## Minimal role index template

```markdown
# SESSION-MANAGEMENT

Controller: <agent name / id>
Updated: <ISO date>

## Roles
| Role | Agent | Owns | Notes |
|------|-------|------|-------|

## Open TODOs
| ID | Owner | Status word | Blocker |
|----|-------|-------------|---------|

## Auth log
| Ref | Who | What | Date |
|-----|-----|------|------|
```
