---
name: sync-check
description: Compare dev theme vs live theme to show what files are different before deploying to production. Use before /push-live to verify what will change.
allowed-tools: Bash(git *), Bash(shopify *), Bash(diff *)
---

# Sync Check — Dev vs Live Theme

## Step 1 — Pull both themes locally
```bash
# Pull live theme to a temp folder
mkdir -p /tmp/theme-live
shopify theme pull --theme 196125032712 --path /tmp/theme-live

# Pull dev theme to a temp folder  
mkdir -p /tmp/theme-dev
shopify theme pull --theme 196494786824 --path /tmp/theme-dev
```

## Step 2 — Compare
```bash
diff -rq --exclude="*.json" /tmp/theme-live /tmp/theme-dev
```

## Step 3 — Report
List all files that differ between dev and live. For each changed file show:
- File path
- Whether it exists only in dev (new) or only in live (deleted) or in both (modified)

## Step 4 — Cleanup
```bash
rm -rf /tmp/theme-live /tmp/theme-dev
```

## Output
Summarise: "X files will change if you run /push-live" and list them clearly.
