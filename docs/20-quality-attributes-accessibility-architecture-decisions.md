# 20. Quality Attributes, Architecture Decisions & Engineering Trade-offs

## 1. Functional behavior vs quality attributes
Functional requirement says what system does. Quality attributes describe how well it does it: availability, latency, throughput, scalability, security, privacy, accessibility, usability, maintainability, portability, interoperability, observability, recoverability and cost efficiency.

## 2. Turn vague goals into measurable scenarios
Instead of “system fast,” define: “Under 2,000 concurrent users and 200 requests/second, 95th percentile read latency remains below agreed threshold for specified endpoint.” Specify workload, environment, measurement window and acceptable failure behavior. Numbers must come from product needs and testing, not arbitrary templates.

## 3. Availability and reliability math
Availability approximation: uptime / total measured time. For independent serial components, end-to-end availability can be lower than each component; redundancy helps only if failure modes are sufficiently independent. SLA is a contractual promise, SLO an internal/service objective, and SLI the measured indicator. Error budget is the allowed unreliability implied by an SLO.

## 4. Latency percentiles and throughput
Average latency can hide tail delays. p50 is median, p95 means 95% of measured requests are at or below that latency, and p99 highlights tail experience. Throughput is completed work per time. Test realistic traffic mix, cache warmth, data size and failure conditions.

## 5. Scalability and capacity
Vertical scaling increases resources on a node; horizontal scaling adds nodes. Stateless services are easier to scale horizontally, while stateful components need replication/partitioning/consistency strategy. Capacity planning includes CPU, memory, connection pools, DB IOPS, network, queue depth and downstream limits.

## 6. Resilience patterns
Timeouts prevent indefinite waits; retries should be bounded and use backoff/jitter; circuit breakers reduce repeated calls to failing dependencies; bulkheads isolate resource pools; queues absorb bursts; load shedding protects core service. Retries can amplify overload if poorly designed. Every pattern needs observability and fallback behavior.

## 7. Architecture decisions
Use Architecture Decision Records (ADR): context, decision, alternatives, consequences, date and owner. Prefer reversible decisions under uncertainty. Evaluate build vs buy, monolith vs services, relational vs NoSQL, synchronous vs asynchronous and managed vs self-hosted against actual constraints.

## 8. Threat modeling and privacy by design
Map assets, actors, trust boundaries, entry points and data flows. Ask what can go wrong, likelihood/impact, mitigations and residual risk. Privacy by design means data minimization, purpose limitation, retention controls and user rights considered early, not added only at launch.

## 9. Accessibility as quality
Follow WCAG guidance appropriate to the product; use semantic HTML, keyboard support, visible focus, sufficient contrast, labels, captions and screen-reader testing. Automated checks catch some but not all accessibility defects; include manual testing with assistive technologies and users where possible.

## 10. Maintainability and technical debt
Technical debt is the future cost created by expedient choices, not automatically bad code. Record debt, risk and payoff; reserve capacity to address high-impact items. Modular boundaries, tests, documentation, dependency updates and small changes reduce maintenance cost.

## 11. Cost-aware architecture
Estimate compute, storage, network egress, managed services, licenses, observability, backups, support and engineer time. Optimize the largest measured cost drivers. Premature optimization and distributed systems can increase complexity beyond their benefits.

## Practical exercise
Write 5 measurable quality scenarios for an exchange-like application: market-data freshness, login security, order submission response, failure recovery and accessibility. Add an ADR for choosing synchronous API vs event queue.

## Questions
1. SLI/SLO/SLA difference?
2. Why p95 can be more useful than average?
3. How can retries worsen an outage?
4. What belongs in an ADR?
