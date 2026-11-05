# Handoff (Grok Bot)

## Package contents

- Goal and current phase  
- Role index + open TODOs with status words  
- Auth log references  
- Artifacts and unverified gaps  
- Automation/routines that must transfer or pause  
- Successor first checks  

## Sequence

1. Prepare package; do not create/archive yet if user only asked to prepare.  
2. Create or brief successor controller only when authorized.  
3. Verify successor can read the same sources.  
4. Transfer routines ownership notes; pause what must not double-fire.  
5. Archive or retire old controller only after preservation checks.  

Grok Bot has no Codex-style session archive API — “archive” means: document retirement, stop watching obsolete cloud agents, and point users to the successor chat.
