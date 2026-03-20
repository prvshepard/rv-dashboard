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
Read the file CLAUDE_CONTEXT.md from the workspace folder. It is located at:
/sessions/.../mnt/rv-dashboard/CLAUDE_CONTEXT.md
(or read it via GitHub: PatriotsRV/rv-dashboard, file path: CLAUDE_CONTEXT.md)

STEP 2 — Confirm what you've read:
Tell me:
- Current version of index.html
- Top 3 items on the Active TODO List
- Any open/blocking known issues

STEP 3 — Follow the Session Protocol:
The CLAUDE_CONTEXT.md file has a START OF SESSION CHECKLIST. Follow it completely.

STEP 4 — End of session commitment:
Before this session ends (whether due to context limits or I say we're done),
you MUST update CLAUDE_CONTEXT.md with everything that was done, commit it,
and push it to GitHub. Do NOT let the session end without this step.

RULES for this session:
- Always check the TODO list before starting new work
- Always use getSB() (not accessToken) as the guard for Supabase operations
- Always destructure { error } from Supabase writes and throw if error exists
- Always write audit log entries for field changes (use writeAuditLog(roId, [{field, oldValue, newValue}]))
- Capture oldValue BEFORE mutating currentData, or the old value is lost
- Use .maybeSingle() not .single() for any lookup where 0 rows is valid
- Version bump index.html (comment + badge + console.log) with every release
- Commit and push to GitHub after every meaningful change

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

**If Claude seems confused or off-track:**
> "Stop. Re-read CLAUDE_CONTEXT.md. Confirm the current version and the top TODO items before continuing."

**To force an end-of-session save at any time:**
> "Please run the End of Session Checklist from CLAUDE_CONTEXT.md right now and push everything to GitHub."

---

## 📍 Key Reference Info (for quick copy/paste)

| Item | Value |
|---|---|
| GitHub repo | PatriotsRV/rv-dashboard |
| Live URL | https://patriotsrv.github.io/rv-dashboard/ |
| Supabase project | axfejhudchdejoiwaetq |
| Context file path | `/mnt/rv-dashboard/CLAUDE_CONTEXT.md` |
| Main file | `index.html` (currently v1.266) |
