# GTM Launch Checklist — B2B Product Releases

This checklist is for shipping a product or feature to existing or new B2B customers. Adjust for size of launch (alpha, beta, GA, major release).

---

## 1. Pre-Launch (T-4 weeks)

### Alignment
- [ ] Launch goals defined and shared with leadership
- [ ] Success metrics agreed upon (primary + guardrail)
- [ ] Launch tier defined: Soft launch / Limited GA / Full GA
- [ ] Rollout plan finalized (% of users, cohort criteria, timeline)

### Product Readiness
- [ ] Feature flag / rollout infrastructure in place
- [ ] All P0 and P1 bugs resolved
- [ ] Edge cases documented and handled or explicitly deferred
- [ ] Monitoring and alerting configured for key flows

### Internal Enablement
- [ ] Sales & CS briefed on the feature (what it does, key benefits, common objections)
- [ ] Internal FAQ document created
- [ ] Demo video or walkthrough available for sales/CS
- [ ] Support documentation drafted

---

## 2. Launch Week (T-1 week)

### Customer Communications
- [ ] Release notes written (customer-facing)
- [ ] Email announcement drafted and reviewed
- [ ] In-app announcement / tooltip copy ready
- [ ] Help center article live or staged

### Technical
- [ ] Staging environment validated
- [ ] Load test completed (if significant traffic change expected)
- [ ] Rollback plan documented and tested
- [ ] Data pipeline verified (events firing, dashboards updating)

### Stakeholder Check-In
- [ ] PM, Eng, Design, CS, Sales all confirmed go/no-go
- [ ] Launch date and time locked
- [ ] On-call coverage confirmed for launch day

---

## 3. Launch Day

- [ ] Feature flag enabled for target cohort
- [ ] Error rates monitored in real-time (first 2 hours)
- [ ] Key metrics baseline captured (before vs. day 1)
- [ ] Customer-facing communications sent
- [ ] Slack channel or war room open for issues

---

## 4. Post-Launch (T+1 week)

- [ ] Metrics review: Did we hit early indicators?
- [ ] CS/support tickets triaged for patterns
- [ ] Any critical issues documented and remediated
- [ ] User feedback collected (NPS, in-app survey, CS escalations)
- [ ] Launch retrospective scheduled

---

## 5. Post-Launch (T+30 days)

- [ ] Full metrics review against success criteria
- [ ] Decision: expand rollout / adjust / pause
- [ ] Learnings documented in the team wiki
- [ ] Next iteration scoped if applicable

---

## Common Failure Modes to Watch

| Failure | Early Signal | Response |
|---|---|---|
| Low adoption despite launch | Low feature discovery rate | In-app guidance, CS outreach |
| Unexpected support volume | CS ticket spike in first 48h | KB article fast-track, PM on standby |
| Performance degradation | Latency spike post-launch | Rollback or feature flag off |
| Wrong audience reached | Feedback mismatch | Targeting review, cohort adjustment |
