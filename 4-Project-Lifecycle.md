# Project Lifecycle
## Inventory Rebalancing Strategy - Meridian Home Goods

A phase-gated lifecycle: diagnostic analysis and strategy were sequenced up front given the cross-category budget implications, while the model build and rollout ran in two-week increments.

---

## Phase 1: Initiation & Diagnostic Analysis (Weeks 1–3)
- Pulled 6 months of POS and inventory data across 4 stores and 10 representative SKUs
- Built [`Inventory_Analytics.xlsx`](./Inventory_Analytics.xlsx) to quantify lost sales, stockout frequency, and inventory turns by SKU, category, store, and month
- Business case drafted and approved by VP Merchandising (see [Business_Case.md](./1-Business-Case.md))

## Phase 2: Strategy & Planning (Weeks 4–5)
- Options analysis and SWOT completed; velocity-based rebalancing strategy selected (see [Strategy_Analysis.md](./2-Strategy-Analysis.md))
- Stakeholder map and RACI finalized (see [Stakeholder_Analysis.md](./3-Stakeholder-Analysis.md))
- BRD drafted and signed off by Supply Chain and Category Management (see [BRD.md](./5-BRD.md))

## Phase 3: Design (Weeks 6–7)
- As-is and to-be replenishment process mapped (see [Process_Map.md](./6-Process-Map.md))
- Reorder-point model logic defined per SKU velocity tier
- User stories written and estimated (see [User_Stories.md](./7-User-Stories.md))

## Phase 4: Build (Weeks 8–11, 2 sprints)
- Sprint 1: Velocity-tiering logic and updated reorder-point calculations
- Sprint 2: Alerting for category managers when a SKU crosses into a new velocity tier

## Phase 5: Pilot (Weeks 12–15)
- Rolled out to 2 of 4 stores, covering all 5 categories
- Category managers reviewed and approved rebalanced reorder points before go-live
- Weekly review of pilot stockout days and inventory levels against baseline

## Phase 6: Rollout & Monitoring (Weeks 16+)
- Expanded to all 4 stores after pilot go/no-go review
- Stockout days, lost-sales estimate, and slow-mover inventory levels tracked quarterly against the [Business_Case.md](./1-Business-Case.md) success criteria

---

## Governance & Phase Gates

| Gate | Decision | Owner |
|---|---|---|
| End of Initiation | Approve business case | VP Merchandising |
| End of Planning | Approve strategy & requirements | Head of Supply Chain, Category Managers |
| End of Design | Approve scope for build | Working team |
| End of Pilot | Go / no-go for full rollout | VP Merchandising, Head of Supply Chain |
