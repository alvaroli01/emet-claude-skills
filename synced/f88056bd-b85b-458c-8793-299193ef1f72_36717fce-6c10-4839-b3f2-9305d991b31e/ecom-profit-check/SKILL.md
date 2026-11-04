---
name: "ecom-profit-check"
description: "Use whenever pricing a product, calculating margin, break-even ROAS, CPA or deciding to launch, kill or scale a Meta ad test (single product or full collection CBO), building a collection from a winner, or deciding when to add new creatives, for Alvaro's Spain store; always before recommending a selling price."
---

# Profit check: price, break-even ROAS, CPA

Alvaro's past mistake: prices set too high and ROAS never calculated. Every product gets this check before it is listed or advertised.

## Minimum margin rule (applies to EVERY product)
- **Margin = selling price − supplier cost. It must be at least 30 € per product; more is better.**
- Why: without that margin, scaling costs far too much and the campaign cannot move forward.
- Example: sell at 49,95 €, supplier cost 19,95 € → 30 € margin.
- Maximum supplier cost for each price point:

| Selling price | Max supplier cost |
|---|---|
| 34,99 € | 4,99 € |
| 39,99 € | 9,99 € |
| 44,99 € | 14,99 € |
| 49,99 € | 19,99 € |
| 54,99 € | 24,99 € |
| 59,99 € | 29,99 € |
| 64,99 € | 34,99 € |
| 69,99 € | 39,99 € |
| 74,99 € | 44,99 € |
| 79,99 € | 49,99 € |

- A product priced at 29,99 € can never reach 30 € margin, and 34,99 € needs a cost under 5 €: in practice most products will sit at 39,99 € or more.
- If a product does not reach 30 € margin inside the price range, flag it: "no cumple el margen mínimo de 30 €", and suggest a cheaper supplier, a higher price inside the range, or dropping it.
- Always also show the real margin after VAT (price ÷ 1.21 − cost), because the 30 € rule is calculated on the VAT-inclusive price (e.g. 49,95 € → 41,28 € without VAT − 19,95 € = 21,33 € real). The 30 € rule is the pass/fail filter; the after-VAT figure is for BER and CPA.

## Store price range (baremo, set by Alvaro)
- Every selling price must sit between **29,99 € and 79,99 €** (VAT included).
- Use endings in **,99** (29,99 €, 34,99 €, 39,99 €, 44,99 €, 49,99 €, 54,99 €, 59,99 €, 64,99 €, 69,99 €, 74,99 €, 79,99 €).
- If the product only works above 79,99 €, do not raise the price: flag it as "no encaja en el baremo" and suggest a cheaper supplier, a bundle, or dropping it.
- If similar items sell well below the price the 30 € margin needs, flag that too (the price may look too high for what it is).
- Low-end prices (29,99–34,99 €) rarely meet the 30 € margin; if used, they should work mainly as bundle entry products (2 items -10%, 3 items -15%).

## Inputs (ask for missing ones; never invent)
- Product cost and shipping to Spain from supplier
- Planned selling price (EUR, VAT included, inside the range above)
- Payment/Shopify fees (default assumption: ~2.9% + €0.30; label as an assumption)
- Expected return/refund rate (default 10% for fashion; label as an assumption)
- Discount or bundle in force (2 items -10%, 3 items -15%, 4+ -20%)
- Competitor prices in Spain for similar items

If a number is a guess, mark it with ⚠️ and keep it separate from confirmed inputs.

## Math (show every formula)
0. **Margin check: price − supplier cost ≥ 30 €.** Fail → stop and flag.
1. Net price = price ÷ 1.21 (Spanish VAT 21% is inside the displayed price).
2. Variable cost per order = product + shipping + fees + (return rate × cost of a return).
3. Contribution margin = net price − variable cost.
4. **Break-even ROAS (BER) = price ÷ contribution margin**. Use the VAT-inclusive price here because Meta reports revenue at checkout price, and say so.
5. Break-even CPA = contribution margin.
6. Target ROAS = price ÷ (contribution margin − desired profit per order). Default desired profit: 30% of the margin.
7. Rerun the numbers with the bundle discounts applied (4+ items at -20% is the tightest case).

Run the math in Python when there are more than a couple of products, and put BER into the Product Research sheet.

## Price sanity check
- Confirm the price is inside 29,99–79,99 €, ends in ,99, and gives at least 30 € margin.
- Compare against Spanish competitors. Flag if the price is more than 20% above similar items.
- Flag products with BER above 3: hard to make profitable with cold Meta traffic.

## Ad decisions (Meta) — Alvaro's rules
First ask (or infer) which test type it is: **single product test** or **collection test (CBO)**. They have different rules.

Net margin = (revenue without VAT − product and shipping cost − fees − ad spend) ÷ revenue without VAT.

