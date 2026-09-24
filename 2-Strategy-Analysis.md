# Strategy Analysis
## Inventory Rebalancing Strategy - Meridian Home Goods

---

## 1. Strategic Context

Meridian's leadership has flagged working-capital efficiency as a priority for the year — inventory investment needs to work harder, not simply grow. Any fix to the stockout problem has to come from reallocating existing inventory capital more intelligently, not from just buying more stock.

## 2. Options Matrix

| Criteria | A: Raise Safety Stock Broadly | B: Data-Driven Rebalancing (Recommended) | C: Vendor-Managed Inventory |
|---|---|---|---|
| Cost | Low effort, high capital tie-up | Medium, one-time build | Medium-high, ongoing supplier coordination |
| Speed to value | Fast | Fast | Slow (supplier onboarding) |
| Addresses root cause | No - treats symptom only | Yes - targets reorder-point accuracy directly | Partially - shifts, doesn't solve, the planning problem |
| Fit with working-capital priority | Poor - increases total inventory | Good - reallocates existing capital | Neutral - capital shifts off books but service risk remains |

## 3. SWOT of Current Inventory Planning

**Strengths**
- Store-level sales and inventory data already exists in the POS system
- Category managers have strong supplier relationships for fast replenishment when needed

**Weaknesses**
- Reorder points are set once per season and rarely revisited against actual velocity
- No visibility that ties stockout frequency directly to lost-sales dollars — the problem is invisible in day-to-day reporting

**Opportunities**
- Existing POS and inventory data is sufficient to build a velocity-based reorder-point model with no new data collection required
- Freed capital from slow-mover reduction can fund fast-mover safety stock at no net new investment

**Threats**
- Competitors with tighter replenishment cycles capture the sale when Meridian's best sellers are out of stock
- Continued overstock of slow movers ties up capital that limits investment elsewhere in the category mix

## 4. Recommended Strategic Direction

Adopt a **velocity-based inventory rebalancing strategy**: recalculate reorder points per SKU using actual demand and stockout data, increasing safety stock for high-velocity SKUs while trimming allocation for consistently slow movers — funding the shift from freed capital rather than new spend. This directly targets the pattern shown in [`Inventory_Analytics.xlsx`](./Inventory_Analytics.xlsx) rather than treating stockouts and overstock as separate problems.

## 5. Key Trade-offs Accepted

- Requires category managers to accept reduced allocation on familiar slow-moving SKUs, which may face internal resistance
- Model accuracy depends on continued, reliable POS/inventory data feeds — validated during the pilot phase (see [Project Lifecycle](./4-Project-Lifecycle.md))
