---
name: new-product
description: Scaffold a new product for The Originea with correct SKU format, French SEO description, and Shopify-ready structure. Use when adding a new product to the store.
allowed-tools: Read, Write
argument-hint: [product-name] [category] [variants]
---

# New Product Scaffold for The Originea

## SKU Format
```
[CATEGORY]-[PRODUCTCODE]-[VARIANT]

Categories:
AGR = Agrumes (citrus)
CONF = Confettis / Pétales
BOT = Botaniques & herbes
FIG = Figues & fruits secs
COFF = Coffrets cadeaux
```

Examples:
- `AGR-CITRON-40G`
- `CONF-PETALESHORT-1L`
- `BOT-LAVANDE-50G`

## Based on $ARGUMENTS, generate:

1. **Product title** (French, SEO-optimised)
2. **SKU** for each variant using the format above
3. **Meta description** (max 160 chars, French, includes key terms)
4. **HTML product description** matching The Originea template:

```html
<p><strong>[Hero statement — naturelle, biodégradable, artisanale]</strong></p>
<p>[2-sentence brand description mentioning Provence]</p>
<hr>
<p><strong>🌸 [Section title]</strong></p>
<ul>
  <li><strong>Variant 1:</strong> [description]</li>
</ul>
<hr>
<p><strong>✦ Ce qui le rend unique</strong></p>
<ul>
  <li>✔ <strong>100% naturel · Sans additifs</strong></li>
  <li>✔ <strong>Artisanal · Fait en Provence</strong></li>
</ul>
<hr>
<p><strong>🚚 Livraison</strong> — Livraison offerte dès 45€ en France, 65€ en Europe.</p>
```

5. **Tags** to add in Shopify (include `personnalisable` if applicable)
6. **Collections** it should belong to
7. **Product type:** always set to the relevant type (e.g. `Confettis mariage`, `Fruits secs`, `Botaniques`)
8. **Vendor:** always `The Originea`
9. **Category:** use the correct Shopify taxonomy (e.g. `gid://shopify/TaxonomyCategory/rc-3` = Wedding Ceremony Supplies for confetti/petal products)
10. **Sales channels:** always publish to ALL 6 channels:
    - Online Store (`gid://shopify/Publication/322003239176`)
    - Point of Sale (`gid://shopify/Publication/322003271944`)
    - Shop (`gid://shopify/Publication/322003337480`)
    - Inbox (`gid://shopify/Publication/322130510088`)
    - Google & YouTube (`gid://shopify/Publication/323019604232`)
    - The Originea Headless (`gid://shopify/Publication/326695813384`)
11. **Collections to join:**
    - All Collection — TheOriginea (`gid://shopify/Collection/567848730888`) — always
    - Celebrate Me – Weddings & events (`gid://shopify/Collection/574620762376`) — for confetti/petal/wedding products
12. **SEO standard:**
    - Title: `[Product name short] | Originea` (max 70 chars)
    - Description: max 160 chars, French, mentions key terms (naturel, biodégradable, artisanal, Provence)

## ⚠️ IMPORTANT RULES

- **NEVER include prices in the "Choisissez votre format" section.** List only the volume/size and a short description. Prices are shown automatically by Shopify via variants — do not repeat them in the description.

- **SKU format for variants:** The 0.5L variant always uses the base SKU only (no size suffix) — this is the Etsy sync workaround (Etsy supports only one SKU per product). All other variants get the size suffix appended.

Example for a product with code `CONF-HORTBLEU`:
```
0.5L  → CONF-HORTBLEU        ← no suffix (Etsy default SKU)
1L    → CONF-HORTBLEU-1L
2L    → CONF-HORTBLEU-2L
5L    → CONF-HORTBLEU-5L
8L    → CONF-HORTBLEU-8L
24L   → CONF-HORTBLEU-24L
```

Example of CORRECT format section:
```html
<p><strong>Choisissez votre format</strong></p>
<ul>
  <li><strong>0.5L :</strong> Un aperçu délicat — idéal pour une décoration de table intime.</li>
  <li><strong>1L :</strong> Pour une petite cérémonie ou décoration de table poétique.</li>
  <li><strong>2L :</strong> Pour 10 à 20 invités — mariage intime ou événement privé.</li>
  <li><strong>5L :</strong> Pour 30 à 50 invités — le format polyvalent de la cérémonie.</li>
</ul>
```
