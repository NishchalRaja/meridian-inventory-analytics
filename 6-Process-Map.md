# Process Map — Velocity-Based Inventory Rebalancing

## As-Is Process (Current State)

```mermaid
flowchart TD
    A[Season begins] --> B[Reorder points set once, based on last season's rough estimate]
    B --> C[Store sells product through the season]
    C --> D{Reorder point reached?}
    D -- Fast-moving SKU --> E[Replenishment often too slow - stockout occurs]
    D -- Slow-moving SKU --> F[Replenishment arrives - stock piles up, rarely sells through]
    E --> G[Lost sales, no alert generated]
    F --> H[Capital tied up, no alert generated]
    G --> I[Season ends - cycle repeats next season]
    H --> I
```

**Pain points identified**
- Reorder points are set once per season and never revisited against actual in-season velocity
- No alert exists when a fast-mover is stocking out or a slow-mover is overstocking — both go unnoticed until a manual review
- The same static reorder logic is applied regardless of how differently individual SKUs actually sell

## To-Be Process (Redesigned)

```mermaid
flowchart TD
    A[Sales and inventory data flows in nightly] --> B[System classifies each SKU into a velocity tier]
    B --> C[Reorder point recalculated per SKU per store]
    C --> D{Tier or reorder point changed significantly?}
    D -- Yes --> E[Category manager alerted with data: stockout days, lost sales, turns]
    D -- No --> F[No action needed, recommendation stands]
    E --> G[Category manager approves or overrides recommendation]
    G --> H[Replenishment adjusted - fast movers get more safety stock, slow movers less]
    H --> A
```

**Key changes**
- Reorder points recalculate continuously from real sales data instead of once a season
- Category managers are proactively alerted only when something has meaningfully changed, rather than needing to notice a problem themselves
- The loop is continuous — each recalculation feeds the next, rather than resetting only at season boundaries

## Estimated Impact

| Stage | As-Is | To-Be Target |
|---|---|---|
| Fast-mover avg stockout days/month | 8.1 | ≤4.0 |
| Slow-mover avg inventory (5 SKUs, 4 stores, snapshot) | ≈$41,984 | ≈$29,400 (-30%) |
| Annualized lost sales from stockouts | $887,139 | ≈$443,500 (-50%) |
