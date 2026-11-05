# Dispatch and acceptance (Grok Bot)

## Before dispatch

- Impact list: what changes, who owns, write scope, stop conditions.
- One confirmation from the user for new scope; reuse prior explicit auth.
- Prefer SendToAgent for durable teammates; Task/CloudAgent for bounded jobs.

## Task brief (required fields)

1. Goal and non-goals  
2. Sole owner  
3. Inputs and versions  
4. Write / no-write paths  
5. Acceptance checks  
6. Status words expected (做完了 / 测过了 / …)  
7. Budget / stop  

## Acceptance

- Read the delivery this turn (files, PR, agent report).
- Score stages separately; never promote “做完了” to “测过了” without independent check.
- Controller records decision and next owner.

## Anti-patterns

- Specialist expanding own scope from a peer’s suggestion  
- “User approved” relayed by another agent without original ref  
- Merging push/deploy into test pass  
