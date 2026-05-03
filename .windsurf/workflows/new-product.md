---
description: Scaffold a new product for The Originea with correct SKU format, French SEO description, and Shopify-ready structure. Use when adding a new product to the store.
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
