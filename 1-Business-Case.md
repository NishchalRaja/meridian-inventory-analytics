# Business Case
## Inventory Rebalancing - Meridian Home Goods

**Prepared by:** Nishchal Raja, Business Analyst
**Company (simulated):** Meridian Home Goods — a fictional 4-store home goods retailer, used as the scenario for this case study

---

## 1. Problem Statement

A 6-month analysis (Jan–Jun 2026) of Meridian's 10 highest- and lowest-velocity SKUs across its 4 stores and 5 categories, built out in [`Inventory_Analytics.xlsx`](./Inventory_Analytics.xlsx), shows a consistent pattern: **best-selling SKUs stock out constantly while slow-moving SKUs sit overstocked.**

- Fast-moving SKUs were out of stock **26.8% of days** on average — roughly 8 days a month each
- Slow-moving SKUs were out of stock only **3.3% of days** — essentially never
- Fast movers turned inventory **9.5x** over the sample window; slow movers turned just **1.1x**

## 2. Cost of Inaction

- **Lost sales from stockouts:** $443,569 over the 6-month sample, an estimated **$887,139 annualized** if the pattern continues (see the Dashboard tab and `Assumptions & Notes` tab in the workbook for the extrapolation method)
- **Capital tied up in overstock:** an estimated **$41,984** worth of inventory sitting in just 5 slow-moving SKUs across 4 stores at any given time — capital that could instead fund safety stock for the SKUs actually driving demand
- **Concentration of the problem:** Bedding is the single worst-affected category ($124,443 in 6-month lost sales), and the Cooling Bamboo Sheet Set (BED-201) alone accounts for $122,958 of that — the single highest-impact SKU in the dataset

## 3. Options Considered

| Option | Description | Cost | Speed to Value | Risk |
|---|---|---|---|---|
| **A — Raise safety stock across the board** | Increase reorder points uniformly for all SKUs | Low effort, but high capital cost | Fast | Worsens the overstock side of the problem |
| **B — Data-driven reorder-point rebalancing** | Recalculate reorder points per SKU based on actual velocity; raise fast-mover safety stock, trim slow-mover allocation | Medium (one-time analytics + process build) | Fast | Requires reliable, regularly refreshed demand data |
| **C — Vendor-managed inventory (VMI)** | Hand replenishment decisions to suppliers for top SKUs | Medium-high (supplier negotiation, integration) | Slow | Loses direct control; supplier lead times vary |

## 4. Recommendation

**Option B (data-driven reorder-point rebalancing)** is recommended. It directly targets the root cause identified in the data — reorder points that don't reflect actual SKU-level velocity — without either the blunt capital cost of Option A or the lead time and control trade-offs of Option C. Full rationale in [Strategy Analysis](./2-Strategy-Analysis.md).

## 5. Financial Projection

| Item | Estimate |
|---|---|
| Build cost (analytics model + replenishment process change) | ≈$60,000 one-time |
| Target: recapture 50% of annualized lost sales | ≈$443,500/year in retained revenue |
| Target: reduce slow-mover inventory by 30% | ≈$12,600 in freed working capital |
| Payback period | Under 2 months of retained revenue |

## 6. Success Criteria

- Fast-mover average stockout days cut from ~8/month to ≤4/month
- Slow-mover average inventory reduced by at least 30%, without new stockouts appearing on those SKUs
- Overall category-level inventory turns balance improves without a net increase in total inventory investment

Full requirements are documented in the [BRD](./5-BRD.md).