The path is: single product test (A) → product scaled to 100 €/day → build a collection around it (B) → test the collection (C) → keep feeding new creatives as budget grows (D).

### A) Single product test
Metrics: spend, visits (link clicks / landing page views), adds to cart, purchases, CTR, CPC, CPM, frequency.

Kill rules:
1. **10 € spent and 0 visits** → turn it off.
2. **Visits but 0 adds to cart at 20 € spent** → turn it off.
3. **Adds to cart but no sale** → keep it running up to **30 €**; still no sale at 30 € → turn it off.
4. **At least one sale** → keep it running and judge it on net margin.

Scaling:
- **Net margin above 30% two days in a row** → double the budget (e.g. 50 € → 100 €/day).
- **Net margin 20–25%** → scale in steps of +25 €/day.
- 25–30% and below 20% not defined for product tests: say so and ask Alvaro.

How many products at once: 1–2 with little capital; 3–5 for faster results when there is time to manage. With the €2,000 budget, show how many full tests (up to 30 € each) the ad budget covers.

### B) Building a collection from a winning product
**When:** only once the single-product campaign is already **scaled to 100 €/day**. Before that, do not.

**How:** pick **products similar to each other**, between **12 and 20 products (ideal: 20)**, every one meeting the 30 € margin rule.

**Where to find them:**
- Similar products from your own store that have already sold.
- Similar products from competitors that pass the validations (winning-product-research skill).
- AliExpress with the **look-alike method** (visually similar items).
- Similar stores that sell similar products.

**Store guidelines:** plan the collection first · same background in every product image · same model (same person) · similar prices (inside 29,99–79,99 €, close to the winner) · products that look alike.

**Creative guidelines:** iterate on what worked in the product campaign (same winning concept) · if the winner used UGC, more UGC with the same person and style · **10 creatives: 7 videos + 3 images** (google-flow-creatives skill).

Key idea: the collection inherits what already works — same style, same concept, same winner — scaled to more products.

### C) Collection test (CBO playbook)
Setup:
| Parameter | Value |
|---|---|
| Daily budget | 100–150 € (CBO) |
| Structure | 1 ad set |
| Creatives | 10: 7 videos + 3 images, varied concepts covering different angles |
| Primary texts | 2 |
| Headlines | 2 |
| Description | 1 |
| Landing page | Collection page |
| Launch window | 11:00–17:00 |
The whole collection is tested, not a single product.

Kill branch (spend checkpoints):
- **20 €**: check soft metrics (CPC, CTR, CPM). CPC above 1 € → kill. Good CPC → keep running.
- **60 €**: no purchase → kill. With a purchase → let it run to 120 €.
- **120 €**: no 2nd purchase → kill. With a 2nd purchase (CPA around 60 € or better) → let it run to 150 €.
- **150 €**: break-even → one more day and repeat the checks. Profitable → scale tomorrow.

Scaling branch:
- **150 €+ and 7 sales on day 1** → raise straight to 200 €/day.
- **2 days in a row at ≥20% margin** → +20% budget. Next day still ≥20% → another +20%.
- **2 days in a row at ≥30% margin** → double the budget, and always launch new ad sets with new creatives.
- **After any scale-up**: 48 h without touching the campaign. If 2 days are not profitable → go back to the previous budget.

Golden rules:
- **CPA is the metric that decides scaling, not ROAS.**
- When it is profitable, **never turn anything off**: only scale and stack new ad sets.
- Wait 48 h after every scale-up before deciding anything.
- Every new ad set launched to scale must carry **new creatives** (google-flow-creatives skill).

Budget note: a full collection test to 150 € is 7.5% of the €2,000 starting budget; say how many tests the ad budget allows.

### D) When to add new creatives (scaled campaigns)
| Campaign | From 200 €/day | From 500 €/day |
|---|---|---|
| Collection | **10 new creatives every 2 days** | **10 new creatives every day** |
| Single product | **5 new creatives every 2 days** | **5 new creatives every day** |

- Mix always **70 / 30**: 70% iterations of what already works, 30% a completely new concept.
- **Always add them in a NEW ad set inside the SAME campaign.**
- **Every time the budget doubles** (100 → 200 → 400 → 800 €), also add new creatives at that moment.
- Every budget jump = new creatives in a new ad set, always 70/30. When a refresh is due, remind Alvaro and hand the brief to google-flow-creatives.

## Output
1. Assumptions table (confirmed vs ⚠️ assumed)
2. Results: margin (vs the 30 € minimum), margin after VAT, BER, break-even CPA, target ROAS
3. Verdict: launch / fix price / drop (or, for live ads: kill / keep / scale / add creatives, naming the test type and the exact rule applied)
4. Budget note: state what a test costs as a share of the €2,000 budget.

No fake strikethrough prices: under the EU Omnibus rules the "before" price must be the lowest price of the last 30 days.