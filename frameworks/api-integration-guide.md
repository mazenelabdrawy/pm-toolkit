# PM Guide to API Integrations

> PMs who understand APIs don't need to write code. They need to ask better questions, write better specs, and avoid the failure modes that come from treating integrations as a black box.

---

## Why PMs Need to Understand APIs

Product integrations are a common source of project failure and timeline slippage — not because engineering is slow, but because the requirements were underspecified. Every "the integration took 3x longer than expected" story usually has one of these root causes:

- The PM didn't know the third-party API had rate limits
- The PM assumed data would be available that the API doesn't expose
- The PM didn't account for authentication complexity (OAuth flows, token refresh)
- The PM didn't define what happens when the third-party API is down
- The PM didn't think about data transformation between the two schemas

Understanding APIs doesn't require being able to build them. It requires knowing the right questions to ask.

---

## API Fundamentals for PMs

### What an API Actually Is

An API (Application Programming Interface) is a defined contract between two systems. It specifies:
- What you can ask the system to do (endpoints / methods)
- What you need to provide to make the request (parameters, authentication)
- What the system will return (response schema)
- What the rules are (rate limits, authentication requirements, data policies)

Think of it as a menu at a restaurant. You can only order what's on the menu; you can't ask the kitchen to make something that isn't there.

---

### The 5 Things to Verify Before Scoping an Integration

**1. What data does the API actually expose?**

"We want to integrate with [platform]" is not a requirement. The requirement is "we need to read X data and write Y data." Check the API documentation to confirm X and Y are actually available. Assume nothing.

Common discovery: "We wanted to pull customer purchase history, but the API only exposes the last 90 days."

**2. What are the rate limits?**

APIs throttle requests. If your feature needs to sync 10,000 records for a customer with 10,000 items, and the API allows 100 requests per minute, that sync takes over 100 minutes. That may be unacceptable for your user experience.

Questions to ask engineering:
- How many API calls does our integration require per user action?
- What happens when we hit the rate limit — does the UI degrade gracefully?
- For batch jobs, what is the sync frequency and will we stay within limits?

**3. What is the authentication flow?**

Different authentication types have different complexity and user experience implications:

| Auth Type | UX Implication | Complexity |
|---|---|---|
| API Key | User copies a key from their account settings | Low — one-time setup |
| OAuth 2.0 | User is redirected to authorize, then returned | Medium — requires callback URL, token refresh |
| OAuth + Scopes | User sees a permissions screen before authorizing | Medium — scope selection affects what you can access |
| JWT | System-to-system, usually invisible to user | Low UX complexity, but token expiry handling matters |
| Webhook-based | Third party pushes data to you | Medium — requires a publicly accessible endpoint |

**4. What is the reliability SLA of the third-party API?**

Your product's reliability is limited by the least reliable thing it depends on. If you integrate with a third-party API that has 99% uptime, your integration feature will have at most 99% uptime — and probably less, because you've added your own failure surface.

Ask: What is our fallback behavior when the API is unavailable? Options:
- Show cached data with a "last updated X minutes ago" indicator
- Disable the integration feature and surface a clear error
- Queue the user's actions and execute them when the API recovers

**5. What are the data transformation requirements?**

APIs don't always return data in the format your product needs. Common transformation challenges:
- Field name mismatches ("customer_id" in one system, "clientId" in another)
- Data type differences (dates as strings vs. timestamps vs. epoch)
- Schema mismatches (the API returns a flat structure; your product needs a nested one)
- Missing fields (the API doesn't return a field your product needs — now what?)

Every transformation is a mapping decision that needs to be spec'd before engineering starts building.

---

## Writing an Integration Spec

An integration spec answers these questions:

### Data Flow Diagram
Describe (or diagram) how data flows between the two systems. Which system is the source of truth for which data?

### Trigger Events
What triggers data to be exchanged? Options:
- Real-time (webhook — third party pushes when something changes)
- On-demand (user-triggered sync)
- Scheduled (periodic batch sync — every hour, every day)

### Field Mapping Table

| Your System Field | API Field | Transformation | Handling if Missing |
|---|---|---|---|
| customer_id | user.id | Cast to string | Error — required |
| email | user.email_address | None | Error — required |
| created_date | user.created_at | Convert ISO 8601 to Unix timestamp | Error — required |
| company_name | user.organization.name | None | Default to empty string |

### Error States

Define what happens in each failure scenario:

| Scenario | Behavior |
|---|---|
| API unavailable | Show cached data; queue writes; surface status indicator |
| Rate limit exceeded | Retry with exponential backoff; notify user if sync delayed > 5 min |
| Authentication expired | Prompt user to re-authenticate; do not silently fail |
| Schema change (API changed a field) | Log error; alert on-call; do not corrupt existing data |
| Partial sync failure | Complete records that succeeded; retry failed records; surface count to user |

### Rollback Plan
If the integration causes data issues, how do we roll back? Can we restore previous data states? Is there a feature flag to disable the integration?

---

## Integration Patterns PMs Should Know

### Webhooks vs. Polling

**Webhooks:** The third-party pushes data to you when something changes. Real-time, efficient.
*PM implication:* You need a publicly accessible endpoint. Requires handling duplicate events (webhooks can fire multiple times for the same event). Requires an event log.

**Polling:** You periodically ask the API for changes.
*PM implication:* Introduces latency (data is only as fresh as your last poll). Simpler to build. Can hit rate limits if polling too frequently.

**When to choose which:** Webhooks for real-time user-visible data; polling for background sync where slight latency is acceptable.

---

### Bi-directional Sync

The hardest type of integration. Data flows in both directions, creating conflict scenarios:
- User edits record in your system; third-party system also has an edit for the same record
- Which edit wins?

Before scoping bi-directional sync, define the conflict resolution strategy explicitly. Options:
- **Last write wins** — most recent edit overrides (simple, but can lose data)
- **Source of truth designation** — one system always wins for specific field types
- **Conflict surfacing** — show the user both versions and ask them to choose

---

## Integration Checklist for PMs

Before a sprint:
- [ ] API documentation reviewed — confirmed data you need is available
- [ ] Rate limits documented — confirmed integration stays within limits
- [ ] Auth flow agreed — UX impact of authentication scoped and designed
- [ ] Error states defined — every failure scenario has a defined behavior
- [ ] Field mapping table complete — every field has a source, transformation, and missing-value handler
- [ ] Rollback plan documented — engineering knows how to disable or revert

After launch:
- [ ] API error rate monitored
- [ ] Sync latency tracked
- [ ] User re-auth prompts monitored (excessive re-auth = token refresh bug)
- [ ] Data integrity checks in place (sample comparison between systems)
