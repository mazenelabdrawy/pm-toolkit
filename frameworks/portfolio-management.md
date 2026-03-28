# Product Portfolio Management

> Managing a single product well is execution. Managing a portfolio of products well is strategy — deciding not just how to build, but what to build, and what to stop building.

---

## What Portfolio Management Is (and Isn't)

Portfolio management is the discipline of allocating finite resources (people, time, budget, attention) across multiple products or product areas to maximize overall business impact.

It is NOT:
- A spreadsheet of features across teams
- Giving every product equal resources to be "fair"
- Managing the Jira backlog for multiple products

It IS:
- Making explicit bets on which products to grow, maintain, harvest, or exit
- Ensuring the portfolio as a whole is greater than the sum of its parts
- Holding the tension between short-term delivery and long-term positioning

---

## The Portfolio Strategy Framework

### Step 1: Classify Each Product

Use a modified BCG matrix adapted for software product portfolios:

| Classification | Market Position | Growth Rate | Strategic Action |
|---|---|---|---|
| **Star** | Strong | High | Invest aggressively — this is the growth engine |
| **Cash Cow** | Strong | Low | Maintain efficiency — extract margin, fund Stars |
| **Question Mark** | Weak | High | Make a decision — invest to win, or exit |
| **Dog** | Weak | Low | Harvest or kill — don't let it drain resources |

**Important:** Classifications change. A Star becomes a Cash Cow as its market matures. A Question Mark that gets investment can become a Star. Review quarterly.

---

### Step 2: Define the Portfolio Thesis

The portfolio thesis answers: *How do these products fit together to create more value than each would create alone?*

Common portfolio theses:
- **Platform + Applications:** One core platform with multiple application layers (e.g., Odoo ERP + CRM + HR + Accounting as modules on a shared data layer)
- **Market penetration + Market expansion:** One mature product that funds the development of a new product for an adjacent market
- **Horizontal + Vertical:** A horizontal product (used across industries) paired with vertical products (purpose-built for specific industries)
- **Data network effect:** Products that individually capture data; together they create a data advantage that none could achieve alone

---

### Step 3: Allocate Resources Against the Thesis

Resource allocation is where strategy becomes real. The default allocation error is distributing resources equally — this satisfies everyone politically but produces suboptimal outcomes strategically.

**Allocation principles:**

*Concentrate investment in Stars.* An underfunded Star is one of the most expensive strategic mistakes — you miss a market window that won't return.

*Protect Cash Cows from over-investment.* Cash Cows fund the portfolio. Don't divert from them, but don't invest in growth they're not capable of. Optimize for margin.

*Set a decision deadline for Question Marks.* A Question Mark that stays a Question Mark indefinitely is a Dog in denial. Set a milestone: "In 2 quarters, this product will show X or we will change our investment thesis."

*Kill Dogs cleanly.* The most common portfolio management failure is keeping products alive out of sunk cost thinking. A product that is draining resources without a path to value should be killed or divested. This is hard politically but necessary strategically.

---

## Cross-Portfolio Dependency Management

In a portfolio of products, dependencies between products create both leverage and risk.

**Leverage:** Shared components (auth, payments, data layer) reduce total investment and create consistency.

**Risk:** A dependency on a shared service means that a change to the shared service can cascade across multiple products.

**The dependency mapping exercise:**

For each product in the portfolio, document:
1. What does it consume from shared services?
2. What does it provide to other products?
3. What happens to other products if this product changes or breaks?

This map reveals:
- Which products are architectural foundations (change carefully)
- Which products are highest-risk for cascading failures
- Where investment in shared infrastructure creates the most portfolio-wide leverage

---

## Portfolio-Level Roadmap

A portfolio roadmap shows how individual product investments relate to each other and to overall business objectives.

**Three layers:**

```
BUSINESS OBJECTIVES
(Revenue, market share, margin, strategic positioning)
          │
PORTFOLIO THEMES
(What capabilities we're building across products this year)
          │
PRODUCT ROADMAPS
(Specific deliverables per product team)
```

The portfolio roadmap lives at the middle layer. It shows:
- Which products are contributing to which business objectives
- Where resources are concentrated and why
- Key dependencies between product teams
- How the portfolio will look different in 12–18 months

**Rule:** Business objectives drive portfolio themes, which drive product roadmaps. Never let product roadmaps drive upward. If a product team is doing work that doesn't map to a portfolio theme, that work is either misdirected or the portfolio themes are wrong.

---

## Portfolio Health Metrics

Track these at the portfolio level, not just per product:

| Metric | What It Tells You |
|---|---|
| Revenue concentration | % of revenue from top 1–2 products — high concentration = portfolio risk |
| Investment-to-revenue ratio by product | Are you over-investing in low-return products? |
| New product contribution | % of revenue from products launched in the last 24 months — signals innovation pipeline health |
| Shared infrastructure cost | Overhead of maintaining shared services across the portfolio |
| Cross-sell rate | % of customers using 2+ products — measures portfolio integration success |

---

## Common Portfolio Management Failure Modes

**Spreading too thin:** Funding 7 products at 70% of what each needs, when 3 funded at 100% would produce better outcomes. Underfunding produces mediocre products at scale.

**Zombie products:** Products that are technically alive (small team, some revenue) but have no path to growth or strategic relevance. They drain morale and resources proportionally to their size.

**Missing the platform layer:** Building multiple products without recognizing the shared layer that could connect them — and then building point-to-point integrations instead. The result is a portfolio of silos.

**Political allocation:** Distributing resources based on seniority of business unit heads or historical headcount rather than strategic opportunity. The noisiest team gets more resources, not the most important one.
