---
description: Add personalisation fields (names, date, message, ribbon colour) to a Shopify product template using line item properties. Use for confetti cones and fruit tag products tagged as personnalisable.
---

# Add Personalisation Fields — The Originea

## Overview
Adds customer-facing input fields to the product page using Shopify line item properties.
No app required — pure Liquid + HTML.
Only shows on products tagged `personnalisable`.

## Target file
`sections/main-product.liquid` (or file specified in $ARGUMENTS)

## Step 1 — Read the current file
Read the target file and find the `<form>` tag that wraps the Add to Cart button.

## Step 2 — Add personalisation block BEFORE the Add to Cart button

Insert this Liquid/HTML block:

```liquid
{%- if product.tags contains 'personnalisable' -%}
<div class="personalisation-fields" style="margin: 20px 0;">
  <h3 style="font-family: Georgia, serif; margin-bottom: 16px;">✦ Personnalisation</h3>

  <div class="field" style="margin-bottom: 12px;">
    <label for="prenom1" style="display:block; margin-bottom:4px; font-weight:bold;">
      Prénom 1 <span style="color:red;">*</span>
    </label>
    <input
      type="text"
      id="prenom1"
      name="properties[Prénom 1]"
      placeholder="Ex: Laetitia"
      required
      style="width:100%; padding:10px; border:1px solid #ccc; border-radius:4px;"
    >
  </div>

  <div class="field" style="margin-bottom: 12px;">
    <label for="prenom2" style="display:block; margin-bottom:4px; font-weight:bold;">
      Prénom 2
    </label>
    <input
      type="text"
      id="prenom2"
      name="properties[Prénom 2]"
      placeholder="Ex: Olivier"
      style="width:100%; padding:10px; border:1px solid #ccc; border-radius:4px;"
    >
  </div>

  <div class="field" style="margin-bottom: 12px;">
    <label for="date-evenement" style="display:block; margin-bottom:4px; font-weight:bold;">
      Date de l'événement
    </label>
    <input
      type="text"
      id="date-evenement"
      name="properties[Date]"
      placeholder="Ex: 30 Mai 2026"
      style="width:100%; padding:10px; border:1px solid #ccc; border-radius:4px;"
    >
  </div>

  <div class="field" style="margin-bottom: 12px;">
    <label for="message" style="display:block; margin-bottom:4px; font-weight:bold;">
      Message personnalisé (optionnel)
    </label>
    <textarea
      id="message"
      name="properties[Message]"
      placeholder="Ex: Avec tout notre amour..."
      rows="3"
      style="width:100%; padding:10px; border:1px solid #ccc; border-radius:4px;"
    ></textarea>
  </div>

  <p style="font-size:0.85em; color:#666; margin-top:8px;">
    🌿 Ces informations apparaîtront sur votre étiquette personnalisée.
  </p>
</div>
{%- endif -%}
```

## Step 3 — Verify
After inserting, confirm:
- The block is inside the `<form>` tag
- It appears before the Add to Cart button
- The `if product.tags contains 'personnalisable'` condition is in place

## Step 4 — Push to dev
Run `/push-dev` to test on the dev theme before going live.

## Notes
- Line item properties (`name="properties[X]"`) automatically appear in Shopify orders
- No database or metafield setup needed
- Ribbon colour is handled via product variants, not line item properties
