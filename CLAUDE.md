# The Originea — Shopify Theme Development

## Project Overview
Artisanal dried fruit & botanical products store based in Provence, France.
- **Store URL:** https://theoriginea.com
- **Shopify store:** originae-2.myshopify.com
- **Local path:** `/Users/D060396/App Development/Shopify-Originea/`

---

## ⚠️ CRITICAL: Theme Safety Rules

| Environment | Theme ID | Git Branch | Status |
|---|---|---|---|
| Production (LIVE) | `196125032712` | `main` | Never touch directly |
| Dev (Personalisation) | `196494786824` | `feature/personalisation` | Safe to push |

**NEVER push to theme `196125032712` unless explicitly told to deploy to production.**
**ALWAYS confirm which branch is active before any theme push.**

### Safe push command (dev only):
```bash
shopify theme push --theme 196494786824
```

### Production deploy (only when explicitly confirmed):
```bash
shopify theme push --theme 196125032712
```

---

## Branch Rules
- All new features → `feature/` branches
- `main` branch = production only
- Current active feature: `feature/personalisation`
- Deploy to live only via PR from feature branch → main

---

## Tech Stack
- **Platform:** Shopify (Liquid templating)
- **Theme:** Custom (based on Dawn)
- **Languages:** Liquid, CSS, JavaScript
- **CLI:** Shopify CLI (`shopify theme push/pull/dev`)
- **Editor:** Windsurf + Claude Code

---

## Business Context

### Products & SKU Format
```
CONF-PETALESHORT-1L    (confetti cones - hydrangea petals)
AGR-CITRON-40G         (dried citrus)
```

### Key product lines:
- Fruits séchés artisanaux (agrumes, figues, etc.)
- Confettis mariage (pétales d'hortensia, roses)
- Coffrets cadeaux personnalisés (in development)

### Personalisable products (tagged: `personnalisable`):
- Confetti cones — ribbon colour + custom name tag
- Fruit name tags — custom names + dates

### Personalisation fields needed:
- Prénom 1 / Prénom 2
- Date (e.g. "30 Mai 2026")
- Message (optional)
- Ribbon colour (variant)

---

## Shipping & Pricing
- Free shipping: **€45+ France / €65+ Europe**
- Primary markets: France, Belgium, Switzerland
- Carrier: Mondial Relay (point relais), Colissimo

---

## Email & Communication
- **Default sender:** contact@theoriginea.com
- **Orders:** orders@theoriginea.com
- **Support:** support@theoriginea.com
- **Email platform:** Klaviyo (sending domain: send.theoriginea.com)
- **Discount codes:** ORIGINEA5 (5% — newsletter welcome), ORIGINEA10 (10% — thank you card), MERCI10 (15% — VIP outreach)

---

## Key Files to Know
```
layout/theme.liquid          — Global layout, title tag logic
sections/main-product.liquid — Product page (personalisation fields go here)
sections/main-cart.liquid    — Cart page
assets/custom.css            — Custom styles
locales/fr.default.json      — French translations
```

---

## Common Commands
```bash
# Pull latest from live theme
shopify theme pull --theme 196125032712

# Push to dev theme only
shopify theme push --theme 196494786824

# Start local dev server (dev theme)
shopify theme dev --theme 196494786824

# Push specific files only
shopify theme push --theme 196494786824 --only sections/main-product.liquid

# Check current git branch
git branch
```

---

## Coding Standards
- All customer-facing text in **French**
- Use Liquid variables for dynamic content (never hardcode prices or names)
- Line item properties for personalisation (not metafields)
- Test on mobile first (majority of traffic is mobile)
- Never remove existing CSS classes — add new ones
- Comment any Liquid logic that isn't obvious
