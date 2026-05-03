---
name: new-collection
description: Scaffold a new Shopify collection for The Originea with French SEO title, description, handle and recommended products. Use when creating a new product category.
allowed-tools: Read
argument-hint: [collection name] [theme/season/occasion]
---

# New Collection Scaffold — The Originea

## Based on $ARGUMENTS, generate:

### 1. Collection Title (French, SEO-optimised)
- Include primary keyword
- Max 60 characters
- Evocative of Provence/artisanal

### 2. Handle (URL slug)
- Lowercase, hyphens only
- Include primary keyword
- No stop words if possible
- Example: `confettis-mariage-petales-secs`

### 3. Meta Description (French, 140-160 chars)
- Primary keyword in first 20 words
- Mention Provence or artisanal
- Include a soft CTA

### 4. Collection Description (HTML, French)
```html
<p><strong>[Hero statement]</strong></p>
<p>[2-3 sentences evoking Provence, season, or occasion]</p>
<p>[What makes The Originea products special — natural, no additives, artisanal]</p>
```

### 5. Recommended product tags to include in this collection
List 3-5 product tags that should auto-populate this collection via Shopify automated conditions.

### 6. Suggested internal linking
Which existing collections should link to this new one and vice versa.
