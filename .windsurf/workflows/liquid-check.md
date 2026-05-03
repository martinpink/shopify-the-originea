---
description: Review Liquid code for errors, missing fallbacks, performance issues, and Shopify best practices. Use before pushing any template changes.
---

# Liquid Code Review — The Originea

## Review $ARGUMENTS for:

### 1. Syntax Errors
- [ ] All `{%` tags are closed with `%}`
- [ ] All `{{` variables are closed with `}}`
- [ ] All `if/unless` blocks have `endif`
- [ ] All `for` loops have `endfor`
- [ ] All `capture` blocks have `endcapture`
- [ ] No unclosed `case/when` statements

### 2. Missing Fallbacks
- [ ] All variables have `| default:` fallbacks where appropriate
  - Example: `{{ product.title | default: 'Produit' }}`
  - Example: `{{ first_name | default: "" }}`
- [ ] Image `src` attributes use `| img_url` filter
- [ ] Money values use `| money` filter

### 3. Performance
- [ ] No `for` loops inside other `for` loops (nested loops are slow)
- [ ] `paginate` used for large collections (not just `for product in collection.products`)
- [ ] Images use `loading="lazy"` where appropriate
- [ ] No inline `<style>` tags — use `{%- style -%}` instead

### 4. Shopify Best Practices
- [ ] Uses `{%- -%}` (whitespace control) for cleaner HTML output
- [ ] `assign` used instead of `capture` for simple strings
- [ ] `unless` used instead of `if not` where appropriate
- [ ] Translation strings use `{{ 'key' | t }}` not hardcoded text

### 5. The Originea Specific
- [ ] Customer-facing text is in French
- [ ] Shipping threshold matches: 45€ France / 65€ Europe
- [ ] Brand name always "The Originea" (not "Originea" or "TheOriginea")

## Output
List all issues found with line numbers.
Rate each: 🔴 Will break / 🟡 Could cause issues / 🟢 Best practice suggestion.
