---
description: Push current changes to the dev theme only (ID 196494786824). Use when you want to deploy changes to the unpublished Dev - Personalisation theme for testing. Never pushes to production.
---

# Push to Dev Theme

## Safety Check
First verify we are on the correct branch:
```bash
git branch --show-current
```

If the current branch is `main`, STOP and warn the user:
> ⚠️ You are on the `main` branch. Switch to `feature/personalisation` or another feature branch before pushing to dev.

## Push to Dev
If on a feature branch, proceed:
```bash
shopify theme push --theme 196494786824
```

Confirm success and remind the user they can preview at:
https://originae-2.myshopify.com/?preview_theme_id=196494786824
