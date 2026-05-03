---
name: klaviyo-email
description: Generate HTML email content ready to paste into Klaviyo. Correct shipping thresholds, The Originea brand voice, French. Use for campaigns, flows, or one-off emails.
allowed-tools: Read
argument-hint: [email type] [topic/offer]
---

# Klaviyo Email Generator — The Originea

## Key Constants (always use these)
- **Free shipping France:** €45
- **Free shipping Europe:** €65
- **Sender name:** The Originea
- **Sender email:** contact@theoriginea.com
- **Store URL:** https://theoriginea.com
- **Brand colours:** Dark (#1a1a1a background), Cream (#f5f0e8), Gold accent
- **Unsubscribe:** `{{ unsubscribe_url }}`
- **First name:** `{{ first_name | default:"" }}`

## Liquid Variables to use
```
{{ first_name | default:"" }}           — Customer first name
{{ event.extra.order_number }}          — Order number
{{ event.extra.order_status_url }}      — Order tracking URL
{{ event.extra.checkout_url }}          — Checkout recovery URL
```

## Based on $ARGUMENTS, generate:

### Subject line (French, max 60 chars)
### Preview text (French, max 90 chars)

### HTML Email Body
Follow this structure:
```html
<!-- Header with logo -->
<div style="background:#1a1a1a; text-align:center; padding:30px;">
  <img src="[LOGO_URL]" alt="The Originea" width="200">
</div>

<!-- Body -->
<div style="background:#ffffff; padding:40px; font-family:Georgia,serif;">
  <h1 style="text-align:center;">[Headline in French]</h1>
  <p>Bonjour {{ first_name | default:"" }},</p>
  [Body content]
  <a href="[CTA_URL]" style="background:#1a1a1a; color:#ffffff; padding:14px 28px; text-decoration:none; display:inline-block;">[CTA Button French]</a>
</div>

<!-- Shipping banner -->
<div style="background:#f5f0e8; text-align:center; padding:20px;">
  <p><strong>LIVRAISON OFFERTE DÈS 45€ EN FRANCE — 65€ EN EUROPE</strong></p>
</div>

<!-- Footer -->
<div style="background:#1a1a1a; color:#ffffff; text-align:center; padding:20px;">
  <p>Vous ne souhaitez plus recevoir ces emails ? <a href="{{ unsubscribe_url }}" style="color:#ffffff;">Se désabonner</a></p>
  <p>The Originea — 500 Route de Fiancey, 26250 Livron-sur-Drôme, France</p>
</div>
```
