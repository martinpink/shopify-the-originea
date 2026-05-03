---
name: push-live
description: Push changes to the LIVE production theme (ID 196125032712). Requires explicit user confirmation. Only use when feature is fully tested and approved.
allowed-tools: Bash(git *), Bash(shopify *)
---

# Push to Live Production Theme

## Step 1 — Branch Check
```bash
git branch --show-current
```

If on a `feature/` branch, STOP and warn:
> ⚠️ You are on a feature branch. You should merge to `main` via PR before pushing to production. Do you want to continue anyway? Type YES to override.

If on `main` branch, proceed to Step 2.

## Step 2 — Confirmation
Ask the user:
> "You are about to push to the LIVE theme (196125032712) at theoriginea.com. Customers will see changes immediately. Are you sure? Type YES to confirm."

Only proceed if the user explicitly types YES.

## Step 3 — Show Changed Files
```bash
git diff --name-only HEAD
```

Show the list of changed files so the user knows exactly what will go live.

## Step 4 — Deploy to Production
```bash
shopify theme push --theme 196125032712
```

After successful push:
> ✅ Live theme updated. Verify at https://theoriginea.com
