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

**SKU variant rule (Etsy sync workaround):**
Etsy supports only one SKU per product. The 0.5L variant always uses the base SKU with NO size suffix — all other variants get the suffix appended:
```
0.5L  → CONF-HORTBLEU        ← no suffix (Etsy default SKU)
1L    → CONF-HORTBLEU-1L
2L    → CONF-HORTBLEU-2L
5L    → CONF-HORTBLEU-5L
8L    → CONF-HORTBLEU-8L
24L   → CONF-HORTBLEU-24L
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

## Product Setup Standards (apply to every new product)

### Sales Channels — always publish to ALL 6:
| Channel | Publication ID |
|---|---|
| Online Store | `gid://shopify/Publication/322003239176` |
| Point of Sale | `gid://shopify/Publication/322003271944` |
| Shop | `gid://shopify/Publication/322003337480` |
| Inbox | `gid://shopify/Publication/322130510088` |
| Google & YouTube | `gid://shopify/Publication/323019604232` |
| The Originea Headless | `gid://shopify/Publication/326695813384` |

### Collections — always add:
| Collection | ID |
|---|---|
| All Collection — TheOriginea | `gid://shopify/Collection/567848730888` |
| Celebrate Me – Weddings & events | `gid://shopify/Collection/574620762376` (confetti/petal/wedding products) |

### Category (Shopify Taxonomy):
- Confetti/petal/wedding products → `gid://shopify/TaxonomyCategory/rc-3` (Wedding Ceremony Supplies)

### Product Type examples:
- `Confettis mariage`
- `Fruits secs`
- `Botaniques`

### Vendor: always `The Originea`

### SEO Standard:
- **Title:** `[Short product name] | Originea` (max 70 chars)
- **Description:** max 160 chars, French, include: naturel, biodégradable, artisanal, Provence

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
- **Discount codes:** ORIGINEA10 (10% — thank you card), MERCI10 (15% — VIP outreach)

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
