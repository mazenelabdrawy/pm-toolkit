# Prioritization Framework

RICE is a starting point, not a final answer. Here's how I use it — and where I deviate.

---

## RICE Formula

```
Score = (Reach × Impact × Confidence) / Effort
```

| Variable | What I Mean By It |
|---|---|
| **Reach** | Users affected per quarter. Use conservative estimates. |
| **Impact** | How much it moves the primary metric. Score 0.25, 0.5, 1, 2, 3. |
| **Confidence** | How sure are we? 100% = solid data. 80% = some data. 50% = gut. |
| **Effort** | Person-months. Include PM + design + eng + QA. |

---

## My Adjustments to Vanilla RICE

### 1. Strategic Multiplier (0.5–1.5×)
Some items punch above their RICE weight because of strategic timing — a competitor just shipped something, a major customer is asking, or it unlocks a product area we're trying to expand into.

Add a strategic multiplier:
- 1.5× — directly enables a key company objective
- 1.0× — neutral, no special strategic relevance
- 0.5× — may be deprioritizing by doing this (opportunity cost is high)

### 2. Debt/Risk Tax
If the feature can't be built without fixing tech debt, add the debt effort to the total. Don't hide it.

### 3. Confidence Calibration
Most teams overestimate confidence. Before scoring:
- Ask: "What would have to be true for our impact estimate to be wrong?"
- Ask: "When did we last validate this with a user in the last 60 days?"
- If the answers make you nervous, drop confidence to 50%.

---

## How I Run a Prioritization Session

**Before the meeting:**
- Each stakeholder scores independently (to avoid anchoring)
- I collect scores in a shared sheet before anyone sees others' scores

**In the meeting:**
- Surface outliers only — items where scores diverge by 2+ points
- Discuss "why" on outliers, not "who's right"
- Reserve final call on strategic items for PM + leadership

**Output:**
- Prioritized backlog in three tiers: Now / Next / Later
- Any item with a strategic modifier noted and visible
- Open questions that need resolution before items can move up

---

## When to Override the Score

RICE is a decision support tool, not a decision maker. Override when:
- A customer contract depends on it (talk to sales before scoring)
- Legal or compliance deadline exists
- It's a dependency for a higher-priority item
- The score is within 20% of adjacent items (treat as a tie, use judgment)

---

## The Test I Always Run

Before locking a roadmap quarter, I ask:
> "If we shipped only these 3 items and nothing else, would it be a meaningful quarter?"

If the answer is no, the prioritization is wrong.
