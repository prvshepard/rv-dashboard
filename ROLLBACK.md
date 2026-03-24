# PRVS Dashboard — Emergency Rollback Guide

Use this guide if the dashboard is broken and you need to restore a working version immediately.
**You do not need Claude to do this.**

---

## Step 1 — Open Terminal

**Mac:** Press `Cmd + Space` → type `Terminal` → hit Enter

**Windows:** Press `Windows key` → type `PowerShell` → hit Enter

---

## Step 2 — Navigate to the Dashboard Folder

```
cd ~/Documents/rv-dashboard
```

If that doesn't work, try:

```
cd ~/Desktop/rv-dashboard
```

You'll know it worked when the prompt shows `rv-dashboard` in it.

---

## Step 3 — Run the Rollback Command

Pick the version you want to restore:

| Version | What's in it | Command |
|---------|-------------|---------|
| v1.285 | Four-state parts chips (Estimate, Sourcing, Outstanding, Received) + Estimate toggle | `git reset --hard v1.285 && git push --force` |
| v1.284 | Three-state parts chips (Sourcing, Outstanding, Received) | `git reset --hard c2c0746 && git push --force` |

Type the command exactly, hit Enter, and wait for it to say `main -> main`. That means it's done.

---

## Step 4 — Hard Refresh the Dashboard in the Browser

**Mac:** `Cmd + Shift + R`

**Windows:** `Ctrl + Shift + R`

This forces the browser to reload the restored version instead of showing a cached copy.

---

## Where to Find All Available Versions

Go to: **https://github.com/PatriotsRV/rv-dashboard/releases**

Every tagged release is listed there with notes on what it contains.
The tag name (e.g. `v1.285`) is what you put after `--hard` in the rollback command.

---

## Still Stuck?

Start a new Claude session in Cowork and say:

> *"Roll back the dashboard to v1.285"*

Claude can do it in about 30 seconds.

---

## Important: Preventing Future Conflicts

**Do not push changes directly to GitHub while a Claude session is active.**
If you need to make a change or restore a backup, either:
- Wait until the Claude session is finished, or
- Tell Claude at the **start** of the next session before any files are touched — Claude will sync up first with one command

Direct pushes during an active session cause a "diverged branch" which requires recovery work and can extend outages.
