# User Stories — Velocity-Based Inventory Rebalancing

Derived from the [BRD](./5-BRD.md) functional requirements (FR-01 through FR-06), organized into three epics.

---

## Epic 1: Velocity Tiering
*Related requirements: FR-01, FR-03*

### US-01 — Automatic velocity classification
**As a** Supply Chain Planner, **I want** every SKU automatically classified as fast, medium, or slow moving, **so that** reorder points reflect actual demand rather than a seasonal guess.

**Acceptance Criteria**
- Given 90 days of trailing sales data for a SKU, when the nightly classification job runs, then the SKU is assigned a velocity tier.
- Given a SKU's tier changes from the prior run, when classification completes, then the change is flagged for review.

**Priority:** Must Have | **Story Points:** 8

### US-02 — Tier change history
**As a** Category Manager, **I want** to see a SKU's velocity tier history, **so that** I can tell whether a change is a one-off blip or a real trend.

**Acceptance Criteria**
- Given a SKU has changed tiers at least once, when its detail view is opened, then prior tier assignments and dates are visible.

**Priority:** Should Have | **Story Points:** 3

---

## Epic 2: Reorder Point Recommendations
*Related requirements: FR-02, FR-06*

### US-03 — Weighted reorder point calculation
**As a** Supply Chain Planner, **I want** reorder points calculated per SKU per store based on velocity tier, **so that** fast movers carry more safety stock and slow movers carry less.

**Acceptance Criteria**
- Given a SKU's velocity tier and store-level sales data, when the nightly job runs, then a recommended reorder point is calculated and stored.

**Priority:** Must Have | **Story Points:** 8

### US-04 — Manual override with logging
**As a** Category Manager, **I want** to override a recommended reorder point when I have context the model doesn't, **so that** I retain control over my category.

**Acceptance Criteria**
- Given a recommended reorder point, when a Category Manager enters an override value, then the override is saved and the original recommendation is preserved in the log.

**Priority:** Must Have | **Story Points:** 5

---

## Epic 3: Alerting & Visibility
*Related requirements: FR-04, FR-05*

### US-05 — Significant-change alert
**As a** Category Manager, **I want** to be alerted only when a reorder point recommendation changes significantly, **so that** I'm not overwhelmed with noise from minor daily fluctuations.

**Acceptance Criteria**
- Given a SKU's reorder point recommendation changes by more than 20% from the prior value, when the nightly job completes, then an alert is generated for that SKU's category manager.
- Given a change is below 20%, when the job completes, then no alert is generated.

**Priority:** Must Have | **Story Points:** 5

### US-06 — Supporting data at point of decision
**As a** Category Manager reviewing an alert, **I want** to see stockout days, lost-sales estimate, and inventory turns alongside the recommendation, **so that** I can make an informed override decision rather than guessing.

**Acceptance Criteria**
- Given an alerted SKU, when its detail view is opened, then stockout days, lost-sales estimate, and inventory turns for the current period are displayed alongside the reorder-point recommendation.

**Priority:** Must Have | **Story Points:** 3

---

## Sprint Planning Summary

**Total estimated story points:** 32

| Sprint | Stories | Points |
|---|---|---|
| Sprint 1 | US-01, US-03, US-05 | 21 |
| Sprint 2 | US-02, US-04, US-06 | 11 |
