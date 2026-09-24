# Business Requirements Document (BRD)
## Velocity-Based Inventory Rebalancing — Meridian Home Goods

**Prepared by:** Nishchal Raja, Business Analyst
**Version:** 1.0 | **Status:** Approved for Development

---

## 1. Project Overview

Analysis of 6 months of sales and inventory data ([`Inventory_Analytics.xlsx`](./Inventory_Analytics.xlsx)) shows fast-moving SKUs stocking out ~27% of days while slow-moving SKUs sit overstocked, turning inventory at just 1.1x versus 9.5x for fast movers.

### 1.1 Business Objective
Rebalance reorder points so fast movers are stocked adequately and slow movers are trimmed, recapturing an estimated $443,500/year in lost sales and freeing ≈$12,600 in tied-up capital — without net new inventory investment.

## 2. Scope

**In Scope**
- Velocity-tiering logic classifying each SKU as fast, medium, or slow moving based on trailing sales data
- Updated reorder-point calculation per velocity tier
- Alerting for category managers when a SKU's velocity tier changes
- Pilot rollout across 2 stores before full deployment

**Out of Scope**
- Supplier contract renegotiation or lead-time changes
- New SKU introduction or assortment planning
- Store layout or shelf-space changes

## 3. Business Requirements

| ID | Requirement |
|---|---|
| BR-01 | Reduce fast-mover average stockout days from ~8/month to ≤4/month |
| BR-02 | Reduce slow-mover average inventory by at least 30% |
| BR-03 | Achieve BR-01 and BR-02 without a net increase in total inventory investment |
| BR-04 | Recalculate velocity tiers and reorder points automatically as new sales data arrives, without manual recalculation |

## 4. Functional Requirements

| ID | Requirement |
|---|---|
| FR-01 | System shall classify each SKU into a velocity tier (fast/medium/slow) based on trailing 90-day sales data |
| FR-02 | System shall calculate a recommended reorder point per SKU per store, weighted by its velocity tier |
| FR-03 | System shall flag any SKU whose velocity tier has changed since the last recalculation |
| FR-04 | System shall alert the relevant category manager when a SKU's reorder point recommendation changes by more than 20% |
| FR-05 | System shall display current stockout days, lost-sales estimate, and inventory turns per SKU alongside its reorder-point recommendation |
| FR-06 | System shall allow category managers to override a recommended reorder point, with the override logged |

## 5. Non-Functional Requirements

| ID | Requirement |
|---|---|
| NFR-01 | Velocity tier and reorder-point recalculation shall run nightly with no impact on POS system performance |
| NFR-02 | Reorder-point logic shall be auditable — category managers can see which inputs drove a given recommendation |
| NFR-03 | The system shall support all 4 stores and the full SKU catalog, not just the 10-SKU pilot sample |

## 6. Assumptions & Constraints

- POS and inventory data feeds are reliable and available at the SKU/store/day level
- Category managers retain override authority — the model recommends, it does not auto-execute purchase orders
- No new headcount is required; the model is added to existing supply-chain planning tools

## 7. Risks

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Category managers override recommendations too often, undermining the rebalancing | Medium | Medium | Track override rate during pilot; review with Supply Chain lead if overrides exceed 20% of SKUs |
| Reducing slow-mover stock triggers unexpected stockouts on those SKUs | Low | Medium | Phase the reduction gradually over the pilot rather than cutting stock in one step |
| Data quality issues in POS feed produce inaccurate tier classification | Low | High | Validate model output against manual category-manager judgment during the pilot |

## 8. Success Metrics / KPIs

- Fast-mover average stockout days (target: ≤4/month)
- Slow-mover average inventory reduction (target: ≥30%)
- Annualized lost-sales estimate (target: reduced from $887,139 baseline)
- Override rate on model recommendations (monitored, target: <20%)
