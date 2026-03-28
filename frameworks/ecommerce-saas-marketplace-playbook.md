# PM Playbook: E-commerce, SaaS & Marketplace

> These are three fundamentally different product models. The metrics, the user psychology, the monetization logic, and the failure modes are different in each. Understanding the model you're operating in is the prerequisite to making good product decisions.

---

## Part 1: SaaS Product Management

### The SaaS Mental Model

SaaS is a recurring value exchange. The customer pays continuously because they receive continuous value. The moment the value stops, the payment stops.

This means:
- **Retention is revenue.** In SaaS, you don't "make the sale" once — you re-earn it every billing cycle.
- **Activation is the highest-leverage investment.** Users who don't activate churn before they've had a chance to experience value. Every activation improvement compounds across the entire customer base.
- **The product IS the sales process** in PLG. Every friction point in the product is a drop in conversion.

### SaaS Metrics That Matter

| Metric | Formula | What It Tells You |
|---|---|---|
| **ARR** | Monthly revenue × 12 | Scale of recurring business |
| **MRR Growth Rate** | (MRR this month - MRR last month) / MRR last month | Growth velocity |
| **Churn Rate** | Lost MRR / Starting MRR | Revenue health |
| **Net Revenue Retention** | (Starting MRR + Expansion - Contraction - Churn) / Starting MRR | True revenue health including expansion |
| **CAC** | Total sales + marketing spend / New customers acquired | Acquisition efficiency |
| **LTV** | ARPU / Churn rate | Long-term value per customer |
| **LTV:CAC Ratio** | LTV / CAC | Unit economic health — target > 3:1 |
| **CAC Payback Period** | CAC / (ARPU × Gross Margin) | How long to break even on a customer |
| **Activation Rate** | Users who hit activation event / Total signups | Onboarding effectiveness |
| **DAU/MAU Ratio** | Daily active users / Monthly active users | Product stickiness |

### The SaaS Growth Equation

```
New ARR = (New Logo ARR + Expansion ARR) - (Churned ARR + Contraction ARR)
```

Healthy SaaS companies have:
- Expansion ARR > Churned ARR (NRR > 100%)
- CAC payback period decreasing over time (efficiency improving)
- Activation rate increasing (onboarding improving)

### PM Priorities by Stage

| Stage | Primary Focus |
|---|---|
| Pre-PMF | Retention of early customers, qualitative feedback loops |
| Post-PMF / Growth | Activation optimization, PLG motion, channel diversification |
| Scale | Expansion revenue, NRR improvement, enterprise motion |

---

## Part 2: Marketplace Product Management

### The Marketplace Mental Model

Marketplaces are fundamentally different from SaaS. You're building two products simultaneously — one for supply (sellers, providers, hosts) and one for demand (buyers, customers, renters). Both sides must succeed for the marketplace to function.

The core challenge: **the chicken-and-egg problem.** Buyers don't come without supply; supply doesn't come without buyers. Every early-stage marketplace decision is about which side to seed first.

**The seeding strategy:** Almost always, seed supply first. It's easier to attract demand to an inventory-rich marketplace than to attract supply to a buyer-sparse one.

### Marketplace Metrics

**Supply-side metrics:**
| Metric | What It Tells You |
|---|---|
| Supplier acquisition rate | How fast you're building inventory |
| Supplier activation rate | % of onboarded suppliers who complete their first transaction |
| Supplier retention rate | Are suppliers finding value in the marketplace? |
| Listing quality score | Is the supply compelling to buyers? |
| Supply concentration | Are you over-dependent on a small number of suppliers? |

**Demand-side metrics:**
| Metric | What It Tells You |
|---|---|
| Buyer acquisition rate | Top-of-funnel health |
| First transaction rate | % of registered buyers who complete a purchase |
| Repeat transaction rate | Are buyers coming back? |
| Search-to-transaction conversion | Is matching working? |
| Average order value (AOV) | Transaction economics |

**Marketplace health metrics:**
| Metric | What It Tells You |
|---|---|
| Gross Merchandise Value (GMV) | Total transaction volume — overall marketplace scale |
| Take rate | Your revenue / GMV — monetization efficiency |
| Liquidity | % of listings that result in a transaction in a given period |
| Match rate | % of searches that result in a transaction |
| Leakage rate | % of matches that happen off-platform — the worst metric |

### The Liquidity Problem

The single biggest product challenge in marketplaces is liquidity — do buyers consistently find what they're looking for? Low liquidity means buyers leave frustrated, supply churns because they're not earning, and the marketplace collapses.

