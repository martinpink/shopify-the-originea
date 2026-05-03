---
description: Stage all changes, write a proper commit message following conventional commits format, and push to current branch. Use after completing any feature or fix.
---

# Commit & Push — The Originea

## Step 1 — Check current status
```bash
git status
git diff --name-only
```

Show the user which files have changed.

## Step 2 — Check current branch
```bash
git branch --show-current
```

⚠️ If on `main` branch, warn:
> "You are on the main branch. Are you sure you want to commit directly to main? Type YES to continue or switch to a feature branch first."

## Step 3 — Generate commit message
Based on the changed files, write a commit message following this format:

```
type(scope): short description

- Detail 1
- Detail 2
```

Types:
- `feat` — new feature or content
- `fix` — bug fix
- `style` — CSS/design changes
- `content` — product descriptions, translations, copy
- `config` — settings, theme configuration
- `seo` — SEO improvements

Examples:
- `feat(product): add personalisation fields to confetti cone page`
- `fix(cart): correct free shipping threshold to 45€`
- `content(product): add French description for hydrangea petals`
- `seo(meta): update meta descriptions for citrus collection`

## Step 4 — Stage and commit
```bash
git add .
git commit -m "[generated message]"
```

## Step 5 — Push
```bash
git push origin $(git branch --show-current)
```

Confirm: ✅ Pushed to [branch name]
