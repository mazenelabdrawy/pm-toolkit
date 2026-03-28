# Growth & Monetization Strategy

> Growth is not a campaign. It is a system. Monetization is not a price tag. It is a theory about value exchange.

---

## The Growth System Model

Sustainable growth comes from loops, not funnels. Funnels leak — you have to keep pouring in the top. Loops compound — each cycle produces more than the last.

**The 4 growth loop types:**

### 1. Viral Loop (User → User)
A user gets value, which naturally leads them to bring in other users, who get value, who bring in more users.

```
User gets value ──► Shares / invites ──► New user joins
                                              │
                              ◄───────────────┘
                         New user gets value
```

**Examples:** Dropbox (share a folder → recipient joins), Notion (share a page → viewer creates an account), Squadio (hire someone → that person refers their network).

**PM's job:** Identify the natural sharing moment (when does value peak?) and reduce friction at that exact point.

---

### 2. Content Loop (Content → SEO → Users → More Content)
Users generate content that attracts organic traffic, which brings new users who generate more content.

**Examples:** Product Hunt, Tripadvisor, Stack Overflow.

**Key metrics:** Content creation rate, content quality score, organic traffic per piece of content, content → signup conversion.

---

### 3. Paid Loop (Revenue → Paid Acquisition → More Revenue)
Revenue from customers funds paid acquisition, which brings customers who generate revenue.

**When it works:** LTV > CAC with payback period < 12 months. If unit economics are negative, scaling paid acquisition accelerates losses.

**Key metric:** CAC payback period. Target varies by business type:
- Consumer SaaS: < 6 months
- B2B SME: < 12 months
- Enterprise: < 18–24 months (acceptable given LTV)

---

### 4. Product Loop (Product Improvement → Better Outcomes → Word of Mouth → More Users)
Better product → better user outcomes → more referrals and case studies → more users → more usage data → better product.

This is the hardest loop to build but the most defensible once running.

---

## Activation: The Most Underinvested Growth Lever

Most growth teams spend 80% of their budget acquiring users and 20% making them succeed. The leverage is inverted.

**Why activation matters more than acquisition:**
- A 10% improvement in acquisition increases your active user base by 10%
- A 10% improvement in activation (assuming typical 30% activation rate) increases your active user base by ~33%
- Better activation also improves word-of-mouth, NPS, and retention — acquisition improvements don't

**How to improve activation:**

1. **Define the activation event precisely.** Not "sign up" or "log in" — the specific action that correlates with retention. Run the cohort analysis: what did users who are still active after 90 days do in their first 7 days that churned users didn't?

2. **Map the path from signup to activation.** Count the steps. Remove every step that doesn't directly contribute to the activation event.

3. **Inject value before asking for investment.** Show the user what they'll get *before* asking them to set up their profile, invite their team, or connect their data.

4. **Build activation nudges at the right moments.** "Right moment" = when the user has just experienced a hint of value but hasn't reached the activation event yet.

---

## Retention: The Growth Lever Nobody Talks About

Churn is a growth ceiling. No acquisition rate can overcome compounding churn.

**The retention curve diagnostic:**

Plot your retention curve (% of users active at day 7, 14, 30, 60, 90). Healthy curves flatten. Unhealthy curves continue declining.

| Curve Shape | Signal | Action |
|---|---|---|
| Flattens early (day 7–14) | Strong core value, healthy retention | Focus on activation to get more users to the "flattened" zone |
| Slow decline that never flattens | Weak core value proposition | Product fundamentals work — find and fix the value gap |
| Cliff at day 1–3 | Severe activation problem | Users aren't reaching first value moment |
| Flattens at very low % | Small passionate core but weak mass appeal | Might be a positioning/ICP problem, not a product problem |

**Retention mechanisms by type:**

| Mechanism | What It Is | Examples |
|---|---|---|
| Habit formation | Product is used as part of a regular routine | Daily active use products (Slack, email) |
| Network effects | Value increases as more of a user's network uses it | LinkedIn, Figma |
| Data lock-in | User's data makes switching painful | CRMs, ERP systems |
| Workflow integration | Product is embedded in how work gets done | Jira, Notion |
| Switching cost | Time/effort cost of migrating | Any deeply configured enterprise tool |

---

## Monetization Architecture

### Choosing a Monetization Model

The best monetization model aligns value delivery with value capture. Ask:

1. **How does the customer measure value?** (Users, outcomes, usage volume, time saved, revenue generated)
2. **How does value scale with growth?** (As the customer grows, does value scale proportionally?)
3. **What does the buyer's budget cycle look like?** (Annual contracts, monthly, project-based?)

**Model selection matrix:**

| If value scales with... | Consider... |
|---|---|
| Number of users | Per-seat pricing |
| Usage volume | Consumption / usage-based |
| Business outcomes | Outcome-based or revenue-share |
| Time / access | Subscription (flat or tiered) |
| Transaction volume | Per-transaction fees |

---

### The Freemium Decision

Freemium is not a monetization model — it's a distribution strategy. It works when:
- You can deliver meaningful value in the free tier without giving away the business
- Free users have a natural upgrade trigger
- Network effects mean free users make paid users more valuable
- Your CAC from freemium is lower than other acquisition channels

Freemium fails when:
- The free tier attracts users who will never convert (wrong ICP)
- The upgrade trigger is artificial ("unlimited exports" — users don't need 50 exports/month)
- Support costs of free users exceed the revenue from converted users

---

### Expansion Revenue

The best SaaS companies grow primarily through expansion, not acquisition. Targets:

- **Net Revenue Retention > 120%** — you're growing revenue from existing customers faster than you're losing it from churn
- **Expansion ARR > New ARR** — the majority of new revenue comes from existing customers

**Building expansion triggers:**
1. **Seat expansion** — champion succeeds → brings in their team
2. **Usage threshold** — customer hits a limit that reflects success (storage, API calls, active users)
3. **Feature upgrade** — customer outgrows the tier they bought (classic SaaS ladder)
4. **New use case** — product solves a second problem the customer didn't originally buy for

**The expansion motion:** Don't wait for the customer to ask. Instrument usage signals and reach out proactively when expansion indicators appear. The best time to have the expansion conversation is when the customer is experiencing peak value.
