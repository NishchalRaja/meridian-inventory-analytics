# Inventory Rebalancing — Meridian Home Goods

**Author:** Nishchal Raja | Business Analyst
**Category:** Data Analysis / Business Case

> A self-directed portfolio project built around a simulated 4-store retailer, "Meridian Home Goods," to demonstrate a data-driven BA engagement — from raw sales data through diagnostic analytics, business case, strategy, and delivery-ready requirements.

---

## 📋 Executive Summary

Meridian's best-selling SKUs were stocking out roughly 8 days a month while its slowest-moving SKUs sat overstocked, tying up capital. A 6-month analysis across 4 stores and 10 representative SKUs quantified the problem — an estimated $887,139 in annualized lost sales and $41,984 in tied-up capital — and this project built the full case for fixing it: diagnostic analytics, a business case, a strategy decision, stakeholder alignment, and a delivery-ready requirements package for a velocity-based inventory rebalancing model.

---

## 🎯 Business Problem

### Context
Meridian sets reorder points once per season and rarely revisits them against actual in-season sales velocity, across 4 stores and 5 product categories.

### Challenge
Fast-moving SKUs were out of stock 26.8% of days on average; slow-moving SKUs almost never stocked out but turned inventory at just 1.1x versus 9.5x for fast movers — full breakdown in [Business Case](./1-Business-Case.md).

### Objective
Rebalance reorder points to cut fast-mover stockouts roughly in half and reduce slow-mover overstock by 30%, without new inventory investment — full reasoning in [Strategy Analysis](./2-Strategy-Analysis.md).

---

## 📊 Methodology & Techniques Used

- **SKU/store/month-level data modeling** — built a 240-row dataset spanning 10 SKUs, 4 stores, and 6 months
- **Formula-driven analysis in Excel** — SUMIF/AVERAGEIF aggregation by category, SKU, store, and month (see [`Inventory_Analytics.xlsx`](./Inventory_Analytics.xlsx))
- **Inventory turns and stockout-rate analysis** — quantified the stockout-vs-overstock pattern at the SKU level
- **Options matrix + SWOT** — evaluated three strategic paths before recommending velocity-based rebalancing
- **Stakeholder mapping + RACI** — aligned Merchandising, Supply Chain, Category Managers, Store Ops, and Finance
- **Phase-gated delivery lifecycle** — diagnostic and strategy sign-off up front, two-week sprints for the build (see [Project Lifecycle](./4-Project-Lifecycle.md))
- **Pilot-then-scale rollout** — validated on 2 of 4 stores before full deployment

---

## 🔍 Key Findings

### Finding 1: The stockout and overstock problems are two sides of the same root cause
**Impact:** Reorder points don't reflect actual SKU velocity — fast movers are under-stocked and slow movers are over-stocked by the same static logic.

### Finding 2: The problem is concentrated, not evenly spread
**Impact:** Bedding is the worst-affected category ($124,443 in 6-month lost sales), driven almost entirely by a single SKU — the Cooling Bamboo Sheet Set ($122,958).

### Finding 3: No one currently sees this pattern in day-to-day reporting
**Impact:** Stockouts and overstock both go unnoticed until a manual review, because no alert or dashboard currently connects sales velocity to reorder-point accuracy.

---

## 💡 Recommendations

1. **Classify every SKU into a velocity tier** using trailing sales data, refreshed nightly (Sprint 1)
2. **Recalculate reorder points per SKU per store**, weighted by tier, replacing the static seasonal approach (Sprint 1)
3. **Alert category managers only on significant changes**, with supporting stockout/lost-sales/turns data at the point of decision (Sprint 2)

Full requirements in [BRD](./5-BRD.md) and delivery-ready backlog in [User Stories](./7-User-Stories.md).

---

## 📈 Expected Impact

| Metric | Current State | Target State | Impact |
|---|---|---|---|
| Fast-mover avg stockout days/month | 8.1 | ≤4.0 | -51% |
| Annualized lost sales from stockouts | $887,139 | ≈$443,500 | -50% |
| Capital tied up in slow-moving SKUs (snapshot) | $41,984 | ≈$29,400 | -30% (≈$12,600 freed) |
| Fast-mover inventory turns | 9.5x | 10–11x target | Faster, more responsive replenishment |

**Overall Business Value:** A projected ~$443,500/year in recaptured revenue plus ~$12,600 in freed working capital, against a one-time build cost of ≈$60,000 — a payback period under 2 months.

---

## 📁 Project Files

Read in this order:

1. [Business Case](./1-Business-Case.md) — Problem cost, options considered, financial projection, and ROI
2. [Strategy Analysis](./2-Strategy-Analysis.md) — Options matrix, SWOT, and recommended strategic direction
3. [Stakeholder Analysis](./3-Stakeholder-Analysis.md) — Stakeholder map, RACI matrix, and engagement plan
4. [Project Lifecycle](./4-Project-Lifecycle.md) — Phases, timeline, and governance gates from initiation to rollout
5. [BRD](./5-BRD.md) — Business, functional, and non-functional requirements
6. [Process Map](./6-Process-Map.md) — As-is and to-be replenishment flow diagrams
7. [User Stories](./7-User-Stories.md) — Sprint-ready backlog with acceptance criteria
8. [`Inventory_Analytics.xlsx`](./Inventory_Analytics.xlsx) — Raw data, category/SKU/store/month summaries, and a dashboard with charts and key metrics

---

## 🛠️ Technical Details

### Tools Used
- **Excel:** Formula-driven analysis (SUMIF, AVERAGEIF, IFERROR), pivot-style summary tabs, and a chart dashboard
- **Mermaid diagrams:** As-is and to-be replenishment process flows
- **Requirements documentation:** BRD authoring, MoSCoW prioritization
- **Agile backlog structuring:** Epics, user stories, story points, sprint planning

### Data Sources
- Simulated 6-month SKU/store/month sales and inventory dataset (constructed for this portfolio project — see the `Assumptions & Notes` tab in the workbook)

### Assumptions
- Full details are documented on the `Assumptions & Notes` tab of [`Inventory_Analytics.xlsx`](./Inventory_Analytics.xlsx), including the lost-sales calculation method and the annualization approach

---

## 📝 Limitations & Caveats

- This is a simulated case study for portfolio purposes, not a real client engagement — the dataset is synthetic, constructed to be internally consistent rather than audited.
- The 10-SKU sample is illustrative of a broader catalog pattern, not an exhaustive inventory audit.
- Lost sales are valued at full retail price (revenue impact), not margin-adjusted.

---

## 🎓 Key Learnings

1. Building the actual dataset and letting formulas compute the totals — rather than asserting round numbers — made the business case far more credible and easier to defend under questioning.
2. The stockout and overstock problems looked unrelated at first glance but turned out to share one root cause, which changed the recommended fix from "buy more stock" to "reallocate existing stock."
3. A dashboard that ties reorder-point accuracy directly to a dollar figure is what actually gets a data-quality problem onto leadership's radar.

---

## 📞 Contact & Questions

**Author:** Nishchal Raja
**Email:** [your.email@example.com]
**LinkedIn:** [Your LinkedIn profile]

---

## 📜 License & Usage

This analysis and recommendations are provided for educational and professional portfolio purposes.
