---
name: "shopify-spain-store"
description: "Use when building or editing Alvaro's Shopify store for Spain (Salvia Madrid, Impulse theme): theme sections, page copy, product descriptions, conversion audits, and legal or compliance checks."
---

# Shopify store for Spain

## Language and tone
- All customer-facing text in Spanish from Spain (castellano). Use "tú" in copy and "vosotros" for plural; euros written like 39,95 €.
- Warm, simple and benefit-first. Real storytelling only: no invented founders, years in business, awards or press.

## Mobile first (most customers buy on their phone)
- Design and check every change at 375 px wide first, then desktop.
- Sticky header; tap targets at least 44 px; no text below 14 px.
- Hero: a separate 9:16 mobile image (`image_mobile` in the Impulse slideshow).
- Product rows swipe sideways on mobile; add-to-cart visible without much scrolling.
- Compress images; lazy-load everything below the fold.

## Coding rules
- Online Store 2.0 sections with a full `{% schema %}` and presets.
- Vanilla JS only, no jQuery or new libraries. Accessible: aria labels, alt text, keyboard focus.
- Every piece of text editable in the theme editor.
- Prefer own code over paid apps. State the cost of any app before suggesting it.
- Edit only the unpublished theme through themeFilesUpsert; the live theme is blocked.
- Range settings must respect their step (e.g. slideshow overlay_opacity step 2).
- Images uploaded to Files are referenced as `shopify://shop_images/<filename>`.

## Conversion audit checklist (homepage, product page, landing)
1. Above the fold: what is sold, for whom, and why buy here, readable in 3 seconds on a phone.
2. Trust near the buy button: shipping, 30-day returns, secure payment, real reviews or videos.
3. Proof placement: real customer videos right after the first best-seller grid and under add-to-cart.
4. Offer clarity: bundle discount (2 items -10%, 3 items -15%, 4+ -20%) shown in the announcement bar and cart.
5. Friction: sizing guide link beside the size picker, FAQ answering delivery time, returns and VAT.
6. Rank fixes as major blockers vs polish, with exact copy to use.

## Product descriptions (Spanish)
Structure: short hook → 3–5 benefit bullets → fabric and fit → size advice → care → shipping and returns. Only use facts the supplier or Alvaro confirmed.

## Legal musts for selling in Spain (always check)
- Aviso legal (LSSI) with the real owner: Scaling Life LLC, Wyoming, US.
- Right of withdrawal: at least 14 days (the store offers 30).
- Prices include VAT. EU import VAT/IOSS applies when shipping from outside the EU; a US LLC does not remove this.
- EU Omnibus: a "before" price must be the lowest of the last 30 days.
- No fake reviews, testimonials or "verified purchase" badges without real purchases.
- No brand story claims that are not true (such as years in business).
- If asked for something misleading, explain the risk briefly and offer the honest version.