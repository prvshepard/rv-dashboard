# PRVS Dashboard — Session Starter Prompt

> **Instructions for Roland:**
> Copy the text in the box below and paste it as your FIRST message at the start of every
> Claude session. This gives Claude its memory and tells it exactly what to do.
> You can add your task/question at the bottom of the paste.

---

## 📋 COPY THIS ENTIRE BLOCK:

```
You are continuing development on the PRVS Dashboard project (Patriots RV Services).
You have no memory of previous sessions, so you MUST do the following before anything else:

STEP 1 — Read your context file:
Read CLAUDE_CONTEXT.md from the workspace folder (rv-dashboard).
Primary path: /sessions/.../mnt/rv-dashboard/CLAUDE_CONTEXT.md (workspace folder)
Fallback if workspace unavailable: fetch via GitHub API — repo PatriotsRV/rv-dashboard, file CLAUDE_CONTEXT.md, branch main.
Read the ENTIRE file top to bottom before doing anything else.

STEP 2 — Confirm what you've read:
Tell me:
- Current version of index.html (must match File Inventory in CLAUDE_CONTEXT.md)
- Full Active TODO List read aloud, grouped by priority
- Any blocking issues or Roland-action items still pending

STEP 3 — Follow the Session Protocol:
CLAUDE_CONTEXT.md has a START OF SESSION CHECKLIST. Follow every step completely.

STEP 4 — Ask before starting:
After reading, ask: "Is there anything new to add or change before we start?"
Wait for Roland's answer before beginning any work.

STEP 5 — End of session commitment:
Before this session ends (context limits or Roland says stop), you MUST:
1. Run: bash scripts/backup.sh
2. Update CLAUDE_CONTEXT.md — TODO list, File Inventory, Session Log, Completed Work, Known Issues, Version History
3. git add all changed files
4. git commit and git push origin main
5. Confirm the push succeeded with the commit hash
Do NOT let the session end without this step completed and confirmed.

---

RULES for this session (non-negotiable):
- Always read CLAUDE_CONTEXT.md before any work — it is your only memory
- Always run bash scripts/backup.sh before every git push
- Always check the TODO list before starting new work
- Always use getSB() AND supabaseSession as auth guards (not accessToken) — check BOTH: !getSB() || !supabaseSession
- Always destructure { error } from Supabase writes and throw/alert if error exists
- Always write audit log entries for field changes: writeAuditLog(roId, [{field, oldValue, newValue}])
- Capture oldValue BEFORE mutating currentData — after mutation the old value is gone
- Use .maybeSingle() not .single() for any lookup where 0 rows is a valid result
- Parts request notes use type:'ro_status' with body prefix '🔩 PARTS REQUESTED:' — NEVER type:'parts_request'
- uploadDocument uses Supabase Storage only — do NOT revert to Google Drive
- Version bump index.html (comment + badge + console.log) with every release
- Commit and push to GitHub after every meaningful change
- If context is getting full, immediately run the End of Session Checklist before anything else

---
[ADD YOUR TASK OR QUESTION HERE]
```

---

## 💡 Tips

**For a quick bug fix session:**
Paste the block above, then add:
> "I found a bug: [describe it]. Please fix it."

**For a feature session:**
Paste the block above, then add:
> "Today I want to work on [GitHub Issue #X / feature name]. Let's plan it out and then build it."

**For a review session:**
Paste the block above, then add:
> "Before we build anything new, review the current state of index.html and tell me if there are any issues, inconsistencies, or technical debt I should know about."

**If Claude seems confused or off-track mid-session (RESET):**
> "Stop everything. Re-read CLAUDE_CONTEXT.md right now. Confirm the current index.html version and the full TODO list before you do anything else. Do not continue until you have confirmed both."

**To force a mid-session save (PAUSE):**
> "Pause what you're doing and save progress now. Run bash scripts/backup.sh, then update CLAUDE_CONTEXT.md with everything completed so far this session — TODO list, session log, any new gotchas — commit all changed files, and push to GitHub. Confirm the push with the commit hash. Then tell me exactly where we are and what's next before continuing."

**To end the session cleanly (STOP):**
> "Before we stop: run bash scripts/backup.sh, then run the End of Session Checklist from CLAUDE_CONTEXT.md. Update the TODO list, File Inventory, Session Log, Completed Work, Known Issues, and Version History as needed. Commit all changed files and push to GitHub. Do not end the session until the push is confirmed with a commit hash."

---

## 📍 Key Reference Info

| Item | Value |
|---|---|
| GitHub repo | PatriotsRV/rv-dashboard |
| Live URL | https://patriotsrv.github.io/rv-dashboard/ |
| Supabase project ref | axfejhudchdejoiwaetq |
| Context file (workspace) | `/mnt/rv-dashboard/CLAUDE_CONTEXT.md` |
| Context file (GitHub fallback) | `PatriotsRV/rv-dashboard` → `CLAUDE_CONTEXT.md` on `main` |
| Backup script | `bash scripts/backup.sh` (run before every push) |
| Current version | See CLAUDE_CONTEXT.md → File Inventory |