**Liquidity levers:**
1. **Geographic concentration** — don't try to be everywhere. Be liquid in a few markets before expanding. Thin coverage everywhere = low liquidity everywhere.
2. **Category concentration** — same logic. A 100-listing marketplace of car rentals is more liquid than 10-listing coverage of 10 categories.
3. **Search and matching quality** — bad search = poor discovery = apparent low supply even if supply is actually healthy.
4. **Pricing transparency** — ambiguous pricing creates friction that kills transactions. Buyers want to know what they'll pay before they engage.

### Trust Architecture

Marketplaces depend on trust between strangers. The PM's job is to build institutional trust so that individual trust between parties doesn't have to be earned from scratch.

Trust mechanisms:
- **Identity verification** — both sides know who they're dealing with
- **Ratings and reviews** — social proof, accumulated over time
- **Payments escrow / protection** — financial safety net for both sides
- **Dispute resolution** — a clear process when things go wrong
- **Insurance / guarantees** — for high-stakes transactions

---

## Part 3: E-commerce Product Management

### The E-commerce Mental Model

E-commerce is a purchase funnel with a supply chain attached. The PM optimizes two things simultaneously: the customer's path from discovery to purchase, and the operational backend that fulfills that promise.

Unlike SaaS or marketplace, e-commerce is highly sensitive to:
- **Discoverability** (paid, SEO, social, affiliate)
- **Merchandising** (what to show, when, to whom)
- **Conversion optimization** (removing friction from the purchase path)
- **Unit economics** (COGS, shipping, returns, CAC must all work together)

### The E-commerce Funnel

```
Awareness
    │
Traffic (paid, organic, social, email)
    │
Product Discovery (search, browse, recommendation)
    │
Product Detail Page (images, copy, reviews, price)
    │
Add to Cart
    │
Checkout (shipping, payment, trust signals)
    │
Order Confirmation
    │
Fulfillment & Delivery
    │
Post-Purchase (review, repeat, return)
```

PMs in e-commerce own different parts of this funnel depending on their team. Know which part you own and optimize it with the upstream and downstream context in mind.

### E-commerce Metrics

| Metric | Formula | Benchmark (varies widely) |
|---|---|---|
| Conversion Rate (CVR) | Orders / Sessions | 1–3% for most e-commerce |
| Average Order Value (AOV) | Revenue / Orders | Category-dependent |
| Revenue per Visitor (RPV) | Revenue / Sessions | CVR × AOV |
| Cart Abandonment Rate | 1 - (Completed checkouts / Add-to-carts) | 70–80% typical |
| Return Rate | Returns / Orders shipped | 10–30% depending on category |
| Customer Acquisition Cost | Total spend / New customers | Must be < LTV |
| Repeat Purchase Rate | Customers with 2+ orders / Total customers | Goal > 30% |
| Customer Lifetime Value | AOV × Purchase frequency × Avg customer lifespan | |

### E-commerce PM Priorities

**Conversion rate optimization (CRO):** Every 0.1% improvement in CVR compounds across your entire traffic base. Prioritize the highest-traffic, lowest-converting pages.

**Search and discovery:** 30–40% of e-commerce revenue comes from search. Poor search = poor discovery = lost revenue. Invest in search relevance, typo tolerance, and faceted filtering.

**Personalization:** Product recommendations ("customers also bought," "because you viewed X") can drive 15–30% of revenue when well-executed. The PM's job is to define the recommendation logic, not build the ML model.

**Checkout optimization:** Every additional step in checkout loses users. One-page checkout, address autocomplete, saved payment methods, and clear shipping costs (shown early, not at the last step) are table-stakes optimizations.

**Mobile experience:** In MENA, 70%+ of e-commerce traffic is mobile. A product experience optimized for desktop is a product experience that fails the majority of your users.

---

## Cross-Domain Patterns

### What These Three Models Have in Common

Despite their differences, the best PMs in all three domains do the same things:

1. **Know their unit economics cold.** Whether it's LTV:CAC in SaaS, take rate in marketplace, or contribution margin in e-commerce, the best product decisions are grounded in economics.

2. **Instrument the most important funnel and optimize it relentlessly.** The specific funnel differs; the discipline of instrumentation doesn't.

3. **Treat retention as the primary growth lever.** Acquisition without retention is a leaking bucket in all three models.

4. **Use qualitative research to explain what quantitative data cannot.** Metrics tell you *that* something is wrong. User interviews tell you *why*.
