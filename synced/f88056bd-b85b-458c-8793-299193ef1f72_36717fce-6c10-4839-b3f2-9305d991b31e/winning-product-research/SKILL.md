---
name: "winning-product-research"
description: "Use for Alvaro's dropshipping product research and competitor-store analysis: Meta Ad Library searches, checking the 4 winning-product criteria, and filling the shared Product Research and Analizar Tiendas sheets."
---

# Winning product research (fashion dropshipping, Spain)

Goal: find stores and products that already work abroad and could work in Spain. Fashion niche, men and women.

## Countries
Italy, Germany, UK, USA, Netherlands, France, Portugal, Spain, Australia.

## Ad Library search
Search the Meta Ad Library (all ads, country = target market). Translate keywords into each market's language. Keyword types:
- store closing / clearance / sale
- urgency (last units, today only)
- free shipping / guarantee / returns
- specific fashion products (coat, jumper, dress, set, trousers, shoes)
- style / comfort
- bestseller / trust
- CTA phrases (shop now, discover the collection)
- city + country-domain URL patterns (london.uk/products, berlin.de, milano.it)

Scraping tip: split `document.body.innerText` on "Library ID:" to parse advertiser, start date and ad text.

## Winning-product criteria (ALL 4 must pass)
1. The store has **50+ active ads** in the Meta Ad Library.
2. The product's ad has been active **7–21 days** (21 is the maximum; older ads do not count).
3. Reach of that ad, tiered by age:
   - 7–13 days: **50,000+**
   - 14–20 days: **100,000+**
   - 21 days: **200,000+**
   EU reach comes from the ad's EU transparency data. For USA/UK/Australia, state where the figure came from.
4. The product's **PPSPY best-seller position falls between 15% and 30% of the store's ranking**.
   - Position % = rank ÷ total products in the store's PPSPY best-seller list × 100.
   - Example: store with 100 products → positions 15–30 pass; #10 or #40 do not. Store with 40 products → positions 6–12.
   - Round the allowed positions to whole numbers and show the calculation.

Never invent a figure. If a data point cannot be verified, mark it "sin verificar" and say how to check it. A product that fails any criterion is not listed as a winner.

## Output 1: "Product Research 2026 - Spain" sheet
Google Sheet id 14WW8Wd4tjddAmC0ZaR8oS4xSSjm-5LQwMwTtniVuw3c, tab "2026". Columns:
Lister | Keywords | Product Name | BER | Competitor Link | FB Ad Link | Other Links | Validation | Spy Method | Date Found | Product Lister | Creatives | Media Buyer

- BER = break-even ROAS (use the ecom-profit-check skill for the math).
- Validation format (Spanish):
  `Anuncio activo desde DD-MM-AAAA (N días) - alcance N (mínimo exigido N) - PPSPY bestseller #N de M (X%) - N anuncios activos totales en la tienda`
- Dates as DD-MM-YYYY.

## Output 2: "Analizar Tiendas - Spain" sheet
Google Sheet id 18909uRsM_vnPSQzHr8jxa1YOMewfewJ1ud7m-pgWBQw, one tab per country. Columns:
LINK TIENDA | ADS ACTIVOS | TIEMPO ACTIVO | Nº DE PRODUCTOS | TOP 5 BEST SELLERS | LISTADOS | FECHA ÚLT. ANÁLISIS

Writing to Google Sheets in the browser: typing into the grid often fails. A synthetic paste event (DataTransfer with a text/html table) on `.cell-input` works. Never overwrite rows co-workers wrote; append.

## Rules
- Inspiration, not copying: never reuse a competitor's photos, text, logo or trademark.
- Finish each session with a summary: stores analysed, products that passed all 4 criteria, products rejected and why, next steps.